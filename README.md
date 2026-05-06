### Схема соединений

```mermaid
graph LR
    subgraph Программатор
        A[DTR]
        B[RTS]
        C[TX]
        D[RX]
        E[GND]
        F[VCC 3.3V]
    end

    subgraph ESP32
        G[GPIO0]
        H[EN]
        I[RX]
        J[TX]
        K[GND]
        L[3.3V VCC]
    end

    A ---|"100nF конденсатор"| G
    B ---|"диод или резистор 10к"| H
    C --- I
    D --- J
    E --- K
    F --- L
