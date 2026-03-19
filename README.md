```mermaid
sequenceDiagram
participant U as usuario
participant App as aplicativo
participant bend as backend
participant banco as banco de dados

U->>App: Clicar em endereço
App-->>App: coordenadas(GPS)
App->>bend: UserID
bend->>banco: busca ultimas 10 ruas do UserID
banco-->>bend:Endereços
bend-->>bend:calcula distancia
bend-->>App:Historico, distancia
App-->>U: requisita novo endereço ou existente
U->>App:seleciona "pesquisar"
App-->>App:envia notificação para usuarios(motoristas) proximos
App->>bend:Informações do usuario(nome, local, destino)
bend->>banco:Requisita UserID dos motoristas proximos
banco-->>bend: UserID(motoristas)
bend-->>App: informações dos motoristas(nome, carro, distancia do usuario)
App-->>U: repassa informações para o usuario
