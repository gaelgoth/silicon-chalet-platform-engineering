import { ref, onMounted, onBeforeUnmount, computed, watch } from 'vue';
import { Icon } from '@iconify/vue';

const props = defineProps({
  numberOfTools: { type: Number, default: 12 },
  rotationSpeed: { type: Number, default: 0.5 }
});

const toolIcons = [
  'mdi:language-javascript', 'mdi:language-python', 'mdi:react',
  'mdi:docker', 'mdi:kubernetes', 'mdi:git', 'mdi:database',
  'mdi:cloud', 'mdi:api', 'mdi:console', 'mdi:folder-network',
  'mdi:application', 'mdi:web', 'mdi:test-tube', 'mdi:cog-outline',
  'mdi:monitor-dashboard'
];

const canvasRef = ref(null);
let animationFrame = null;
let ctx;
const width = ref(600);
const height = ref(400);

const createTools = () => {
  const tools = [];
  const iconCount = Math.min(props.numberOfTools, toolIcons.length);
  for (let i = 0; i < iconCount; i++) {
    tools.push({
      icon: toolIcons[i],
      angle: Math.random() * Math.PI * 2,
      radius: 50 + Math.random() * 130,
      speed: (0.2 + Math.random() * 0.8) * props.rotationSpeed * (Math.random() > 0.5 ? 1 : -1),
      size: 24 + Math.random() * 12,
      eccentricity: 0.7 + Math.random() * 0.3,
      yOffset: (Math.random() - 0.5) * 60
    });
  }
  return tools;
};

const tools = ref(createTools());
const toolPositions = computed(() => tools.value.map(tool => ({
  ...tool,
  x: width.value / 2 + Math.cos(tool.angle) * tool.radius * tool.eccentricity,
  y: height.value / 2 + Math.sin(tool.angle) * tool.radius + tool.yOffset
})));

const animate = () => {
  tools.value.forEach(tool => (tool.angle += tool.speed / 100));
  ctx.clearRect(0, 0, width.value, height.value);
  ctx.fillStyle = '#8B5CF6';
  ctx.font = 'bold 24px sans-serif';
  ctx.textAlign = 'center';
  ctx.textBaseline = 'middle';
  ctx.fillText('DevEx', width.value / 2, height.value / 2);
  requestAnimationFrame(animate);
};

const updateCanvasSize = () => {
  const canvas = canvasRef.value;
  if (!canvas || !canvas.parentElement) return;
  width.value = canvas.parentElement.clientWidth;
  height.value = canvas.parentElement.clientHeight;
  canvas.width = width.value * 2;
  canvas.height = height.value * 2;
  ctx.scale(2, 2);
};

onMounted(() => {
  ctx = canvasRef.value.getContext('2d');
  updateCanvasSize();
  window.addEventListener('resize', updateCanvasSize);
  animationFrame = requestAnimationFrame(animate);
});

onBeforeUnmount(() => {
  cancelAnimationFrame(animationFrame);
  window.removeEventListener('resize', updateCanvasSize);
});
