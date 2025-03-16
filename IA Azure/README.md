# Configuração da Pesquisa do Azure AI  

Esse é um passo a passo rápido para configurar a Pesquisa do Azure AI e integrá-la em aplicações. Além disso, compartilho algumas ideias sobre como essa ferramenta pode ser útil e alguns aprendizados que tive no processo.  

---

## O que precisa antes de começar  

- Uma conta no [Azure](https://azure.microsoft.com/).  
- Permissão para criar e gerenciar recursos.  
- Noções básicas de APIs e consultas.  

---

## Passo a passo  

### 1. Criando o recurso  

1. Acesse o [Portal do Azure](https://portal.azure.com/).  
2. Vá em **Criar um recurso** e procure por **Azure Cognitive Search**.  
3. Preencha os detalhes básicos (nome, assinatura, região, etc.).  
4. Clique em **Criar** e aguarde a implantação.  

### 2. Configurando o índice  

1. Dentro do recurso criado, vá até **Índices** e clique em **Adicionar índice**.  
2. Defina os campos principais (exemplo: `id`, `titulo`, `descricao`).  
3. Escolha os tipos de dados corretos (texto, número, etc.).  
4. Salve as configurações.  

### 3. Importando dados  

1. Vá para **Fontes de Dados** e clique em **Adicionar**.  
2. Escolha de onde os dados virão (SQL, Cosmos DB, Blob Storage, etc.).  
3. Configure a conexão e salve.  

### 4. Fazendo consultas  

Agora dá pra testar a busca via API. Exemplo:  

```bash
curl -X GET "https://[nome-do-recurso].search.windows.net/indexes/[nome-do-índice]/docs?search=[termo]" -H "Content-Type: application/json" -H "api-key: [sua-chave]"
