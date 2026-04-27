# API Principal

## animate()

Função principal para criar animações.

```javascript
import { animate } from 'animejs';

const animation = animate({
  targets: '.element',
  translateX: 250,
  duration: 1000
});
```

### Métodos do Objeto Animation

| Método | Descrição |
|--------|-----------|
| `play()` | Inicia a animação |
| `pause()` | Pausa a animação |
| `restart()` | Reinicia a animação |
| `finish()` | Finaliza a animação |
| `seek(time)` | Pula para um tempo específico (ms) |
| `reverse()` | Inverte a direção da animação |

### Exemplo com Controle

```javascript
const animation = animate({
  targets: '.box',
  translateX: 300,
  duration: 2000,
  loop: true
});

// Controles
animation.pause();
animation.play();
animation.reverse();
animation.seek(1000);
```

## timeline()

Cria uma linha do tempo para animações encadeadas.

```javascript
import { timeline } from 'animejs';

const tl = timeline({
  duration: 1000,
  easing: 'easeInOutQuad',
  loop: true
});

tl.add({
  targets: '.element1',
  translateX: 250
});

tl.add({
  targets: '.element2',
  translateY: 250
});

tl.add({
  targets: '.element3',
  rotate: 360
});
```

### Métodos do Timeline

| Método | Descrição |
|--------|-----------|
| `add(props)` | Adiciona uma animação à linha do tempo |
| `play()` | Inicia a linha do tempo |
| `pause()` | Pausa a linha do tempo |
| `restart()` | Reinicia a linha do tempo |
| `seek(time)` | Pula para um tempo específico |
| `reverse()` | Inverte a direção |

## stagger()

Cria um delay progressivo entre elementos.

```javascript
import { stagger } from 'animejs';

animate({
  targets: '.items',
  translateX: 250,
  delay: stagger(100, {
    from: 'center',  // 'first', 'last', 'center', ou índice numérico
    axis: 'x',       // 'x', 'y', ou 'xy'
    start: 0,
    end: 500
  })
});
```

### Opções do Stagger

| Opção | Descrição | Valores |
|-------|-----------|---------|
| `from` | Ponto de início | 'first', 'last', 'center', número |
| `axis` | Eixo do stagger | 'x', 'y', 'xy' |
| `start` | Delay inicial | número |
| `end` | Delay final | número |
| `grid` | Grid para stagger 2D | [linhas, colunas] |
| `amount` | Quantidade total de delay | número |
| `direction` | Direção | 'normal', 'reverse' |
