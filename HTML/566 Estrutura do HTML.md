# Estrutura do HTML - Resumo para Revisão Ativa

## 1. Conceitos Fundamentais

### O que é HTML?

- **HTML** = arquivo de texto que o navegador usa para renderizar páginas
- Todos os sites do mundo utilizam HTML
- **Pirâmide web**: HTML + CSS + JavaScript = sites completos (ex: Facebook)
- HTML define a **semântica** e **estrutura** da página

### Extensão de Arquivos

- Arquivos HTML usam extensão `.html`
- Exemplo: `index.html`
- É um arquivo de texto puro (como .txt)
- Pode ser aberto em qualquer editor de texto

## 2. Tags HTML

### Estrutura de Tags

```html
<!-- Tag com corpo -->
<tagname>conteúdo</tagname>

<!-- Tag sem corpo (self-closing) -->
<tagname />
<!-- ou -->
<tagname>
```

### Características das Tags

- **Case insensitive**: `<HTML>` = `<html>` = `<Html>`
- **Tags com corpo**: têm conteúdo entre abertura e fechamento
- **Tags sem corpo**: são autocontidas
- **Hierarquia**: tags filhas devem ser fechadas antes das tags pais

### Atributos

```html
<!-- Atributo sem valor -->
<tag atributo>

<!-- Atributo com valor -->
<tag atributo="valor">

<!-- Múltiplos valores -->
<tag atributo="valor1 valor2">
```

## 3. Estrutura Padrão do Documento HTML

### Documento HTML Completo

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Meu HTML</title>
</head>
<body>
    <p>Conteúdo da página</p>
</body>
</html>
```

## 4. Elementos Obrigatórios e Recomendados

### DOCTYPE

- `<!DOCTYPE html>` - especifica HTML5
- **Obrigatório** para validação
- Não é uma tag HTML

### Tag `<html>`

- **Tag raiz** do documento
- Todas as outras tags são filhas dela
- **Atributo lang**: especifica idioma (`lang="pt-br"`)

### Tag `<head>`

- Contém **metadados** do documento
- Não aparece visualmente na página
- Informações para o navegador e motores de busca

### Tag `<title>`

- **Obrigatório** dentro de `<head>`
- Define o título da aba do navegador
- Importante para SEO

### Meta Charset

- `<meta charset="UTF-8">`
- Define **codificação de caracteres**
- **Recomendado** para evitar problemas com acentos
- UTF-8 é o padrão mais usado

### Tag `<body>`

- Contém todo o **conteúdo visível** da página
- **Recomendado** (tecnicamente não obrigatório)
- Tudo que o usuário vê fica aqui

## 5. Hierarquia e Indentação

### Regras de Hierarquia

- Tags filhas devem ser fechadas antes das tags pais
- **Incorreto**: `<pai><filho></pai></filho>`
- **Correto**: `<pai><filho></filho></pai>`

### Indentação

- Use espaços ou tabs para mostrar hierarquia
- Facilita leitura e manutenção do código
- Não afeta o funcionamento, mas é boa prática

## 6. Validação HTML

### W3C Validator

- Site oficial: validator.w3.org
- Verifica se o HTML está correto
- Mostra erros e warnings
- **W3C** = World Wide Web Consortium (cria especificações web)

### Tipos de Problemas

- **Erros**: código inválido que deve ser corrigido
- **Warnings**: avisos sobre boas práticas (ex: falta de `lang`)

## 7. Estrutura Mínima vs Recomendada

### Mínimo Obrigatório

```html
<!DOCTYPE html>
<html>
<head>
    <title>Título</title>
</head>
</html>
```

### Estrutura Recomendada

```html
<!DOCTYPE html>
<html lang="pt-br">
<head>
    <meta charset="UTF-8">
    <title>Título da Página</title>
</head>
<body>
    <!-- Conteúdo aqui -->
</body>
</html>
```

## 8. Dicas Importantes

### Navegador vs Código Correto

- Navegadores tentam **corrigir** HTML incorreto automaticamente
- **Nunca dependa** dessa correção automática
- Sempre escreva HTML válido desde o início

### Ferramentas de Desenvolvimento

- Use **Live Server** ou ferramentas similares
- Atualização automática ao salvar o arquivo
- Facilita o desenvolvimento

### Boas Práticas

- Sempre use a estrutura completa recomendada
- Valide seu HTML regularmente
- Use indentação consistente
- Especifique sempre o idioma da página

## Perguntas para Revisão Ativa

1. Qual a diferença entre uma tag com corpo e uma tag sem corpo?
2. Por que é importante usar o atributo `lang` na tag `<html>`?
3. Qual a função do `<meta charset="UTF-8">`?
4. O que acontece se você não fechar tags na ordem correta?
5. Quais elementos são obrigatórios vs recomendados em um documento HTML?
6. Como validar se seu HTML está correto?
