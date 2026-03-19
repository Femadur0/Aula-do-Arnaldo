sequenceDiagram
    participant U as Desenvolvedor
    participant A as Git Local
    participant B as GitHub (Servidor)
    participant D as Repositório Remoto

    U->>A: Clica em "Escolher Endereço"
    A->>B: Solicita endereços (latitude/longitude atual)
    B->>D: Consulta endereços cadastrados 
    D-->>B: Retorna lista de endereços
    Note over B: Calcula distâncias em KM 
    B-->>A: Retorna lista de endereços + distâncias
    A-->>U: Exibe lista de endereços com KM
