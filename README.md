### Test Técnico - Engenheiro de RPA ###
Este projeto foi realizado com base em state machines, utilizando REFramework

## 🎯 Objetivo
Este workflow atua como Performer
- Buscar transaction items na queue do orchestrator;
- Enviar dados através de POST requests para a API.

## 📑 State Machines
Nesta sessão serão descritas as principais tasks realizadas por cada state machine do REF deste repositório

**1. INITIALIZATION**
 - Inclui a execução das atividades de inicialização padrão do template de REFramework, sendo a principal delas a leitura do arquivo Config.xlsx. Nesta etapa, são configuradas a pasta do orchestrator onde a queue está localizada, assim como o nome da queue;

**2. GET TRANSACTION DATA**
 - Padrão utilizado pelo template REF, utilizando a atividade get queue item e encaminhando-o para processamento ou finalizando o processo caso não haja mais transações.

**3. PROCESS TRANSACTION**
- Invoca workflow para envio de requests para API com os dados da Transaction Item. O status de retorno da API controla a mudança do status do transaction item para "success" ou "failure".

**4. END PROCESS**
 - Padrão utilizado pelo REF. Caso seja necessário utilizar alguma aplicação em futuras atualizações neste projeto, a mesma será encerrada nesta etapa.


## 📋 Guia de instalação
Para executar localmente este app, siga as intruções abaixo:

- Clone este repositório;
- No arquivo Config.xlsx os seguintes campos devem ser preenchidos: 
    - OrchestratorQueueName (Criei uma Queue no orchestrator e indique aqui o nome)
    - OrchestratorQueueFolder (Indique qual pasta está sendo utilizada no orchestrator)

## 🔗 Links

- Repositório do backend | API [aqui](https://github.com/osmfaria/roit-api)
- Repositório do workflow que atua como dispatcher [aqui](https://github.com/osmfaria/RoitRPA)

