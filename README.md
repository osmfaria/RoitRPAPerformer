### Test Técnico -  ###
Este projeto foi realizado com base state machines, utilizando REFramework

## 🎯 Objetivo:
Este workflow atua como Performer
- Buscar transaction items na queue do orchestrator;
- Enviar dados através de POST requests para a API.

## 📑 State Machines
Nesta sessão serão descritos as principais tasks realizadas por cada state machine do REF deste repositório

**1. INITIALIZATION**
 - Inclui a execução das atividades de inicialização padrão do template de REFramework, sendo a principal delas a leitura do arquivo Config.xlsx, aqui foram setadas a pasta do orchestrator em que a queue se encontra assim como o nome da queue;

**2. GET TRANSACTION DATA**
 - Padrão utilizado pelo template REF, utilizando get queue item activity e enviando para processamento ou finalizando processo caso não haja mais transactions.

**3. PROCESS TRANSACTION**
- Invoca workflow para envio de requests para API com os dados da Transaction Item, o status de retorno da API controla a mudança do status do transaction item para success ou failure.

**4. END PROCESS**
 - Padrão utilizado pela REF, se em uma futura atualização neste projeto, seja necessário utilizar alguma aplicação, a mesma será encerrada aqui.


## 📋 Guia de instalação
Para executar localmente este app, siga as intruções abaixo:

- Clone este repositório;
- No arquivo Config.xlsx os seguintes campos devem ser preenchidos: 
    - OrchestratorQueueName (Criei uma Queue no orchestrator e indique aqui o nome)
    - OrchestratorQueueFolder (Indique qual pasta está sendo utilizada no orchestrator)

## 🔗 Links

- Repositório do backend | API [aqui](https://github.com/osmfaria/roit-api)
- Repositório do workflow que atua como dispatcher [aqui](https://github.com/osmfaria/RoitRPA)

