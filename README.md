# Arduino ECG Portátil
A escalabilidade é uma característica muito aplicada em solução de tecnologia da informação / computação. O conceito de “crescer” a oferta de recursos por demanda é muito atrativo em prover melhores produtos e diminuição de custo. Relacionando o tema a área de saúde, vemos atualmente dificuldade, principalmente econômica, na adequação de leitos a demanda de pacientes com a COVID-19. Com o uso da computação ubíqua (IoT – Internet of Things/Internet das Coisas).

O AD8232 é um bloco de condicionamento de sinal integrado para aplicações de medição de ECG (eletrocardiografia) e monitoramento da frequência cardíaca. Ele é projetado para extrair, amplificar e filtrar pequenos sinais biopotenciais na presença de condições ruidosas, como aquelas criadas por movimento ou posicionamento de eletrodos remotos. Esse design permite que um conversor analógico-digital (ADC) de energia ultrabaixa ou um microcontrolador incorporado adquira facilmente o sinal de saída (fonte: https://www.eletrogate.com/modulo-pulso-cardiaco-com-eletrodos-ad8232).

O CI consiste em um amplificador de instrumentação especializado (IA), um amplificador operacional (A1), um amplificador de acionamento para a perna direita (A2) e um buffer de referência de meio da frase (A3).

O ECG é a medição dos potenciais elétricos gerados pela despolarização e repolarização das células do coração, atividade que gera o impulso bioelétrico responsável pela contração cardíaca. Os impulsos elétricos do coração são detectáveis na superfície do corpo mediante a aplicação de eletrodos.

O sinal de ECG é um sinal analógico sendo necessário proceder à digitalização e quantização deste tipo de sinal uma vez que os computadores e os dispositivos móveis operam no domínio discreto. Este tipo de sinal é susceptível a ruído proveniente de várias fontes, nomeadamente da rede elétrica, da deslocação dos eletrodos relativamente à sua posição inicial e de certos artefatos originados pela contração muscular. É necessário proceder a uma filtragem do sinal previamente à fase de detecção do complexo QRS. (VALENTE, 2014)

## Esquema de ligação:
![](https://user-images.githubusercontent.com/77074489/103965373-f32e1e80-5133-11eb-8532-ab204fa965a6.png)

## Equipamentos:
[1] MÓDULO PULSO CARDÍACO COM ELETRODOS AD8232 <br/>
[2] ARDUINO UNO R3<br/>
[3] CABO USB<br/>
[4] 5 JUMPERS MACHO/FÊMEA<br/>

## Programação Arduino:
```
void setup() {
  Serial.begin(9600);
  pinMode(10, INPUT);
  pinMode(11, INPUT);  
}

void loop() {
 if ((digitalRead(10)==1)||(digitalRead(11) == 1)){
   Serial.println("!");
 } else {
   Serial.println(analogRead(A0));
 }
 
 delay(1);  
}
```

## Dados Coletados:
![](https://user-images.githubusercontent.com/77074489/103965437-12c54700-5134-11eb-898d-5b5f2ee7dd44.png)

## Vídeo disponível em:
https://www.arduinobrasil.cc/files/dados_coletados.mp4

## Autores:
Ivo Brites<br/>
Josué Nascimento<br/>

## Referencias:
VALENTE, J. H. R. Monitorização de ECG de Pacientes em Mobilidade. 137 p., 2014.
