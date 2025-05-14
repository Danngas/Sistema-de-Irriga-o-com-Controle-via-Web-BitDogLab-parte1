# Sistema de Irrigação Automático

## Descrição

Este projeto tem como objetivo o desenvolvimento de um sistema de irrigação inteligente utilizando a placa **BitDogLab** com o microcontrolador **RP2040**. O sistema possui dois modos de operação: **Modo Manual** e **Modo Automático**, sendo controlado através de uma interface web, permitindo ao usuário gerenciar os setores de irrigação de forma prática e eficiente.

## Funcionalidades

### Modo Manual
No **Modo Manual**, o usuário pode controlar os setores de irrigação individualmente. Cada setor pode ser ligado ou desligado através de botões na interface web. Quando uma ação de ligar ou desligar um setor é realizada, o buzzer emite um som para indicar que a ação foi executada.

### Modo Automático
No **Modo Automático**, o sistema alterna automaticamente entre os setores de irrigação, ligando e desligando cada setor com um intervalo fixo de 10 segundos. O buzzer emite um som cada vez que a troca entre os setores ocorre. O tempo de troca não pode ser ajustado diretamente pelo usuário, sendo definido no código.

### Alternar Entre Modos
O usuário pode alternar entre o **Modo Manual** e o **Modo Automático** através da interface web. O sistema permite essa transição de maneira simples, através de um botão de alternância.

### Exibição Visual
A matriz de LEDs exibe os quatro setores de irrigação. Quando um setor está desligado, o LED correspondente fica vermelho; quando está ligado, o LED fica verde. Além disso, o display exibe a animação que indica o estado de cada setor, mostrando se ele está ligado ou desligado.

### Alarme Sonoro
O sistema utiliza um buzzer para emitir um alarme sempre que um setor é alterado, seja manualmente ou automaticamente. O alarme é uma interrupção programada que é ativada quando o sistema entra no **Modo Automático** e é desativada quando o modo é desligado.

## Tecnologias Utilizadas

- **BitDogLab** (microcontrolador RP2040)
- **Interface Web** (para controle e alternância entre os modos)
- **Matriz de LEDs** (para exibição dos setores)
- **Buzzer** (para indicações sonoras)
- **C** (linguagem de programação utilizada no código)

## Como Rodar o Projeto

1. Clone este repositório em sua máquina.
2. Conecte a placa **BitDogLab** à sua máquina.
3. Compile o código e faça o upload na placa.
4. Acesse a interface web no navegador através do IP da sua placa.
5. A partir daí, você poderá controlar os setores e alternar entre os modos.

## Licença

Este projeto é de código aberto. Sinta-se à vontade para usar, modificar e compartilhar. Para modificações, por favor, dê o devido crédito ao autor do projeto.

