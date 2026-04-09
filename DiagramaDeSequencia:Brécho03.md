**DiagramaDeSequencia:Brécho**
```mermaid
sequenceDiagram
participant U as Usuario
participant S as Site
participant B as BancoDeDados
U->>S:Seleciona Menu "Brécho"
S->>B:Procura itens disponiveis à venda
B-->>S:Mostra itens junto com o preço
S-->>U:Exibe itens com o preço abaixo
U->>S:Escolhe item
S->>B:
