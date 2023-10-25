# 3.3-Conceptos-
<pre>

	<p align=center>

Tecnológico Nacional de México
Instituto Tecnológico de Tijuana

Departamento de Sistemas y Computación
Ingeniería en Sistemas Computacionales

Semestre:
Agosto - Diciembre 2023

Materia:
Lenguajes de interfaz

Docente:
M.C. Rene Solis Reyes 

Unidad:
3

Título del trabajo:
3.3 Conceptos

Estudiante:
Marquez Santillan Jose Eduardo 21210395

	</p>

</pre>

<pre>

	<p align=left>
//----------------------------------------------------------------------Codigo en Arduino----------------------------------------------------------------------------
/*
Nombre del Archivo: Arduino
Autor:   Marquez Santillan Jose Eduardo
Correo:  l21210395@tectijuana.edu.mx
Fecha:   24/10/2023
Curso:   Lenguajes de Interfaz, TECNM Campus ITT
Objetivo:
Este programa Se ejecuta una tabla ascil
Historial de Revisiones:
23/10/2023        Marquez Santillan Jose Eduardo
*/

void setup() {
  //Initialize serial and wait for port to open:
  Serial.begin(9600);
  while (!Serial) {
    ;  // wait for serial port to connect. Needed for native USB port only
  }

  // prints title with ending line break
  Serial.println("ASCII Table ~ Character Map");
}

// first visible ASCIIcharacter '!' is number 33:
int thisByte = 33;
// you can also write ASCII characters in single quotes.
// for example, '!' is the same as 33, so you could also use this:
// int thisByte = '!';

void loop() {
  // prints value unaltered, i.e. the raw binary version of the byte.
  // The Serial Monitor interprets all bytes as ASCII, so 33, the first number,
  // will show up as '!'
  Serial.write(thisByte);

  Serial.print(", dec: ");
  // prints value as string as an ASCII-encoded decimal (base 10).
  // Decimal is the default format for Serial.print() and Serial.println(),
  // so no modifier is needed:
  Serial.print(thisByte);
  // But you can declare the modifier for decimal if you want to.
  // this also works if you uncomment it:

  // Serial.print(thisByte, DEC);


  Serial.print(", hex: ");
  // prints value as string in hexadecimal (base 16):
  Serial.print(thisByte, HEX);

  Serial.print(", oct: ");
  // prints value as string in octal (base 8);
  Serial.print(thisByte, OCT);

  Serial.print(", bin: ");
  // prints value as string in binary (base 2) also prints ending line break:
  Serial.println(thisByte, BIN);

  // if printed last visible character '~' or 126, stop:
  if (thisByte == 126) {  // you could also use if (thisByte == '~') {
    // This loop loops forever and does nothing
    while (true) {
      continue;
    }
  }
  // go on to the next character
  thisByte++;
}
//---------------------------------------------------------------Codigo en Wokwi-----------------------------------------------------------------------------------
//Hola mundo
//Marquez Santillan Jose Eduardo
//24/10/2023
//Imprimir Hola Mundo

#include <stdio.h>
#include "pico/stdlib.h"

int main() {
  stdio_init_all();
  while (true) {
    printf("Hello, Wokwi!\n");
    sleep_ms(250);
  }
}
