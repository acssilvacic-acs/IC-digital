# Semana 1.2 — Protoboard virtual, resistores e LEDs externos  

## 1. Objetivo da semana 
Montar um semáforo simples utilizando somente uma protoboard, LEDs, resistoes e Arduino
 
## 2. O que foi estudado 
- Pinos digitais do arduino
- Funcionamento de LED e resistor e por que o LED depende de um resistor para funcionar corretamente.
- Estrutura básica de um programa no Arduino.
- Funcionamento da protoboard.

## 3. O que eu aprendi 
 
### Estudante 1 
Texto individual do estudante. 
### Estudante 2 
Desenvolvendo a parte do código, pude perceber como funciona um semáforo, no Arduino, a gente configurou os pinos como saída com o pinMode e controlou a energia com o digitalWrite. O ciclo acontece na sequência, usando o delay para definir o tempo que cada cor fica acesa, dentro do loop infinito

 
## 4. Explicação técnica da atividade 
Explicar como o circuito funciona, como o código funciona e qual é a relação entre hardware e software. 

## 5. Circuito 

| Componentes | Modelo / Valor | Quantidade | Função no circuito  |
| :--- | :--- | :--- | :--- |
| **Arduino Uno** | R3 | 1 | Controlar o tempo do sistema e mudar os sinais de saída conforme o que está programado no código. |
| **LED Vermelho** | Comum (5mm) | 1 | Luz de "PARE". Ligado na porta digital 11. |
| **LED Amarelo** | Comum (5mm) | 1 | Luz de "ATENÇÃO". Ligado na porta digital 10. |
| **LED Verde** | Comum (5mm) | 1 | Luz de "SIGA". Ligado na porta digital 9. |
| **Resistores** | $330\ \Omega$ | 3 | Servem para proteger os LEDs. Eles seguram o excesso de energia para as luzes não queimarem. |
| **Protoboard** | 400 pontos | 1 | A placa de ensaio onde encaixamos as peças e fazemos as ligações elétricas sem precisar de solda. |
| **Fios (Jumpers)** | Macho-Macho | 4 | Fios coloridos para conectar tudo. Usamos 3 para os sinais das portas 9, 10 e 11, e 1 preto para ligar o negativo (GND). |

## 7. Código 
A lógica utilizada para o desenvolvimento do funcionamento do semáforofoi a seguinte: O programa vai lendo as linhas de cima para baixo, dentro do loop(), e fica repetindo esse ciclo sem parar. Quando a gente liga uma cor com o HIGH, o código já desliga as outras duas com o LOW. Já o delay() dá uma pausa em tudo por alguns segundos (5 segundos para o verde e o vermelho, e 2 para o amarelo) antes de passar para o próximo comando. Assim o semáforo consegue manter cada cor acesa no tempo certo.

Código: [Clique aqui para ver o código (semana-1.2.ino)](../firmware/src/semana-1.2.ino)
 
## 8. Testes realizados 
Descrever como o teste foi executado. 
## 9. Resultados obtidos 
Apresentar leituras, imagens, vídeo curto, tabela ou observações. 


https://github.com/user-attachments/assets/d9bc92a3-cecf-4fcb-b59b-ba29078a3c9a


## 10. Problemas encontrados 

Durante a contrução do circuito, que foi realizada paralelo aos estudos sobre os componentes, foi encontrado um erro na montagem, como pode ser visto na imagem abaixo:

<img width="953" height="866" alt="image" src="https://github.com/user-attachments/assets/de152ed9-7b87-4d6d-874b-a8e773ce60ee" />

Inicialmente, acreitávamos que a alimentação do circuito seria realizada somente pelo pino 5V do Arduino, mas, ao mergulhar mais fundo nos estudos sobres os pinos digitais, descobrimos que a alimentação seria feita pelos pinos digitais onde os LEDs estavam conectados, e que manter a alimentação pelo pino V5 deixaria todos os LEDs ligados o tempo todo, já que estariam recebendo tensão a todo momento, o que resultaria em erro, visto que a intenção era alternar os status de "ligado" e "desligado" dos LEDs, algo que seria feito através da Lógica do nosso código mais tarde.

## 11. Correções realizadas 

Para corrigir esse erro, como pode ser visto na imagem abaixo, removemos a alimentação realizada através do pino 5V, deixando somente os pinos digitais ~9, ~10 e ~11 como os responsáveis por levar tenão aos LEDs. 

<img width="701" height="597" alt="image" src="https://github.com/user-attachments/assets/3045a97f-f4b9-41c1-a096-b550f2941f0b" />

## 12. Relação com aplicações do dia a dia 
Explicar como o conceito estudado na semana pode ser usado em uma solução real. 
## 13. Critério de aceite 
Informar se a entrega passou ou não passou no critério técnico definido. 
## 14. Link da simulação, vídeo ou evidência 
Inserir link do Tinkercad, vídeo, imagem, commit ou pasta do GitHub.
