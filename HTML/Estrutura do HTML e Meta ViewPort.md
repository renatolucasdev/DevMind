# Estrutura HTML e Meta ViewPort

## 1. Estrutura Básica do Documento HTML

### Criação Rápida no VS Code

- **Atalho**: Digite `!` + Enter para gerar estrutura HTML5 automaticamente
- **Vantagem**: Cria documento completo com estrutura padrão
- **Configuração**: Ajustar idioma de `en` para `pt-BR` caso seja necessário

### Características do HTML5

- **Case Insensitive**: Não diferencia maiúsculas de minúsculas
- **Estrutura padrão**: `<!DOCTYPE html>`, `<html>`, `<head>`, `<body>`
- **Charset**: UTF-8 para suporte a caracteres especiais

## 2. Tags com Corpo vs Tags sem Corpo

### Tags com Corpo (Container)

- **Definição**: Necessitam de abertura e fechamento
- **Exemplos**: `<h1></h1>`, `<p></p>`, `<body></body>`
- **Regra**: Sempre fechar na ordem correta (hierarquia)
- **Conteúdo**: Podem conter texto e outras tags

### Tags sem Corpo (Self-closing)

- **Definição**: Não necessitam fechamento
- **Exemplos**: `<br>`, `<img>`, `<hr>`
- **Função**: Executam ação específica sem conteúdo interno

## 3. Hierarquia e Estrutura de Tags

### Conceito Pai-Filho

- **Regra**: Tags filhas devem ser fechadas antes das tags pai
- **Exemplo correto**: `<body><p>texto</p></body>`
- **Exemplo incorreto**: `<body><p>texto</body></p>`
- **Importância**: Mantém estrutura válida do documento

### Aninhamento Correto

- Sempre respeitar a ordem de fechamento
- Tags internas fecham antes das externas
- Indentação ajuda na visualização da hierarquia

## 4. Tags Básicas Apresentadas

### `<h1>` - Cabeçalho Principal

- **Função**: Título principal da página
- **Uso**: Conteúdo de destaque
- **Exemplo**: `<h1>Meu HTML</h1>`

### `<p>` - Parágrafo

- **Função**: Texto em parágrafo
- **Uso**: Conteúdo textual principal
- **Dica**: Use Lorem Ipsum para texto de exemplo

### `<span>` - Elemento Inline

- **Função**: Formatação de texto inline
- **Característica**: Não quebra linha automaticamente
- **Uso**: Aplicar estilos específicos em partes do texto

### `<br>` - Quebra de Linha

- **Função**: Força quebra de linha
- **Tipo**: Tag sem corpo
- **Uso**: Separar conteúdo em linhas diferentes

## 5. Meta Tag Viewport

### Origem e Propósito

- **Criada por**: Apple para Safari
- **Finalidade**: Controlar exibição em dispositivos móveis
- **Suporte**: Aceita pela maioria dos navegadores modernos

### Funcionamento

- **Problema**: Browsers móveis usam viewport virtual maior que a tela
- **Solução**: `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- **Resultado**: Página se ajusta à largura real do dispositivo

### Parâmetros Importantes

- `width=device-width`: Largura igual à do dispositivo
- `initial-scale=1.0`: Zoom inicial de 100%
- **Benefício**: Elimina necessidade de zoom/scroll horizontal

## 6. Boas Práticas de Desenvolvimento

### Organização de Arquivos

- Criar um arquivo HTML por aula/exercício
- Manter estrutura consistente
- Usar nomes descritivos para arquivos

### Configuração Inicial

- Sempre ajustar idioma (`lang="pt-BR"`)
- Incluir charset UTF-8
- Adicionar meta viewport para responsividade
- Definir título descritivo

### Estruturação de Código

- Usar indentação consistente
- Fechar tags na ordem correta
- Comentar código quando necessário
- Testar em diferentes dispositivos

## 7. Ferramentas de Desenvolvimento

### VS Code

- **Emmet**: Atalhos para criação rápida de HTML
- **Preview**: Visualização em tempo real
- **Extensions**: Plugins para produtividade
- **Lorem**: Para criar textos Lorem Ipsum dentro de tags para testar

### DevTools do Chrome

- **Device Toggle**: Simular dispositivos móveis
- **Responsive Design**: Testar diferentes resoluções
- **Inspector**: Analisar estrutura HTML
