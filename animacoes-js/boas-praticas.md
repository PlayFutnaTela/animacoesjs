# Boas Práticas

## Performance

### 1. Use transform e opacity
```javascript
// ✅ BOM - Usa GPU
animate({
  targets: '.box',
  translateX: 300,
  opacity: [0, 1]
});

// ❌ RUIM - Força layout
animate({
  targets: '.box',
  left: 300,
  width: '200px'
});
```

### 2. Reduza o número de elementos animados
```javascript
// ✅ Anima container
animate({
  targets: '.container',
  translateX: 300
});

// ❌ Anima muitos elementos
document.querySelectorAll('.item').forEach(item => {
  animate({ targets: item, translateX: 300 });
});
```

### 3. Use requestAnimationFrame
```javascript
// O Anime.js já usa requestAnimationFrame internamente
// Não é necessário envolver em requestAnimationFrame
```

## Código Limpo

### 1. Reutilize configurações
```javascript
const baseAnimation = {
  duration: 500,
  easing: 'easeInOutQuad',
  complete: () => console.log('Animação finalizada')
};

animate({ ...baseAnimation, targets: '.box1', translateX: 100 });
animate({ ...baseAnimation, targets: '.box2', translateY: 100 });
```

### 2. Use variáveis para valores repetidos
```javascript
const DURATION = 1000;
const EASING = 'easeInOutQuad';

animate({ targets: '.a', translateX: 100, duration: DURATION, easing: EASING });
animate({ targets: '.b', translateX: 200, duration: DURATION, easing: EASING });
```

### 3. Separe lógica de animação
```javascript
function fadeIn(element) {
  return animate({
    targets: element,
    opacity: [0, 1],
    duration: 300
  });
}

function slideIn(element) {
  return animate({
    targets: element,
    translateX: [100, 0],
    duration: 500
  });
}
```

## Acessibilidade

### 1. Respeite prefers-reduced-motion
```javascript
const prefersReducedMotion = window.matchMedia('(prefers-reduced-motion: reduce)').matches;

if (!prefersReducedMotion) {
  animate({ targets: '.element', translateX: 300, duration: 500 });
}
```

### 2. Forneça fallbacks
```javascript
const element = document.querySelector('.box');

if (element.animate) {
  // Usa Web Animations API
  element.animate({ transform: 'translateX(300px)' }, { duration: 500 });
} else {
  // Fallback com CSS
  element.style.transition = 'transform 500ms';
  element.style.transform = 'translateX(300px)';
}
```

## Eventos e Callbacks

```javascript
animate({
  targets: '.box',
  translateX: 300,
  duration: 1000,
  begin: () => console.log('Iniciou'),
  update: () => console.log('Atualizando'),
  complete: () => console.log('Finalizou'),
  loop: true
});
```

### Eventos Disponíveis
- `begin` - Quando a animação começa
- `update` - A cada frame da animação
- `complete` - Quando a animação termina
- `loop` - A cada loop
- `change` - Quando um valor muda
