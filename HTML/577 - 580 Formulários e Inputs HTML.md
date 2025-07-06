# Formulários e Inputs HTML

Segue um resumo em tópicos para facilitar a revisão ativa sobre **Formulários e Inputs em HTML**, com base nas transcrições fornecidas e complementos pontuais para clareza e atualização:

**Estrutura Básica de Formulários**

- Um formulário HTML é criado com a tag `<form>`, que serve para coletar dados do usuário e enviá-los para um servidor (back-end)1.

- Os principais atributos do `<form>` são:
  
  - **action**: define para onde os dados serão enviados.
  
  - **method**: especifica o método HTTP (GET ou POST) usado no envio.
  
  - **target**: determina onde a resposta será exibida (ex: `_blank` para nova aba).
  
  - **autocomplete**: controla o preenchimento automático dos campos pelo navegador1.

**Agrupamento e Semântica**

- Campos relacionados podem ser agrupados com `<fieldset>`, e uma legenda pode ser definida com `<legend>`, melhorando acessibilidade e organização1.

- Nunca se deve aninhar um `<form>` dentro de outro, pois isso pode causar problemas de funcionamento nos navegadores1.

- O uso correto de `<label>` vinculado aos inputs melhora a usabilidade e a acessibilidade, permitindo que o clique no texto selecione o campo correspondente2.

**Tipos de Inputs Comuns**

| Tipo de Input      | Atributo type  | Uso Principal                                  |
| ------------------ | -------------- | ---------------------------------------------- |
| Texto              | text           | Entrada livre de texto                         |
| Senha              | password       | Entrada de texto oculto (senha)3               |
| E-mail             | email          | Validação básica de formato de e-mail4         |
| Número             | number         | Apenas números, com opções de min, max e step4 |
| Data               | date           | Seleção de datas em calendário4                |
| Data e Hora        | datetime-local | Seleção de data e hora (depende do navegador)4 |
| Hora               | time           | Seleção apenas de horário4                     |
| Cor                | color          | Seletor de cor hexadecimal4                    |
| Arquivo            | file           | Upload de arquivos, com opção de múltiplos4    |
| Checkbox           | checkbox       | Seleção múltipla (marcar/desmarcar opções)2    |
| Radio              | radio          | Seleção única entre várias opções2             |
| Range (deslizante) | range          | Seleção de valor em uma faixa (ex: volume)3    |
| URL                | url            | Validação básica de formato de endereço3       |
| Busca              | search         | Campo de busca, com semântica específica3      |

**Atributos Importantes de Inputs**

- **id**: identificador único na página, usado para associar labels2.

- **name**: nome do campo, fundamental para o envio dos dados ao servidor2.

- **value**: valor padrão ou atual do campo2.

- **placeholder**: texto de exemplo exibido no campo até o usuário digitar algo2.

- **required**: torna o preenchimento obrigatório, com validação automática pelo navegador2.

- **disabled**: desabilita o campo, impedindo interação2.

- **readonly**: impede edição, mas permite seleção e envio do valor2.

- **checked**: define se um checkbox ou radio já vem marcado2.

- **multiple**: permite seleção de múltiplos arquivos ou opções (em `<input type="file">` e `<select>`)43.

- **accept**: restringe os tipos de arquivos aceitos em uploads4.

**Botões em Formulários**

- `<button type="submit">`: envia o formulário2.

- `<button type="reset">`: reseta todos os campos para o valor inicial2.

- `<button type="button">`: botão genérico, usado geralmente com JavaScript2.

**Elementos Especiais**

- `<select>`: cria uma lista suspensa de opções, podendo ter agrupamentos com `<optgroup>` e múltipla seleção com o atributo `multiple`3.

- `<textarea>`: campo de texto multilinha, com atributos para definir quantidade de linhas (rows) e colunas (cols)3.

**Validações e Usabilidade**

- Navegadores modernos já realizam validações básicas (ex: campos obrigatórios, formatos de e-mail e URL)4.

- Para validações mais robustas, recomenda-se o uso adicional de JavaScript e validação no servidor.

- Atributos como `min`, `max` e `step` ajudam a controlar os valores aceitos em inputs numéricos e de faixa43.

**Acessibilidade e Boas Práticas**

- Sempre utilize `<label>` associado ao campo correspondente para acessibilidade e melhor experiência do usuário2.

- Use agrupamentos semânticos (`<fieldset>`, `<legend>`) quando houver campos relacionados1.

- Prefira tipos de input específicos ao invés de apenas `<input type="text">`, pois isso ativa validações e controles nativos do navegador43.

*Complemento*: Para detalhes e exemplos práticos, consulte sempre a documentação oficial da [W3C](https://www.w3.org/) ou [MDN Web Docs](https://developer.mozilla.org/), que trazem tabelas completas de tipos de campos e atributos, além de recomendações de acessibilidade.

1. https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/73252786/017d6daa-0735-4726-9756-4da62d5adbae/Formularios-e-Inputs-HTML.txt
2. https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/73252786/773d92d3-88ee-4710-96be-c54ec30e4113/Formularios-e-Inputs-HTML-pt2.txt
3. https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/73252786/69c98b67-1f7b-4c44-836e-4264fefc1d70/Formularios-e-Inputs-HTML-pt4.txt
4. https://ppl-ai-file-upload.s3.amazonaws.com/web/direct-files/attachments/73252786/076d61ec-d79e-400a-872f-b8582e3dd958/Formularios-e-Inputs-HTML-pt3.txt
