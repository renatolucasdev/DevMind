# Tags HTML para Textos

## 1. Conceitos Fundamentais

### Display Block vs Inline

- **Block**: Ocupa largura total disponível, quebra linha automaticamente
  - Exemplos: `<h1>`, `<p>`, `<div>`
- **Inline**: Ocupa apenas o espaço necessário, não quebra linha
  - Exemplos: `<span>`, `<a>`, `<strong>`

### Semântica vs Física

- **Tags Semânticas**: Carregam significado (melhor para SEO e acessibilidade)
- **Tags Físicas**: Apenas aparência visual

## 2. Tags de Formatação de Texto

### Negrito

| Tag        | Tipo      | Uso                         | Exemplo                     |
| ---------- | --------- | --------------------------- | --------------------------- |
| `<strong>` | Semântica | Texto com importância/força | `<strong>Cuidado!</strong>` |
| `<b>`      | Física    | Apenas visual bold          | `<b>Texto negrito</b>`      |

### Itálico

| Tag    | Tipo      | Uso                   | Exemplo                     |
| ------ | --------- | --------------------- | --------------------------- |
| `<em>` | Semântica | Dar ênfase            | `<em>Eu amo</em> sanduíche` |
| `<i>`  | Física    | Apenas visual itálico | `<i>Texto itálico</i>`      |

### Outras Formatações

- `<small>`: Texto menor
- `<sup>`: Texto sobrescrito (ex: 2²)
- `<sub>`: Texto subscrito (ex: H₂O)
- `<del>`: Texto riscado (semântico - indica remoção)
- `<s>`: Texto riscado (físico - apenas visual)
- `<ins>`: Texto inserido (semântico - indica adição)
- `<u>`: Texto sublinhado (físico)

## 3. Links e Referências

### Tag `<a>` (Anchor)

```html
<a href="https://example.com" target="_blank" rel="noopener">
  Texto do link
</a>
```

- **href**: URL de destino
- **target="_blank"**: Abre em nova aba
- **rel**: Define relacionamento (ex: noopener, nofollow)

### Citações

- `<q>`: Citação inline (dentro do parágrafo)

- `<blockquote>`: Bloco de citação (elemento próprio)
  
  ```html
  <blockquote cite="https://fonte.com">  Texto da citação longa</blockquote>
  ```

## 4. Imagens

### Tag `<img>`

```html
<img src="caminho/imagem.jpg" alt="Descrição da imagem" width="50" height="44">
```

- **src**: Caminho da imagem
- **alt**: Texto alternativo (obrigatório para acessibilidade)
- **width/height**: Dimensões (preferível usar CSS)

### Imagem como Link

```html
<a href="https://example.com">
  <img src="imagem.jpg" alt="Descrição">
</a>
```

## 5. Estrutura e Quebras

### Quebras e Separações

- `<br>`: Quebra de linha simples
- `<hr>`: Linha horizontal separadora

### Código

- `<code>`: Código inline (fonte monoespaçada)

- `<pre>`: Texto pré-formatado (preserva espaços e quebras)
  
  ```html
  <pre>  <code>    function exemplo() {      console.log("Olá mundo!");    }  </code></pre>
  ```

## 6. Containers Genéricos

### `<span>` (Inline)

- Container genérico para texto
- Não quebra linha
- Usado para aplicar estilos específicos

```html
<p>Texto normal <span class="destaque">texto destacado</span> mais texto</p>
```

### `<div>` (Block)

- Container genérico de bloco
- Quebra linha automaticamente
- Usado para agrupamento e layout

```html
<div class="secao">
  <p>Conteúdo da seção</p>
</div>
```

## 7. Boas Práticas

### Acessibilidade

- Sempre use `alt` em imagens
- Prefira tags semânticas (`<strong>` ao invés de `<b>`)
- Use `<em>` para ênfase real, não apenas visual

### SEO

- Use `rel="noopener"` em links externos
- Considere `rel="nofollow"` para links patrocinados
- Estruture o conteúdo semanticamente

### Organização

- Evite inline styles, prefira CSS externo
- Use classes para reutilização de estilos
- Valide seu HTML regularmente

## 8. Pontos de Atenção

### Hierarquia de Elementos

- Elementos block não podem ir dentro de elementos inline
- `<p>` não pode conter outros elementos block
- `<div>` pode conter qualquer elemento

### Compatibilidade

- Atributos `width` e `height` em imagens são válidos mas preferível CSS
- Tags físicas ainda são válidas, mas semânticas são recomendadas

## 9. Checklist de Revisão

- [ ] Usei tags semânticas quando possível?
- [ ] Todas as imagens têm atributo `alt`?
- [ ] Links externos têm `rel` apropriado?
- [ ] Código está dentro de `<pre><code>`?
- [ ] Hierarquia de elementos está correta?
- [ ] HTML foi validado?

## 10. Recursos Adicionais

Para aprofundar seus conhecimentos:

- MDN Web Docs (Mozilla Developer Network)
- W3C HTML Validator
- Google Web Fundamentals
- Guias de acessibilidade WCAG
