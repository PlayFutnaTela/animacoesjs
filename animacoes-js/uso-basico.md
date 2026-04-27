# Uso Básico

## Animação Simples

```javascript
import { animate } from 'animejs';

animate({
  targets: '.element',
  translateX: 250,
  rotate: 360,
  duration: 1000,
  easing: 'easeInOutQuad'
});
```

## Parâmetros Principais

| Parâmetro | Descrição | Tipo | Obrigatório |
|-----------|-----------|------|-------------|
| `targets` | Elementos a animar (seletor, array, objeto) | string/array/object | Sim |
| `translateX` | Movimento horizontal (px) | number | Não |
| `translateY` | Movimento vertical (px) | number | Não |
| `rotate` | Rotação (graus) | number | Não |
| `scale` | Escala | number | Não |
| `opacity` | Opacidade (0-1) | number | Não |
| `duration` | Duração em ms | number | Não (padrão: 1000) |
| `easing` | Função de easing | string | Não (padrão: 'easeOutElastic') |
| `delay` | Delay inicial | number | Não (padrão: 0) |
| `loop` | Número de loops ou true | number/boolean | Não (padrão: false) |
| `direction` | 'normal' ou 'alternate' | string | Não (padrão: 'normal') |

## Exemplos Práticos

### Mover Elemento
```javascript
animate({
  targets: '.box',
  translateX: 300,
  duration: 1500
});
```

### Rotacionar e Escalar
```javascript
animate({
  targets: '.circle',
  rotate: 360,
  scale: [0, 1],
  duration: 2000,
  easing: 'easeInOutQuad'
});
```

### Animação com Loop
```javascript
animate({
  targets: '.pulse',
  scale: [1, 1.2, 1],
  opacity: [1, 0.5, 1],
  duration: 1000,
  loop: true,
  direction: 'alternate'
});
```
