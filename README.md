# Sistema de Irrigação Automático

### Fala, macacada! 🐒

Esse projeto é um sistema de irrigação automático com dois modos: **Manual** e **Automático**, controlado pela placa BitDogLab com o microcontrolador RP2040. O mais daora é que a galera pode controlar tudo via uma interface web!

## O que o sistema faz?

O sistema tem dois modos principais:

1. **Modo Manual**: Aqui, você tem o controle total! Pode ligar ou desligar os setores de irrigação manualmente pelo botão da interface web. Quando um setor é ligado ou desligado, o buzzer solta aquele som de confirmação. 🔊
   
2. **Modo Automático**: O sistema vai alternando entre os setores automaticamente, de 1 a 4, a cada 10 segundos. E a cada troca de setor, o buzzer avisa! 🕹️🔄

### Modo Manual x Modo Automático

- No **Modo Manual**, você manda ver e decide qual setor ligar ou desligar, usando os botões na interface web. Isso pode ser feito de forma individual para cada setor.
- No **Modo Automático**, a parada acontece sozinha. Os setores vão se alternando a cada 10 segundos, no estilo "agora é a vez do setor X". E claro, cada troca vem com um som do buzzer pra avisar que foi trocado. 

## Funcionalidades do Sistema

- **Alternar entre os modos**: Dá pra alternar entre o **Modo Manual** e o **Modo Automático** pela interface web.
- **Controle de Setores**: Ligar/desligar setores manualmente (Setor 1, Setor 2, Setor 3 e Setor 4).
- **Indicação Visual**: A matriz de LEDs mostra os setores, onde os LEDs ficam **vermelhos** quando desligados e **verdes** quando ligados.
- **Alarme Sonoro**: Sempre que muda de setor (ou no Modo Automático), o buzzer emite um som pra avisar que o setor foi alterado. 🎶
  
### Como Funciona o Código?

O código foi feito pra controlar a irrigação de forma simples e sem complicação! O sistema roda tudo de acordo com a programação que define os tempos de troca entre os setores (10 segundos). Além disso, o código cuida da parte sonora (buzzer) e do controle de modo via interface web.

#### Alarme no Modo Automático

O buzzer também tem uma função de alarme: ele é ativado quando o sistema entra no **Modo Automático** e toca toda vez que o setor é trocado. É uma interrupção que rola a cada 10 segundos pra garantir a troca dos setores!

## Como Rodar o Projeto?

1. Faça o clone do repositório no seu PC.
2. Conecte a BitDogLab na sua máquina.
3. Compile e faça o upload do código na placa.
4. Abra o navegador e acesse a interface web pelo IP da sua placa.
5. A partir daí, você pode controlar a irrigação e alternar entre os modos.

## Tecnologias Usadas

- BitDogLab (com microcontrolador RP2040)
- Interface Web (pra controle)
- Buzzer para indicações sonoras
- Matriz de LEDs para exibição dos setores
- Código em C com lógica simples de controle de setores e interrupções

## Licença


