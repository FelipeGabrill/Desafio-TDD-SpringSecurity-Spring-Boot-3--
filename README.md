# Projeto Event-City

## Objetivo do Projeto

O **Projeto Event-City** consiste em desenvolver uma API RESTful utilizando **Java** e **Spring Boot**, com o objetivo de gerenciar eventos e cidades. A aplicação integra **testes automatizados (TDD)**, **segurança com Spring Security e OAuth2** e **controle de acesso por perfis de usuários**, seguindo as melhores práticas de desenvolvimento e segurança.

## Competências Avaliadas

- **Desenvolvimento TDD de API Rest com Java e Spring Boot**: Avaliação dos testes automatizados são escritos previamente como especificação para garantir a qualidade da API e validar as funcionalidades.

- **Implementação de segurança com Spring Security e OAuth2**: Garantia de que a API possua controle de acesso adequado, utilizando OAuth2 para autenticação e autorização.

- **Controle de acesso por rotas e perfis de usuário**: Verificação de que diferentes perfis de usuário (cliente, administrador) têm permissões específicas para acessar rotas e recursos.

- **Validação de dados com Bean Validation**: Garantia de que os dados enviados nas requisições sejam validados corretamente, incluindo a validação de campos obrigatórios e regras de negócio como datas e nomes.
  
## Critérios de Correção

### Testes Implementados

1. **POST /events deve retornar 401 Unauthorized para usuário não logado**
   - **Objetivo**: Garantir que o acesso ao endpoint para criação de eventos seja restrito a usuários logados.

2. **POST /events deve retornar 201 Created para CLIENT logado e dados corretos**
   - **Objetivo**: Verificar que, quando um cliente (usuário com permissões adequadas) está logado e envia dados corretos, o evento é criado com sucesso.

3. **POST /events deve retornar 201 Created para ADMIN logado e dados corretos**
   - **Objetivo**: Verificar que, quando um administrador está logado e envia dados corretos, o evento é criado com sucesso.

4. **POST /events deve retornar 422 Unprocessable Entity para ADMIN logado e nome em branco**
   - **Objetivo**: Garantir que o nome do evento não pode ser em branco, retornando erro 422 quando esse campo estiver vazio.

5. **POST /events deve retornar 422 Unprocessable Entity para ADMIN logado e data no passado**
   - **Objetivo**: Garantir que a data do evento não pode ser no passado, retornando erro 422 quando a data fornecida for inválida.

6. **POST /events deve retornar 422 Unprocessable Entity para ADMIN logado e cidade nula**
   - **Objetivo**: Garantir que o campo "cityId" seja obrigatório e que, se nulo, retorne erro 422.

7. **GET /events deve retornar 200 Ok com página de recursos**
   - **Objetivo**: Verificar que a listagem de eventos é retornada corretamente e paginada.

8. **POST /cities deve retornar 401 Unauthorized para usuário não logado**
   - **Objetivo**: Garantir que o acesso ao endpoint de criação de cidades seja restrito a usuários logados.

9. **POST /cities deve retornar 403 Forbidden para CLIENT logado**
   - **Objetivo**: Verificar que o cliente não tem permissões suficientes para criar cidades, retornando erro 403.

10. **POST /cities deve retornar 201 Created para ADMIN logado e dados corretos**
    - **Objetivo**: Garantir que um administrador logado possa criar uma cidade com dados válidos.

11. **POST /cities deve retornar 422 Unprocessable Entity para ADMIN logado e nome em branco**
    - **Objetivo**: Garantir que o nome da cidade seja obrigatório e que o campo em branco retorne erro 422.

12. **GET /cities deve retornar 200 Ok com todos recursos ordenados por nome**
    - **Objetivo**: Verificar que a listagem das cidades seja retornada corretamente e ordenada por nome.

## Como Executar o Projeto

### Pré-requisitos

Antes de executar o projeto, é necessário ter os seguintes softwares instalados:

- **Java 17 ou superior**
- **Maven**
- **IDE como IntelliJ IDEA ou Eclipse**
