# Semântica na Estrutura do HTML5

## 1. Evolução da Estruturação HTML

### Antes do HTML5:

- Uso excessivo de `<div>` para organizar conteúdo
- Estruturação com tabelas (prática inadequada)
- Falta de elementos semânticos específicos
- Exemplo: `<div id="menu">`, `<div id="content">`, `<div id="footer">`

### Com HTML5:

- Criação de tags semânticas específicas
- Melhor estruturação e significado do conteúdo
- Maior acessibilidade e compreensão por leitores de tela
- Melhor indexação pelos mecanismos de busca

## 2. Principais Tags Semânticas do HTML5

### `<header>`

- Define o cabeçalho da página ou seção
- Pode conter logo, título principal, navegação
- Pode ser usado múltiplas vezes na página
- Exemplo: cabeçalho do site, cabeçalho de artigo

### `<nav>`

- Define área de navegação
- Contém links de navegação principal
- Geralmente usado com listas (`<ul>`, `<li>`)
- Pode aparecer em sidebars, menus principais

### `<main>`

- Define o conteúdo principal da página
- **Importante**: Apenas UM `<main>` por página
- Não pode ser descendente de `<article>`, `<aside>`, `<header>`, `<footer>`, `<nav>`, `<section>`
- Representa o foco central do documento

### `<section>`

- Define seções genéricas do documento
- Usado quando não há tag semântica específica
- Geralmente contém um cabeçalho (`<h1>` a `<h6>`)
- Pode ser repetida múltiplas vezes

### `<article>`

- Define conteúdo independente e reutilizável
- Ideal para: posts de blog, produtos, comentários
- Pode ser repetido na página
- Deve fazer sentido isoladamente

### `<aside>`

- Define conteúdo relacionado mas secundário
- Usado para: sidebars, informações complementares
- Pode conter navegação secundária
- Relacionado ao conteúdo principal mas não essencial

### `<footer>`

- Define rodapé da página ou seção
- Relacionado ao elemento pai mais próximo
- Pode conter: informações de contato, copyright, links
- Pode ser usado múltiplas vezes

### `<address>`

- Define informações de contato
- Usado para endereços de empresas ou autores
- Específico para dados de localização/contato

## 3. Hierarquia de Cabeçalhos

### Boas Práticas:

- `<h1>`: Título principal da página (único)
- `<h2>` a `<h6>`: Subtítulos em ordem hierárquica
- Cada `<section>` e `<article>` deve ter um cabeçalho
- Validadores HTML alertam sobre seções sem cabeçalho

### Exemplo de Estrutura:

```html
<h1>Título Principal do Site</h1>
<section>
    <h2>Seção Principal</h2>
    <article>
        <h3>Artigo Individual</h3>
    </article>
</section>
```

## 4. Exemplo de Estrutura Semântica Completa

```html
<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <title>Loja Online</title>
</head>
<body>
    <header>
        <h1>Nome da Loja</h1>
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#produtos">Produtos</a></li>
                <li><a href="#contato">Contato</a></li>
            </ul>
        </nav>
    </header>

    <main>
        <section>
            <h2>Roupas Femininas</h2>
            <article>
                <h3>Produto 1</h3>
                <p>Descrição do produto...</p>
            </article>
        </section>

        <section>
            <h2>Roupas Masculinas</h2>
            <article>
                <h3>Produto 2</h3>
                <p>Descrição do produto...</p>
            </article>
        </section>
    </main>

    <aside>
        <h3>Links Úteis</h3>
        <nav>
            <ul>
                <li><a href="#ofertas">Ofertas</a></li>
                <li><a href="#novidades">Novidades</a></li>
            </ul>
        </nav>
    </aside>

    <footer>
        <address>
            <p>Endereço: Rua das Flores, 123</p>
            <p>Telefone: (11) 1234-5678</p>
        </address>
    </footer>
</body>
</html>
```

## 5. Benefícios da Semântica HTML5

### Acessibilidade:

- Leitores de tela compreendem melhor a estrutura
- Navegação mais fácil para usuários com deficiências
- Melhor experiência para tecnologias assistivas

### SEO (Search Engine Optimization):

- Mecanismos de busca entendem melhor o conteúdo
- Melhor indexação e ranqueamento
- Estrutura clara para crawlers

### Manutenibilidade:

- Código mais limpo e organizador
- Mais fácil de entender por outros desenvolvedores
- Estrutura lógica e intuitiva

## 6. Ferramentas de Validação e Teste

### Validação HTML:

- Usar validadores HTML (W3C Markup Validator)
- Verificar se todas as tags estão fechadas corretamente
- Validar estrutura semântica

### Testes de Acessibilidade:

- Extensões como ChromeVox
- Testadores de leitores de tela
- Verificar navegação por teclado

## 7. Dicas Importantes

### ❌ Evitar:

- Usar `<div>` quando existe tag semântica específica
- Múltiplos `<main>` na mesma página
- Seções sem cabeçalhos
- Estruturação apenas com `<div>` e `<span>`

### ✅ Fazer:

- Sempre validar o HTML
- Usar tags semânticas apropriadas
- Incluir cabeçalhos em seções e artigos
- Testar com leitores de tela
- Manter hierarquia lógica de cabeçalhos

## 8. Próximos Passos

- Estudar CSS para estilização visual
- Aprender sobre ARIA (Accessible Rich Internet Applications)
- Praticar com projetos reais
- Continuar estudando novas tags HTML5
- Testar regularmente a acessibilidade dos projetos
