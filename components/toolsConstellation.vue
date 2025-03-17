<template>
  <div class="devex-constellation-container">
    <canvas ref="canvasRef" class="constellation-canvas"></canvas>

    <!-- Center DevEx text -->
    <div class="devex-center">
      <span>DevEx</span>
    </div>

    <!-- Actual icon elements displayed over the canvas -->
    <div
      v-for="(tool, index) in toolPositions"
      :key="index"
      class="tool-icon"
      :style="{
        left: `${tool.x}px`,
        top: `${tool.y}px`,
        fontSize: `${tool.size}px`
      }"
    >
      <Icon :icon="tool.icon" />
    </div>
  </div>
</template>

<script setup>
import { ref, onMounted, onBeforeUnmount, computed, nextTick } from 'vue';
import { Icon } from '@iconify/vue';

const props = defineProps({
  numberOfTools: {
    type: Number,
    default: 12,
  },
  rotationSpeed: {
    type: Number,
    default: 0.5,
  },
});

const toolIcons = [
  'simple-icons:backstage',
  'simple-icons:helm',
  'simple-icons:jenkins',
  'simple-icons:confluence',
  'simple-icons:flux',
  'codicon:azure',
  "mdi:aws",
  "mdi:github",
  "mdi:jira",
  'mdi:kubernetes',
  'mdi:react',
  'mdi:language-python',
  'mdi:test-tube',
  'mdi:language-java',
  'mdi:api',
  'mdi:database',
  'mdi:console',
  'simple-icons:sonar'
];

const canvasRef = ref(null);
let animationFrame = null;
let ctx;
const width = ref(600);
const height = ref(400);
let resizeObserver;

const updateCanvasSize = () => {
  const container = canvasRef.value.parentElement;
  if (container) {
    width.value = container.clientWidth;
    height.value = container.clientHeight;
    const canvas = canvasRef.value;
    canvas.width = width.value * 2;
    canvas.height = height.value * 2;
    ctx.scale(2, 2);
  }
};

const createTools = () => {
  return Array.from({ length: Math.min(props.numberOfTools, toolIcons.length) }, (_, i) => ({
    icon: toolIcons[i],
    angle: Math.random() * Math.PI * 2,
    radius: 50 + Math.random() * 130,
    speed: (0.2 + Math.random() * 0.8) * props.rotationSpeed * (Math.random() > 0.5 ? 1 : -1),
    size: 24 + Math.random() * 12,
    eccentricity: 0.7 + Math.random() * 0.3,
    yOffset: (Math.random() - 0.5) * 60,
  }));
};

const tools = ref(createTools());

const toolPositions = computed(() => {
  return tools.value.map((tool) => ({
    ...tool,
    x: width.value / 2 + Math.cos(tool.angle) * tool.radius * tool.eccentricity,
    y: height.value / 2 + Math.sin(tool.angle) * tool.radius + tool.yOffset,
  }));
});

const animate = () => {
  tools.value.forEach((tool) => { tool.angle += tool.speed / 100; });
  ctx.clearRect(0, 0, width.value, height.value);

  toolPositions.value.forEach((tool) => {
    ctx.beginPath();
    ctx.ellipse(width.value / 2, height.value / 2 + tool.yOffset, tool.radius * tool.eccentricity, tool.radius, 0, 0, Math.PI * 2);
    ctx.strokeStyle = 'rgba(0, 0, 0, 0.1)';
    ctx.stroke();
  });

  animationFrame = requestAnimationFrame(animate);
};

onMounted(() => {
  const canvas = canvasRef.value;
  const container = canvas.parentElement;

  if (canvas && container) {
    ctx = canvas.getContext('2d');

    // Use nextTick to ensure the DOM is fully updated
    nextTick(() => {
      updateCanvasSize();
      animationFrame = requestAnimationFrame(animate);
    });

    // Use ResizeObserver to handle container size changes
    resizeObserver = new ResizeObserver(updateCanvasSize);
    resizeObserver.observe(container);
  }
});

onBeforeUnmount(() => {
  if (animationFrame) cancelAnimationFrame(animationFrame);
  if (resizeObserver) resizeObserver.disconnect();
});
</script>

<style scoped>
.devex-constellation-container {
  @apply relative w-full h-full flex items-center justify-center min-h-[400px] overflow-hidden;
}

.constellation-canvas {
  @apply absolute top-0 left-0 w-full h-full;
}

.devex-center {
  @apply absolute top-1/2 left-1/2 transform -translate-x-1/2 -translate-y-1/2;
  @apply text-2xl font-bold text-gray-900 bg-white bg-opacity-90;
  @apply px-4 py-2 rounded-2xl shadow-lg shadow-gray-500/20 z-10;
}

.tool-icon {
  @apply absolute transform -translate-x-1/2 -translate-y-1/2;
  @apply text-gray-900 filter drop-shadow-lg transition-all duration-300 ease-in-out z-5;
  @apply flex justify-center items-center bg-white bg-opacity-90 rounded-full;
  @apply w-12 h-12 p-3;
}
</style>