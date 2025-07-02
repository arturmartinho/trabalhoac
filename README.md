# Projeto SAP-5 Microcontrolador com Periféricos - Logisim 2.7.1

## 📌 Descrição

Este projeto é uma extensão da arquitetura SAP-5, implementado no **Logisim versão 2.7.1**, com a adição de **periféricos que o transformam em um microcontrolador funcional**, incluindo:

- 🕒 **Temporizador (Timer)**  
- 🧠 **Porta de entrada de 8 bits (Input Switches)**  
- 🔄 **Unidade de comunicação serial de entrada e saída de 8 bits**

---

## 🎯 Objetivo

Transformar a arquitetura SAP-5 tradicional em um microcontrolador completo e funcional, capaz de interagir com periféricos de entrada/saída e controlar o fluxo de execução com base em tempo (delay), entrada do usuário e comunicação serial.

---

## 🧱 Componentes principais

| Bloco                         | Função                                                                 |
|------------------------------|------------------------------------------------------------------------|
| **Contador de Programa (PC)**| Avança sequencialmente ou salta para endereços da RAM                 |
| **Memória RAM**              | Armazena o programa em assembly SAP                                   |
| **Registrador de Instruções**| Separa opcode e operando para controle sequencial                     |
| **Registradores A e B**      | Acumulador e registrador auxiliar para operações aritméticas          |
| **ULA**                      | Executa operações como ADD, SUB, MUL, etc.                            |
| **Controle Sequencial (ROM)**| Controla os sinais internos para cada ciclo de máquina                |
| **Temporizador (Timer)**     | Gera delays com base em clock secundário, usado com instrução `SLP`  |
| **Porta de Entrada (IN)**    | Recebe dados do usuário via chaves (8 bits)                           |
| **Registrador de Entrada**   | Armazena os dados da porta IN para uso pela CPU                       |
| **Unidade de Saída Serial**  | Mostra dados do acumulador nos displays de 7 segmentos                |

---

## 💾 Instruções disponíveis

| Instrução | Opcode | Função                                   |
|----------|--------|------------------------------------------|
| `LDA`    | 0000   | Carrega valor da RAM para o Acumulador   |
| `ADD`    | 0001   | Soma conteúdo de RAM ao Acumulador       |
| `SUB`    | 0010   | Subtrai valor da RAM do Acumulador       |
| `INC`    | 0011   | Incrementa Acumulador                    |
| `DEC`    | 0100   | Decrementa Acumulador                    |
| `MUL`    | 0101   | Multiplica Acumulador por valor da RAM   |
| `JMP`    | 0110   | Salta para endereço especificado         |
| `OUT`    | 0111   | Envia valor do Acumulador para saída     |
| `SLP`    | 1000   | Pausa execução por tempo determinado     |
| `INA`    | 1001   | Lê valor da entrada de 8 bits            |
| `HLT`    | 1111   | Interrompe a execução (halt)             |

---

## 📐 Organização do circuito

O circuito está organizado de forma lógica:
- Blocos principais (PC, IR, RAM) à esquerda.
- ULA e registradores no centro.
- Periféricos (Timer, Entrada e Saída Serial) à direita.
- Barramento de dados compartilhado.
- Sinais de controle interligados com a ROM de microinstruções.

---

## ▶️ Como utilizar

1. **Abra o arquivo `.circ` no Logisim 2.7.1**
2. **Programe a RAM** com instruções desejadas.
3. **Use a entrada de switches** para simular dados externos.
4. **Execute os ciclos de clock** ou use modo automático.
5. **Observe a saída nos displays de 7 segmentos**.
6. **Utilize o botão Reset** sempre antes de iniciar uma nova execução.

