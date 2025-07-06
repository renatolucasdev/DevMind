## **Separando HTML e CSS em arquivos diferentes**

### **1. CSS Interno (Tag `<style>`)**

- Utiliza a tag `<style>` dentro do documento HTML
- Pode ser colocada em qualquer lugar do documento (mais comum no `<head>`)
- Exemplo: seletor de classe `.caixa { width: 120px; height: 120px; }`

### **2. CSS Inline (Atributo `style`)**

- Aplicado diretamente no elemento HTML através do atributo `style`
- Exemplo: `<div style="width: 120px; height: 120px;"></div>`

### **3. CSS Externo (Arquivo Separado)**

- **Método mais recomendado** para projetos maiores
- Mantém separação entre estrutura (HTML) e apresentação (CSS)

## **Estrutura de Pastas Recomendada**

```
projeto/
├── index.html
└── assets/
    ├── css/
    │   └── estilos.css
    ├── js/
    │   └── (arquivos JavaScript)
    └── img/
        └── (imagens)
```

## **Linkando CSS Externo**

### **Sintaxe da Tag `<link>`**

```html
<link rel="stylesheet" href="caminho/para/arquivo.css">
```

### **Caminhos Relativos**

- **Caminho simples**: `assets/css/estilos.css`
- **Caminho explícito**: `./assets/css/estilos.css`
- O ponto (`./`) indica "pasta atual"

## **Múltiplos Arquivos CSS**

### **Ordem de Importação**

- **Regra fundamental**: O último CSS carregado tem prioridade
- Arquivos linkados posteriormente sobrescrevem regras anteriores
- Importante para controlar qual estilo será aplicado

### **Exemplo de Múltiplos Links**

```html
<link rel="stylesheet" href="assets/css/base.css">
<link rel="stylesheet" href="assets/css/layout.css">
<!-- layout.css terá prioridade sobre base.css -->
```

## **Boas Práticas**

### **Seletores CSS**

- **Prefira sempre classes** (`.classe`) em vez de IDs (`#id`) ou tags
- Classes oferecem maior flexibilidade e reutilização
- Evitam problemas de especificidade CSS

### **Organização**

- Mantenha CSS separado do HTML para melhor manutenção
- Use estrutura de pastas organizada
- Considere ferramentas como Webpack para projetos grandes

## **Vantagens do CSS Externo**

1. **Manutenção**: Facilita edição e organização do código
2. **Reutilização**: Mesmo CSS pode ser usado em múltiplas páginas
3. **Performance**: Arquivo CSS pode ser cacheado pelo navegador
4. **Separação de responsabilidades**: HTML para estrutura, CSS para estilo

## **Considerações de Performance**

- Navegadores preferem **uma requisição grande** a várias pequenas
- Ferramentas de build (como Webpack) podem concatenar múltiplos arquivos CSS
- Cache do navegador melhora carregamento em visitas subsequentes

Este resumo fornece uma base sólida para revisar os conceitos de separação HTML/CSS e organização de projetos web.
