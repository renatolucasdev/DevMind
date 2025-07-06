# Tabelas HTML

## 1. Conceitos Fundamentais

### Estrutura Básica

- **Tag principal**: `<table>` - contém toda a estrutura da tabela
- **Organização**: Baseada em linhas e colunas, similar a planilhas
- **Uso histórico**: Antigamente utilizadas para layout completo de sites (prática obsoleta)

### Componentes Estruturais

- **`<thead>`** - Cabeçalho da tabela (opcional, mas recomendado)
- **`<tbody>`** - Corpo principal da tabela
- **`<tfoot>`** - Rodapé da tabela (opcional)

## 2. Elementos de Linha e Célula

### Linhas

- **`<tr>`** (table row) - Define cada linha da tabela
- Deve manter consistência no número de colunas

### Células

- **`<th>`** (table header) - Células de cabeçalho
  - Texto centralizado e em negrito por padrão
  - Usadas no `<thead>`
- **`<td>`** (table data) - Células de dados
  - Texto alinhado à esquerda por padrão
  - Usadas no `<tbody>` e `<tfoot>`

## 3. Elementos Complementares

### Caption

- **`<caption>`** - Legenda/descrição da tabela
- Posicionamento: `caption-side: top/bottom`
- Estilização personalizada com CSS

## 4. Expansão de Células

### Colspan

- **`colspan="n"`** - Faz uma célula ocupar N colunas
- Reduz o número de `<td>` na linha proporcionalmente
- Exemplo: `<td colspan="2">Conteúdo</td>`

### Rowspan

- **`rowspan="n"`** - Faz uma célula ocupar N linhas
- Remove células das linhas subsequentes
- Exemplo: `<td rowspan="3">Conteúdo</td>`

## 5. Estilização com CSS

### Bordas e Espaçamento

```css
table, td, th {
  border: 1px solid #ccc;
  border-collapse: collapse; /* Une as bordas */
  padding: 8px; /* Espaçamento interno */
}
```

### Alinhamento

```css
th {
  text-align: left; /* Alinha cabeçalhos à esquerda */
}

td {
  text-align: center; /* Centraliza conteúdo das células */
}
```

### Diferenciação de Seções

```css
tfoot td {
  background-color: #666;
  font-style: italic;
}
```

## 6. Responsividade

### Problema

- Tabelas largas quebram o layout em dispositivos móveis
- Conteúdo pode ficar cortado ou forçar scroll horizontal

### Solução - Wrapper com Scroll

```html
<div class="table-responsive">
  <table>
    <!-- conteúdo da tabela -->
  </table>
</div>
```

```css
.table-responsive {
  width: 100%;
  max-width: 100vw;
  overflow-x: auto;
}

table {
  width: 800px; /* Largura fixa maior que mobile */
}
```

## 7. Boas Práticas

### Estrutura Semântica

- Sempre use `<thead>`, `<tbody>` e `<tfoot>` quando apropriado
- Mantenha consistência no número de colunas
- Use `<th>` para cabeçalhos e `<td>` para dados

### Acessibilidade

- Forneça `<caption>` para descrever o conteúdo da tabela
- Use `scope` attribute em headers complexos
- Considere `<th>` com `scope="col"` ou `scope="row"`

### Performance

- Evite tabelas aninhadas desnecessárias
- Use CSS para estilização, não atributos HTML obsoletos
- Considere alternativas como CSS Grid/Flexbox para layouts

## 8. Exemplo Completo

```html
<table>
  <caption>Vendas do Trimestre</caption>
  <thead>
    <tr>
      <th>Produto</th>
      <th>Quantidade</th>
      <th>Preço</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Produto A</td>
      <td>10</td>
      <td>R$ 100,00</td>
    </tr>
    <tr>
      <td colspan="2">Total</td>
      <td>R$ 1.000,00</td>
    </tr>
  </tbody>
</table>
```

## 9. Pontos de Atenção

- **Não use tabelas para layout** - Use CSS Grid ou Flexbox
- **Sempre teste a responsividade** em diferentes dispositivos
- **Considere alternativas** como listas ou cards para dados simples
- **Valide a estrutura** - cada linha deve ter o mesmo número de colunas (considerando colspan/rowspan)
