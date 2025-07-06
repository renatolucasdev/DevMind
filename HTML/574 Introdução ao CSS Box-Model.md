# Introdução ao CSS Box Model

## Conceito Fundamental

- **Tudo é caixa no HTML/CSS**: Todos os elementos são representados como caixas retangulares ou quadradas
- **Estrutura básica**: Para criar um site, você posiciona caixas dentro de outras caixas
- **Renderização**: O navegador usa o Box Model para calcular como exibir cada elemento na tela

## Componentes do Box Model (de dentro para fora)

### 1. **Content (Conteúdo)**

- Área interna da caixa onde fica o texto, imagens, etc.
- Controlado pelas propriedades `width` (largura) e `height` (altura)
- Por padrão, elementos de bloco ocupam 100% da largura disponível
- Exemplo: `width: 200px; height: 150px;`

### 2. **Padding (Preenchimento)**

- Espaço entre o conteúdo e a borda
- Cria um "enchimento" interno da caixa
- Propriedade: `padding`
- **Sintaxe do atalho**:
  - `padding: 15px;` (todos os lados iguais)
  - `padding: 15px 0;` (cima/baixo: 15px, esquerda/direita: 0)
  - `padding: 15px 10px 5px 20px;` (topo, direita, baixo, esquerda - sentido horário)

### 3. **Border (Borda)**

- Linha ao redor da caixa
- Requer três propriedades para aparecer:
  - **Largura**: `border-width: 5px;`
  - **Estilo**: `border-style: solid;` (solid, dashed, dotted, etc.)
  - **Cor**: `border-color: black;`
- **Atalho**: `border: 5px solid black;`
- **Bordas específicas**: `border-top`, `border-right`, `border-bottom`, `border-left`

### 4. **Margin (Margem)**

- Espaço externo que empurra elementos para longe de outros elementos
- Área transparente
- Mesmo sistema de atalhos do padding
- **Colapso de margens**: Quando duas margens se encontram, apenas a maior é aplicada

## Box-Sizing: Mudando o Comportamento

### Padrão (content-box)

- `width` e `height` definem apenas o tamanho do conteúdo
- Padding e border são **adicionados** ao tamanho total

### Border-box (Recomendado)

```css
box-sizing: border-box;
```

- `width` e `height` incluem conteúdo + padding + border
- Facilita cálculos e previsibilidade do layout
- **Reset comum**:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

## Propriedades Específicas por Lado

### Padrão de nomenclatura:

- `propriedade-top` (topo)
- `propriedade-right` (direita)
- `propriedade-bottom` (baixo)
- `propriedade-left` (esquerda)

### Exemplos:

```css
padding-top: 10px;
margin-left: 20px;
border-bottom: 3px solid red;
```

## Dicas Práticas

### Reset CSS básico:

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
```

### Visualização no DevTools:

- Clique com botão direito → Inspecionar
- Na aba "Computed" você pode ver o Box Model visual
- Mostra as dimensões exatas de cada componente

### Unidades de medida comuns:

- `px` (pixels) - valor fixo
- `%` (porcentagem) - relativo ao elemento pai
- `em` - relativo ao tamanho da fonte
- `rem` - relativo ao tamanho da fonte raiz

## Conceitos Importantes

- **Elementos de bloco** ocupam toda a largura disponível por padrão
- **Backgrounds** (cores e imagens) se estendem até a borda, incluindo o padding
- **Margens negativas** podem ser usadas para sobreposição de elementos
- **Box-sizing: border-box** é considerado boa prática moderna no desenvolvimento web
