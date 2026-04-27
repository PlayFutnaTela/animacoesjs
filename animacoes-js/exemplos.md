# Exemplos

## Animações de Texto

### Efeito de Split
```javascript
import { animate } from 'animejs';

const textElement = document.querySelector('.title');
const chars = textElement.textContent.split('');
textElement.innerHTML = chars.map(char => `<span>${char}</span>`).join('');

animate({
  targets: '.title span',
  translateY: [-100, 0],
  opacity: [0, 1],
  delay: animate.stagger(80, { from: 'center' }),
  easing: 'easeOutBack'
});
```

### Hover Effect
```javascript
const links = document.querySelectorAll('a');

links.forEach(link => {
  link.addEventListener('mouseenter', () => {
    animate({
      targets: link,
      color: ['#fff', '#ff6b6b'],
      scale: [1, 1.1],
      duration: 300
    });
  });
});
```

## Animações de SVG

### Linha Desenhando
```javascript
animate({
  targets: 'path',
  strokeDashoffset: [anime.setDashoffset, 0],
  easing: 'easeInOutSine',
  duration: 1500,
  loop: true,
  direction: 'alternate'
});
```

### Gráfico de Barras
```javascript
const bars = document.querySelectorAll('.bar');

animate({
  targets: bars,
  height: [0, '100%'],
  fill: ['#3498db', '#2ecc71'],
  duration: 1000,
  delay: animate.stagger(100),
  easing: 'easeOutElastic'
});
```

## Animações de Scroll

### Elemento Entrando na Tela
```javascript
import { animate } from 'animejs';

const observer = new IntersectionObserver((entries) => {
  entries.forEach(entry => {
    if (entry.isIntersecting) {
      animate({
        targets: entry.target,
        translateY: [50, 0],
        opacity: [0, 1],
        duration: 600,
        easing: 'easeOutQuad'
      });
      observer.unobserve(entry.target);
    }
  });
});

document.querySelectorAll('.fade-in').forEach(el => {
  observer.observe(el);
});
```

## Animações de Carregamento

### Loading Spinner
```javascript
animate({
  targets: '.spinner',
  rotate: 360,
  duration: 1000,
  easing: 'linear',
  loop: true
});
```

### Progress Bar
```javascript
const progressBar = document.querySelector('.progress');

animate({
  targets: progressBar,
  width: ['0%', '100%'],
  duration: 2000,
  easing: 'easeInOutQuad',
  complete: () => {
    console.log('Carregamento completo!');
  }
});
```

## Animações de Menu

### Hamburger Menu
```javascript
const menuBtn = document.querySelector('.menu-btn');
const lines = document.querySelectorAll('.menu-line');

menuBtn.addEventListener('click', () => {
  lines.forEach((line, i) => {
    animate({
      targets: line,
      rotate: i === 1 ? [0, 45] : [0, -45],
      translateY: i === 1 ? [0, -10] : [0, 10],
      duration: 200,
      easing: 'easeInOutQuad'
    });
  });
});
```

### Dropdown Menu
```javascript
const dropdown = document.querySelector('.dropdown');
const menu = document.querySelector('.menu-items');

dropdown.addEventListener('click', () => {
  animate({
    targets: menu,
    height: menu.style.height === '0px' ? [0, 200] : [200, 0],
    opacity: menu.style.height === '0px' ? [0, 1] : [1, 0],
    duration: 300,
    easing: 'easeInOutQuad'
  });
});
```
