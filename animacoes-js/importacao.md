# Importação

## ES Modules (Projetos Modernos)

```javascript
import { animate, stagger, timeline } from 'animejs';

// Ou importação seletiva
import animate from 'animejs';
import { stagger } from 'animejs';
```

## CommonJS (Node.js)

```javascript
const { animate, stagger, timeline } = require('animejs');
```

## CDN (Browser Direto)

```html
<script src="https://cdn.jsdelivr.net/npm/animejs@4.3.6/dist/bundles/anime.min.js"></script>
<script>
  // A variável 'anime' fica disponível globalmente
  anime({
    targets: '.element',
    translateX: 250
  });
</script>
```

## TypeScript

```typescript
import { animate, stagger, timeline, Animatable } from 'animejs';

// Tipos são automaticamente inferidos
const animation = animate('.box', {
  translateX: 100,
  duration: 1000
});
```

## Importação de Submódulos

O Anime.js permite importar funcionalidades específicas:

```javascript
// Timer apenas
import { timer } from 'animejs/timer';

// Timeline apenas
import { timeline } from 'animejs/timeline';

// Easings
import { easings } from 'animejs/easings';

// Draggable
import { draggable } from 'animejs/draggable';
```
