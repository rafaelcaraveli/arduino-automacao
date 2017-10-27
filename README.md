# arduino-automacao
Projeto com objetivo de acender um led conectado a uma bateria usando um button e um relé.

int rele = 52;
int botao = 2;
int estado = 0;

void setup(){
 pinMode(rele,OUTPUT);
 pinMode(botao,INPUT);
 digitalWrite(botao,HIGH);
 Serial.begin(9600);
}

void loop() {
 int valor = digitalRead(botao);
 Serial.println(valor);
 if (valor == 1) {
 while (digitalRead(botao) == 1)
 delay(100);
 estado = !estado;
 digitalWrite(rele, estado);
 }
}
