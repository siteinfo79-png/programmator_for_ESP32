# 🔌 ESP32 программатор — схема подключения

Правильное подключение USB-UART программатора (CP2102/CH340/FTDI) к ESP32 с автоматическим входом в режим прошивки.

## 📦 Компоненты
- ESP32 (любая версия)
- USB-UART программатор 3.3V
- Конденсатор 100 нФ
- Диод 1N4148

## 📐 Схема соединений

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

    A ---|"100nF"| G
    B ---|"диод"| H
    C --- I
    D --- J
    E --- K
    F --- L
