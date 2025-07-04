# Atributos HTML - ID e Class

## 1. Anatomia das Tags HTML

- **Estrutura básica**: `<tag>conteúdo</tag>`
- **Regra fundamental**: Sempre fechar as tags na ordem correta
- **Hierarquia**: Tags filhas devem ser fechadas antes das tags pai
- **Erro comum**: Fechar tags fora de ordem quebra o layout

## 2. Atributos HTML - Conceitos Gerais

- **Definição**: Propriedades adicionais que podem ser aplicadas às tags
- **Localização**: Sempre na tag de abertura
- **Sintaxe**: `<tag atributo="valor">conteúdo</tag>`
- **Recomendação**: Sempre usar aspas duplas para valores de atributos

## 3. Atributo ID

### Características:

- **Unicidade**: Cada ID deve ser único na página
- **Sintaxe**: `<tag id="identificador">conteúdo</tag>`
- **Convenção de nomenclatura**:
  - Usar letras minúsculas
  - Separar palavras com hífen (-)
  - Evitar acentos e caracteres especiais
  - Exemplo: `id="cabecalho-principal"`

### Uso prático:

- Identificar elementos específicos
- Seleção no CSS: `#nome-do-id { propriedades }`
- Seleção no JavaScript para manipulação
- Alta especificidade no CSS

## 4. Atributo Class

### Características:

- **Reutilização**: Podem ser repetidas em múltiplos elementos
- **Múltiplas classes**: Um elemento pode ter várias classes
- **Sintaxe**: `<tag class="nome-da-classe">conteúdo</tag>`
- **Múltiplas classes**: `<tag class="classe1 classe2">conteúdo</tag>`

### Uso prático:

- Agrupar elementos com estilos similares
- Seleção no CSS: `.nome-da-classe { propriedades }`
- Mais flexível que ID para estilização
- Especificidade menor que ID no CSS

## 5. Seletores CSS Básicos

### Tipos de seletores:

1. **Por tag**: `h1 { background: red; }`
2. **Por ID**: `#cabecalho-1 { background: purple; }`
3. **Por classe**: `.fundo-vermelho { background: red; }`

### Especificidade CSS:

- **Ordem de prioridade**: ID > Classe > Tag
- **Regra da cascata**: Último estilo declarado prevalece (mesma especificidade)
- **!important**: Força aplicação do estilo (não recomendado)

## 6. Boas Práticas

### Nomenclatura:

- Use nomes descritivos e semânticos
- Evite nomes baseados em aparência visual
- Prefira hífen (-) para separar palavras
- Mantenha consistência no projeto

### Quando usar cada um:

- **ID**: Para elementos únicos e específicos
- **Class**: Para grupos de elementos com características similares
- **Tag**: Para estilos globais aplicados a todos os elementos do tipo

### Recomendações gerais:

- Prefira classes para estilização
- Use IDs apenas quando necessário
- Evite uso excessivo de !important
- Mantenha a estrutura HTML semântica

## 7. Exemplo Prático

```html
<!-- Estrutura HTML -->
<h1 id="titulo-principal" class="destaque fundo-azul">Título Principal</h1>
<h2 id="subtitulo-1" class="destaque">Subtítulo 1</h2>
<p class="texto-comum">Parágrafo comum</p>

<!-- CSS correspondente -->
<style>
  #titulo-principal { font-size: 2em; }
  .destaque { font-weight: bold; }
  .fundo-azul { background-color: blue; }
  .texto-comum { color: gray; }
</style>
```

## 8. Dicas para Revisão Ativa

- **Pratique digitando**: Não copie e cole código, digite para memorizar
- **Teste variações**: Experimente diferentes combinações de ID e classes
- **Valide o HTML**: Verifique se todas as tags estão fechadas corretamente
- **Experimente seletores**: Teste diferentes tipos de seletores CSS
- **Observe a especificidade**: Entenda por que alguns estilos sobrescrevem outros
