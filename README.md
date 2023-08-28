# Desafio: API Segura e Escalável em um Ambiente Limitado

## Objetivo
Desenvolver uma API RESTful que seja capaz de lidar com uma alta demanda de requisições simultâneas em um ambiente com recursos limitados, garantindo também a segurança contra ataques comuns.

## Ambiente

- **Host Limitado:** 
  - **vCPUs:** 2
  - **RAM:** 1GB
- **Meta de Requisições:** A API deve ser capaz de lidar com 50.000 requisições por minuto.

## Parte 1: Desenvolvimento da API

1. **Endpoint de Registro:** 
    - Crie um endpoint `POST /register` que permita o registro de um usuário com nome, e-mail e senha.
    - A senha do usuário deve ser armazenada de forma segura (hash e sal).
    - O e-mail do usuário deve ser único.

2. **Endpoint de Login:**
    - Crie um endpoint `POST /login` que permita que um usuário faça login usando seu e-mail e senha.
    - Em caso de sucesso, retorne um token JWT que será usado para autenticar as próximas requisições.

3. **Endpoint de Dados:**
    - Crie um endpoint `GET /data` que retorne alguns dados fictícios, mas que só possa ser acessado por usuários autenticados.

## Parte 2: Teste de Carga

1. **Configuração:** 
    - Use ferramentas como o [Locust](https://locust.io/) ou [Apache JMeter](https://jmeter.apache.org/) para simular uma grande quantidade de usuários acessando sua API simultaneamente.
    - Configure os testes para simular 50.000 usuários fazendo requisições ao endpoint `/data` por minuto.

2. **Análise:** 
    - Monitore o tempo de resposta da sua API e a utilização de recursos do servidor.
    - Identifique gargalos e otimize sua API para lidar com a carga, mantendo-se dentro das limitações do host.

## Parte 3: Segurança

1. **Injeção de SQL:** 
    - Garanta que sua API esteja protegida contra ataques de injeção de SQL.
    - Teste seu endpoint de registro e login com entradas maliciosas para tentar explorar possíveis vulnerabilidades.

2. **Rate Limiting:** 
    - Implemente um sistema de limitação de requisições para evitar ataques de força bruta no endpoint de login.
    - Por exemplo, limite um IP a 5 tentativas de login por minuto.

3. **Headers de Segurança:** 
    - Configure sua API para usar headers HTTP de segurança, como `Strict-Transport-Security` e `Content-Security-Policy`.

4. **Logs:** 
    - Mantenha logs detalhados de todas as requisições, incluindo tentativas de acesso maliciosas.
    - Implemente alertas para notificar quando padrões suspeitos de comportamento são detectados.

## Critérios de Avaliação

- Funcionalidade da API.
- Capacidade de lidar com alta carga dentro das limitações do servidor.
- Implementação de medidas de segurança.
- Qualidade do código e organização.
