# Módulo Operações do EF Core

Este módulo abrange as operações fundamentais com o Entity Framework Core (EF Core), fechando o ciclo básico de conhecimento deste ORM. Serão abordadas as técnicas para inserir, consultar, atualizar e remover registros, além de recursos avançados como inserção em massa, carregamento de entidades relacionadas e o comportamento do rastreamento (tracking) em consultas.

---

## 1. Inserção de Registros

### 1.1. Configuração do Contexto
- No *ApplicationContext* são expostas as propriedades do tipo `DbSet<T>`, que representam as entidades como:
  - **Pedidos**
  - **Produtos**
  - **Clientes**

### 1.2. Formas de Inserção
O EF Core permite inserir registros utilizando diferentes abordagens:

1. **Inserção via Propriedade DbSet**
   - Utiliza os métodos `Add()` e `AddRange()`.  
   
	```csharp
	context.Produtos.Add(produto);
	context.Produtos.AddRange(listaDeProdutos)
	```

2.  **Inserção com Método Genérico**
    
    -   Através do método `Set<T>()` do contexto.
     
	```csharp
	context.Set<Produto>().Add(produto);  
	```
    
3.  **Forçando o Rastreamento com** `Entry()`
    
    -   Anexa uma entidade de forma explícita e define seu estado para `Added`.
        
    ```csharp
    var entry = context.Entry(produto);
    entry.State = EntityState.Added;
    ```
    
4.  **Utilizando a Propriedade** `State` **Diretamente**
    
    -   Configura o estado da entidade via `context.Entry(produto).State = EntityState.Added;`.
        

> **Observação:** Embora existam várias alternativas, as duas primeiras (usando o DbSet ou o método genérico) são geralmente as mais eficientes e diretas, pois evitam sobrecarga desnecessária.

### 1.3. Persistindo as Alterações

-   Após inserir registros, é necessário chamar o método `SaveChanges()` para que as alterações rastreadas em memória sejam persistidas no banco de dados.
   
    ```csharp
    int registrosAfetados = context.SaveChanges();
    Console.WriteLine($"{registrosAfetados} registros afetados.");
    ```
    

## 2. Consultas e Carregamento de Dados Relacionados

### 2.1. Carregamento de Propriedades de Navegação

No EF Core, entidades relacionadas podem ser carregadas de três maneiras:

1.  **Carregamento Adiantado (Eager Loading)**
    
    -   Utiliza o método `Include()` (e `ThenInclude()` para níveis aninhados) para buscar os dados relacionados em uma única consulta.
            
    ```csharp
    var pedidos = context.Pedidos
        .Include(p => p.Itens)
        .ThenInclude(i => i.Produto)
        .ToList();    
    ```
    
2.  **Carregamento Explícito**
    
    -   Carrega os dados relacionados em um momento posterior, utilizando o método `Load()`.
        
    ```csharp
    context.Entry(pedido).Collection(p => p.Itens).Load();
    ```
    
3.  **Carregamento Lento (Lazy Loading)**
    
    -   Os dados são carregados sob demanda ao acessar a propriedade de navegação. (Requer configuração adicional, como proxies.)
        

### 2.2. Consultando Dados com LINQ

O EF Core suporta dois estilos para realizar consultas:

-   **Consulta por Sintaxe de Consulta (Query Syntax)**
    
    ```csharp
    var consulta = from c in context.Clientes
                   where c.Id > 0
                   select c;
    
    ```
-   **Consulta por Métodos (Method Syntax)**
    
    
    
    ```csharp
    var consulta = context.Clientes
        .Where(c => c.Id > 0)
        .ToList();
    ```

### 2.3. Tracking e Desabilitando Rastreamento (No-Tracking)

-   Por padrão, o EF Core rastreia os objetos materializados, o que permite que alterações sejam automaticamente detectadas.
    
-   Para consultas onde não é necessário rastrear os resultados, pode-se utilizar o método `AsNoTracking()`.

    ```csharp
    var clientes = context.Clientes
        .AsNoTracking()
        .Where(c => c.Id > 0)
        .ToList();
    ```
    
-   O método `Find()` prioriza verificar os objetos em memória antes de fazer uma consulta ao banco de dados.
    

## 3. Atualização de Registros

### 3.1. Atualização em Entidades Rastreadas

-   Ao carregar um registro, modificar seus valores e chamar `SaveChanges()`, o EF Core atualiza somente os campos alterados.
    
    ```csharp
    var cliente = context.Clientes.Find(1);
    cliente.Nome = "Cliente Alterado";
    context.SaveChanges();
    ```
    
### 3.2. Cenário Desconectado

-   Em aplicações (como APIs) onde os dados vêm desconectados, cria-se uma instância com as alterações desejadas e utiliza-se o método `Entry()` para especificar quais propriedades foram modificadas.
    
    ```csharp
    var cliente = new Cliente { Id = 1, Nome = "Novo Nome" };
    context.Entry(cliente).Property(c => c.Nome).IsModified = true;
    context.SaveChanges();
    ``` 
> **Dica:** Evite usar o método `Update()` indiscriminadamente, pois ele força a atualização de todas as propriedades, mesmo as que não foram modificadas.

## 4. Remoção de Registros

### 4.1. Métodos de Remoção

Para remover um registro, o EF Core oferece várias opções:

1.  **Usando o DbSet.Remove()**
    
    ```csharp
    var cliente = context.Clientes.Find(2);
    context.Clientes.Remove(cliente);
    context.SaveChanges();
    ```
    
2.  **Diretamente pelo Contexto**
    
    ```csharp
    var cliente = context.Clientes.Find(2);
    context.Remove(cliente);
    context.SaveChanges();
    ```
    
3.  **Definindo o Estado da Entidade**
    
    ```csharp
    var cliente = context.Clientes.Find(2);
    context.Entry(cliente).State = EntityState.Deleted;
    context.SaveChanges();
    ```
    

### 4.2. Abordagem para Cenário Desconectado

-   Se o registro a ser removido não está carregado, basta instanciar uma entidade com o ID desejado e removê-la.
       
    ```csharp
    var cliente = new Cliente { Id = 3 };
    context.Remove(cliente);
    context.SaveChanges();
    ```

## 5. Inserção em Massa e Recursos Avançados

### 5.1. Inserção em Massa

-   A partir de versões mais recentes, o EF Core passou a permitir a inserção de registros em massa, evitando múltiplas interações separadas com o banco de dados.
    
-   Utilizando o método `AddRange()` pode-se persistir uma lista de entidades de uma só vez:
    
    ```csharp
    context.AddRange(listaDeProdutos, listaDeClientes);
    context.SaveChanges();
    ```
-   Esta abordagem melhora a **performance**, pois agrupa as operações em uma única instrução SQL.
    

### 5.2. Configuração de Log para Monitoramento

-   É possível configurar o _logging_ no EF Core para acompanhar os comandos SQL gerados. Isso é feito no método `OnConfiguring()` do _ApplicationContext_:
    
    ```csharp
    protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder)
    {
        var logFactory = LoggerFactory.Create(builder =>
        {
            builder.AddConsole();
        });
        optionsBuilder
            .UseLoggerFactory(logFactory)
            .EnableSensitiveDataLogging();
    }
   
    ```
    
-   O `EnableSensitiveDataLogging()` permite visualizar os valores dos parâmetros nas instruções SQL, o que é útil para depuração.
    

### 5.3. Consultas Avançadas

-   Além dos métodos básicos de consulta, o EF Core suporta:
    
    -   **Ordenação:** Utilização de `OrderBy()`
        
     ```csharp
       var clientesOrdenados = context.Clientes
           .OrderBy(c => c.Nome)
           .ToList();
        
    ```
        
    -   **Rastreamento e Não Rastreamento:**
        
        -   `Find()` para buscar com preferência aos objetos em memória.
            
        -   `AsNoTracking()` para otimizar consultas retornando somente os dados.
            

 **Exemplo de Uso do Find:**  
```csharp 
var cliente = context.Clientes.Find(1); 
``` 
-  Se o objeto já estiver em memória, o EF Core o retorna sem fazer nova consulta ao banco.

## Considerações Finais

-   O EF Core oferece um arsenal de ferramentas para **manipulação eficiente do banco de dados**:
    
    -   **Inserção:** Diversas formas de adicionar dados (inclusão de instâncias únicas ou em massa).
        
    -   **Consulta:** Diferentes estratégias para carregar entidades e seus relacionamentos, com controle sofisticado de _tracking_.
        
    -   **Atualização e Remoção:** Métodos que permitem atualizar apenas os campos modificados e remover registros de forma segura, inclusive em cenários desconectados.
        
-   **Boas Práticas:**
    
    -   Prefira utilizar os métodos que mantêm o código limpo e legível (como `Add()` e `AddRange()` para inserção).
        
    -   Utilize as configurações de log para depurar e monitorar as operações SQL, especialmente em ambientes de desenvolvimento.
        
    -   Em cenários de alta performance, explore as técnicas de inserção em massa e desative o rastreamento onde não é necessário (com `AsNoTracking()`).
        

Este resumo integra as principais funcionalidades e práticas do EF Core para operações de **inserção**, **consulta**, **atualização** e **remoção**, enfatizando também os recursos avançados que ajudam a otimizar e depurar a interação com o banco de dados.

---
Fontes: Curso Introdução ao Entity Framework Core - Módulo Operações- Desenvolvedor.io
