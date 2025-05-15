
# Migrations (Introdução ao Entity Framework Core)

## 1. Conceito e Importância das Migrações

- **O que são migrações?**  
  Migrações são recursos essenciais do EF Core que permitem acompanhar e versionar as alterações feitas no modelo de dados da aplicação. Durante o desenvolvimento, o modelo sofre mudanças (como inclusão de novas entidades, colunas ou relacionamentos), e as migrações garantem que o banco de dados permaneça sincronizado com essas alterações.

- **Por que são essenciais?**  
  - **Evolução Contínua:** Permitem ajustes incrementais sem comprometer o funcionamento da aplicação.  
  - **Rollback Simplificado:** Possibilitam reverter alterações por meio do método `Down()`.  
  - **Sincronismo entre Modelo e Banco:** Mantêm a integridade e sincronia entre o código e o banco de dados.

---

## 2. Pacotes e Ferramentas Necessárias

- **Pacotes Principais:**  
  - `Microsoft.EntityFrameworkCore.Design`: Responsável por gerar arquivos de migração.  
  - `Microsoft.EntityFrameworkCore.Tools`: Fornece comandos para criar, aplicar e gerenciar migrações.

- **Instalação:**  
  - **.NET CLI:**  
    ```bash
    dotnet tool install --global dotnet-ef --version 3.1.5
    dotnet ef
    ```
  - **Visual Studio:**  
    Utilize o NuGet Package Manager para instalar os pacotes e a *Package Manager Console* (PMC) para executar os comandos do EF Core.

---

## 3. Criação e Estrutura dos Arquivos de Migração

- **Criando uma migração:**  
  - **Usando .NET CLI:**  
    ```bash
    dotnet ef migrations add PrimeiraMigracao -p <Caminho/Projeto> -o Migrations
    ```
  - **No Visual Studio (Package Manager Console):**  
    ```powershell
    Add-Migration PrimeiraMigracao -OutputDir Migrations
    ```

- **Arquivos Gerados:**  
  - **Arquivo de Migração:** Contém os métodos `Up()` e `Down()` para aplicar e reverter as alterações.  
  - **Arquivo de Design (Snapshot):** Mantém uma cópia do modelo de dados no momento da migração.  
  - **ApplicationContextModelSnapshot:** Representa o estado atual do modelo de dados e é atualizado a cada migração.

---

## 4. Comandos Essenciais e suas Equivalências no Visual Studio

### Geração de Migração  
- **CLI:**  

	``` bash
	dotnet ef migrations add NomeDaMigracao
    ```

-   **Visual Studio (PMC):**
    
    ```powershell
    Add-Migration NomeDaMigracao
    ```
    

### Aplicação da Migração

-   **CLI:**
  
    ``` bash
    dotnet ef database update -p <Caminho/Projeto>
    ```
    
-   **Visual Studio (PMC):**
     
    ```powershell
    Update-Database
    ```
    

### Removendo a Última Migração

-   **CLI:**
    
    ```bash
    dotnet ef migrations remove -p <Caminho/Projeto>
    ```
    
-   **Visual Studio (PMC):**
        
    ```powershell
    Remove-Migration
    ```
    Obs: caso o CLI esteja apontando para a raiz do projeto, não é necessário o argumento -p
---    

### Gerando Script SQL da Migração

-   **CLI:**
   
    ```bash
    dotnet ef migrations script -p <Caminho/Projeto> -o "script.sql"
    ```
    
    Para um script idempotente:
    
    ```bash
    dotnet ef migrations script -i -p <Caminho/Projeto> -o "script.sql"
    ```
    
-   **Visual Studio (PMC):**
   
    ```powershell
    Script-Migration -Output "script.sql" -Idempotent   
    ```
    

## 5. Aplicação e Reversão de Migrações

-   **Aplicando Migrações:**
    
    -   **Executando Script SQL Manualmente:** O script gerado pode ser executado diretamente no banco de dados.
        
    -   **Via Comando:** Utilize `Update-Database` para aplicar migrações automaticamente.
        
    -   **Via Program.cs:** No código, chame `context.Database.Migrate()` para aplicar migrações durante a inicialização.
	    - Não recomendado.
        
-   **Revertendo Migrações (Rollback):**
    
    -   Especificar uma migração anterior para restaurar um estado anterior: `Update-Database NomeDaMigracaoAnterior`

        
    -   Remover a última migração (caso ela não tenha sido aplicada): `Remove-Migration`
  ---      
        
## 6. Migrações Idempotentes e Boas Práticas para Produção

-   **Script Idempotente:** Scripts idempotentes contêm validações que evitam erros ao serem executados diversas vezes.
    
-   **Ambientes Diferentes:**
    
    -   **Desenvolvimento:** Migrações podem ser aplicadas automaticamente.
        
    -   **Produção:** Scripts SQL devem ser gerados e analisados antes de serem aplicados manualmente.
        
-   **Verificando Migrações Pendentes:**
    
    ```csharp
    bool temPendentes = context.Database.GetPendingMigrations().Any();
    ```
---

## 7. Complementos para Evoluir até Nível Sênior

-   **Versionamento e Controle de Alterações:** Documente migrações e integre-as com ferramentas de CI/CD.
    
-   **Análise de Impacto e Performance:** Avalie como alterações no esquema do banco afetam desempenho.
    
-   **Automatização e Estratégias de Deploy:** Utilize scripts idempotentes e pipelines de deploy para garantir estabilidade.
    
-   **Documentação e Referência Oficial:** Consulte a documentação do EF Core para melhores práticas.
    
-   **Uso no Visual Studio:** Prefira a _Package Manager Console_ para gerenciar migrações diretamente na IDE.
---
**Fontes:**  Curso Introdução ao Entity Framework Core - Módulo Migrações - Desenvolvedor.io
