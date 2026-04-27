# Easings (Funções de Interpolação)

Os easings definem como a animação acelera e desacelera ao longo do tempo.

## Tipos de Easing

### Simples
- `linear` - Velocidade constante
- `easeInQuad` - Aceleração quadrática
- `easeOutQuad` - Desaceleração quadrática
- `easeInOutQuad` - Aceleração e desaceleração

### Cúbicos
- `easeInCubic` - Aceleração cúbica
- `easeOutCubic` - Desaceleração cúbica
- `easeInOutCubic` - Aceleração e desaceleração cúbica

### Elásticos
- `easeOutElastic` - Efeito elástico no final
- `easeInElastic` - Efeito elástico no início
- `easeInOutElastic` - Efeito elástico em ambos

### Bounce (Quicando)
- `easeOutBounce` - Quica no final
- `easeInBounce` - Quica no início
- `easeInOutBounce` - Quica em ambos

## Uso

```javascript
import { animate } from 'animejs';

// Easing simples
animate({
  targets: '.box',
  translateX: 300,
  easing: 'easeInOutQuad'
});

// Easing elástico
animate({
  targets: '.circle',
  scale: [0, 1.2, 1],
  easing: 'easeOutElastic(1, .5)'
});

// Easing customizado (cubic-bezier)
animate({
  targets: '.element',
  translateX: 300,
  easing: 'cubic-bezier(0.68, -0.55, 0.265, 1.55)'
});
```

## Easing Personalizados

Você pode usar cubic-bezier personalizados:

```javascript
animate({
  targets: '.box',
  translateX: 300,
  easing: 'cubic-bezier(0.68, -0.55, 0.265, 1.55)' // Bounce
});

animate({
  targets: '.box',
  translateX: 300,
  easing: 'cubic-bezier(0.77, 0, 0.175, 1)' // EaseOutBack
});
```

## Lista Completa

```
linear
easeInQuad, easeOutQuad, easeInOutQuad
easeInCubic, easeOutCubic, easeInOutCubic
easeInQuart, easeOutQuart, easeInOutQuart
easeInQuint, easeOutQuint, easeInOutQuint
easeInSine, easeOutSine, easeInOutSine
easeInExpo, easeOutExpo, easeInOutExpo
easeInCirc, easeOutCirc, easeInOutCirc
easeInBack, easeOutBack, easeInOutBack
easeInElastic, easeOutElastic, easeInOutElastic
easeInBounce, easeOutBounce, easeInOutBounce
```
