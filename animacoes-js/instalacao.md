# Instalação

## Via npm (Recomendado)

```bash
npm install animejs
```

## Via Yarn

```bash
yarn add animejs
```

## Via CDN

### Versão UMD (minificada)
```html
<script src="https://cdn.jsdelivr.net/npm/animejs@4.3.6/dist/bundles/anime.umd.min.js"></script>
```

### Versão ESM
```html
<script type="module">
  import { animate } from 'https://cdn.jsdelivr.net/npm/animejs@4.3.6/dist/modules/index.js';
</script>
```

## Arquivos Disponíveis

A pasta `dist/` contém:

| Arquivo | Descrição | Uso |
|---------|-----------|-----|
| `dist/modules/index.js` | Módulo ES (ESM) | Projetos modernos com import/export |
| `dist/modules/index.cjs` | Módulo CommonJS | Projetos Node.js |
| `dist/bundles/anime.umd.min.js` | UMD minificado | Browser direto |
| `dist/modules/index.d.ts` | Tipos TypeScript | Projetos TypeScript |

## Estrutura de Módulos

O Anime.js V4 usa módulos ES6. Você pode importar apenas o que precisa:

```javascript
// Importação completa
import { animate, stagger, timeline } from 'animejs';

// Importação seletiva (tree-shaking)
import animate from 'animejs/lib/animate';
import stagger from 'animejs/lib/stagger';
```
