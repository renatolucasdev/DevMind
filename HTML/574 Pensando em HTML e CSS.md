## Pensando em HTML e CSS

### **1. Conceito Fundamental**

- **Websites são compostos por "caixas dentro de caixas"**
- Todos os elementos HTML são estruturalmente quadrados ou retangulares
- A construção de uma página web é como montar um "Lego" de containers

### **2. Elementos de Estrutura**

- **`<div>`**: Principal elemento de estrutura (container genérico)
- **`<header>`**: Cabeçalho da página
- **`<section>`**: Seções de conteúdo
- **Semântica**: Usar elementos apropriados para cada finalidade

### **3. Propriedades CSS Básicas**

- **`width`**: Define largura (ex: `width: 120px`)
- **`height`**: Define altura (ex: `height: 120px`)
- **`background-color`**: Define cor de fundo (ex: `background-color: red`)
- **`color`**: Define cor do texto

### **4. Unidades de Medida**

- **Pixels (px)**: Medida fixa e precisa
- **Porcentagem (%)**: Medida relativa ao elemento pai
- **Outras unidades**: em, rem, vh, vw (mencionadas para conhecimento)

### **5. Modelo de Caixa (Box Model)**

- **Margin**: Espaçamento externo do elemento
- **Padding**: Espaçamento interno do elemento
- **Border**: Borda do elemento
- **Content**: Conteúdo real do elemento

### **6. Reset CSS**

```css
* {
    margin: 0;
    padding: 0;
}
```

- Remove margens e padding padrão dos navegadores

### **7. Posicionamento com Flexbox**

- **`display: flex`**: Transforma container em flex
- **`justify-content: center`**: Centraliza conteúdo horizontalmente
- **`justify-content: space-between`**: Distribui elementos nas extremidades
- **Flexbox é mais moderno que `float`**

### **8. Cores em CSS**

- **Nomes**: `red`, `blue`, `yellow`
- **Hexadecimal**: `#FF0000`, `#00FF00`
- **RGB**: `rgb(255, 0, 0)`
- **RGBA**: `rgba(255, 0, 0, 0.5)` (com transparência)

### **9. Centralização de Elementos**

- **Margin auto**: `margin: 0 auto` (centraliza horizontalmente)
- **Flexbox**: `display: flex` + `justify-content: center`
- **Text-align**: `text-align: center` (para texto)

### **10. Propriedades de Texto**

- **`font-size`**: Tamanho da fonte
- **`font-family`**: Família da fonte
- **`text-decoration`**: Decoração do texto (`none` remove sublinhado)
- **`text-transform`**: Transformação do texto (`uppercase`)

### **11. Background e Imagens**

- **`background-image`**: Define imagem de fundo
- **`background-size`**: Controla tamanho da imagem (`cover`)
- **`background-position`**: Posiciona a imagem (`center top`)

### **12. Metodologia de Desenvolvimento**

1. **Analisar o layout** como caixas e containers
2. **Criar a estrutura HTML** com elementos semânticos
3. **Aplicar CSS** para estilização e posicionamento
4. **Testar e ajustar** responsividade

### **13. Dicas Importantes**

- **Inspecionar elementos** no navegador para entender estruturas
- **Começar sempre pela estrutura** antes da estilização
- **Usar classes CSS** para reutilização de estilos
- **Evitar estilos inline** quando possível

### **14. Exemplo Prático Abordado**

- Criação de um header similar ao Netflix
- Uso de containers para organização
- Aplicação de flexbox para alinhamento
- Implementação de logo e menu

### **💡 Próximos Passos Sugeridos**

- Estudar mais elementos HTML (formulários, tabelas, listas)
- Aprofundar em CSS Grid como alternativa ao Flexbox
- Praticar construindo layouts completos
- Explorar responsividade com media queries

Este resumo oferece uma base sólida para revisão ativa e prática dos conceitos apresentados na aula!
