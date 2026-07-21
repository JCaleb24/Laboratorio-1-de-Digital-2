# Laboratorio-1-de-Digital-2
Lab 1 
#include <Arduino.h>
#include <stdio.h>
#include <stdint.h>

//led
const int led1 = 15;
const int led2 = 2;
const int led3 = 4;
const int led4 = 16; 

//Pushbuttoms
int boton1 = 23;
int boton2 = 21;
int boton3 = 22;
int modo = 0;
int num = 0;
int salida, salida2, salida3;

// put function declarations here:


void setup() {
  // put your setup code here, to run once:
  pinMode(led1, OUTPUT);
  pinMode(led2, OUTPUT);
  pinMode(led3, OUTPUT);
  pinMode(led4, OUTPUT);
  pinMode(boton1, INPUT_PULLDOWN);
  pinMode(boton2, INPUT);
  pinMode(boton3, INPUT);

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);

  
}

void loop() {
//boton1
  int estado = digitalRead(boton1);
  delay(15);
  if (estado == HIGH){
    (salida = 1);

  }
  if(salida == 1 && estado == LOW){
    salida = 0;
    num++;
      if (modo == 0 && num > 4) {
      num = 1;
    }

    if (modo == 1 && num > 15) {
      num = 0;
    }
  }

   //boton2
  int estado2 = digitalRead(boton2);
  delay(10);
  if (estado2 == LOW){
    (salida2 = 1);
  }
  if(salida2 == 1 && estado2 == HIGH){
    salida2 = 0;
    num--;
     if (modo == 0 && num < 1) {
      num = 4;
    }

    if (modo == 1 && num < 0) {
      num = 15;
    }
     
  }



  //boton3
  int estado3 = digitalRead(boton3);
  delay(10);
  if (estado3 == HIGH){
    (salida3 = 1);
  }
  if(salida3 == 1 && estado3 == LOW){
    salida3 = 0;
    modo++;
      if(modo > 1)
        modo = 0;
      
      num = 0;
    
  }

  digitalWrite(led1, LOW);
  digitalWrite(led2, LOW);
  digitalWrite(led3, LOW);
  digitalWrite(led4, LOW);

 
  //Contadores 
  if(modo == 0){
  switch(num){
   case 1:
   digitalWrite(led1, HIGH);
   break;


   case 2:
   digitalWrite(led2, HIGH);
  
  
   
   break;
   case 3:
   digitalWrite(led3, HIGH);


 
   break;
   case 4:
   digitalWrite(led4, HIGH);
   break;

  // put your main code here, to run repeatedly:
}
  
}
 else if (modo == 1) {

  switch(num){

    case 0:
      break;

    case 1:
      digitalWrite(led1, HIGH);
      break;

    case 2:
      digitalWrite(led2, HIGH);
      break;

    case 3:
      digitalWrite(led1, HIGH);
      digitalWrite(led2, HIGH);
      break;

    case 4:
      digitalWrite(led3, HIGH);
      break;

    case 5:
      digitalWrite(led1, HIGH);
      digitalWrite(led3, HIGH);
      break;

    case 6:
      digitalWrite(led2, HIGH);
      digitalWrite(led3, HIGH);
      break;

    case 7:
      digitalWrite(led1, HIGH);
      digitalWrite(led2, HIGH);
      digitalWrite(led3, HIGH);
      break;

    case 8:
      digitalWrite(led4, HIGH);
      break;

    case 9:
      digitalWrite(led1, HIGH);
      digitalWrite(led4, HIGH);
      break;

    case 10:
      digitalWrite(led2, HIGH);
      digitalWrite(led4, HIGH);
      break;

    case 11:
      digitalWrite(led1, HIGH);
      digitalWrite(led2, HIGH);
      digitalWrite(led4, HIGH);
      break;

    case 12:
      digitalWrite(led3, HIGH);
      digitalWrite(led4, HIGH);
      break;

    case 13:
      digitalWrite(led1, HIGH);
      digitalWrite(led3, HIGH);
      digitalWrite(led4, HIGH);
      break;

    case 14:
      digitalWrite(led2, HIGH);
      digitalWrite(led3, HIGH);
      digitalWrite(led4, HIGH);
      break;

    case 15:
      digitalWrite(led1, HIGH);
      digitalWrite(led2, HIGH);
      digitalWrite(led3, HIGH);
      digitalWrite(led4, HIGH);
      break;
  }

}


}



// put function definitions here:
