
## Integrantes 
- Jonathan Fernandez
- Santiago Amato
- Joaquin Carnelos Duarte
- Magali Gimenez

## Descripción
1- El semáforo tiene que tener 2 leds de cada color como mínimo, en caso de que uno se  rompa. 
2- Tiene que implementar los tiempos correctos como se detallan a continuación. 3- El verde dura 5 segundos. 
4- El amarillo dura 3 segundos. 
5- Rojo dura 5 segundos. 
6- Tiene que tener señalización para personas no videntes como se detalla a  continuación. (Buzzer o piezo)
7- Durante el rojo: Tiene que sonar 2 vez por segundo en un tono FUERTE. 

## Función principal:
- //definir leds y piezo
#define rojo1 2
#define rojo2 3
#define amarillo1 4
#define amarillo2 5
#define verde1 6
#define verde2 7
#define piezo 11

// constantes tiempos
const int tiempoVerde = 5000;
const int tiempoAmarillo = 3000;
const int tiempoRojo = 5000;
const int piezoPrender = 500;
const int piezoApagar = 500;


~~~ C (lenguaje en el que esta escrito)
void setup(){
  pinMode(6, OUTPUT);
  pinMode(7, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(11, OUTPUT);
}

void loop(){
  faseVerde();
  faseAmarilla();
  faseRoja();
  }

void apagarLeds(){
  digitalWrite(6, 0);
  digitalWrite(7, 0);
  digitalWrite(4, 0);
  digitalWrite(5, 0);
  digitalWrite(2, 0);
  digitalWrite(3, 0);
}

//Verde
void faseVerde(){
  apagarLeds();
  digitalWrite(6, 1);
  digitalWrite(7, 1);
  activarPiezo(0);
  delay(tiempoVerde);
}

//Amarillo
void faseAmarilla(){
  apagarLeds();
  digitalWrite(4, 1);
  digitalWrite(5, 1);
  activarPiezo(0);
  delay(tiempoAmarillo);
}

//Rojo
void faseRoja(){
  apagarLeds();
  digitalWrite(2, 1);
  digitalWrite(3, 1);
  activarPiezo(tiempoRojo);
  
}

//Piezo
void activarPiezo(int tiempo){
  for (int i = 0; i < tiempo;i+=piezoPrender+piezoApagar) {
    tone(11,1000);
    delay(piezoPrender/2);
    noTone(11);
    delay(piezoApagar/2);

  }
}
~~~

## Link al proyecto:
- [proyecto](https://www.tinkercad.com/things/8L0ZZGNULYv?sharecode=l6ph9JN3hTitBmxZJr_NqEklLnHbRX-NbpJDkcaUi1M)
