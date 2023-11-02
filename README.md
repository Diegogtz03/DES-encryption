# DES-encryption
DES python encryption example

- Para correr el código simplemente se necesita ejecutar el siguiente comando: `python3 encrypt.py`
- El programa solicita el texto a encriptar, solo es necesario introducir el texto y presionar `Enter`


**Ejemplos**
------
1.
Texto a encriptar: texto123
*Encryption*

Plain Text :  texto123

After initial permutation 1FED1BB200FF14D0

Cipher Text :  9305E71454223845

*Decryption*

Result:  texto123

---
2. 
*Encryption*

Plain Text :  Hola Mun

After initial permutation EF40E66A00DEA782

Plain Text :  do!     

After initial permutation 0300030600FF0202

Cipher Text :  D912C6F724091DD3DF7A0C63CAE62377

*Decryption*

Result:  Hola Mundo! 

---


**Explicación**
------
1. La llave (string hexadecimal de 16 caracteres) es convertida a binario para después permutar de 64 a 56 bits
2. La llave posteriormente se divide 16 veces en mitades, se intercambian los bits, y permutan de 56 a 48 bits
3. En caso de encriptar un texto, el texto primero se divide en bloques de 64 bits, es decir, de 8 caracteres, si no completa, se rellena con espacios
4. Cada bloque se traduce a Hexadecimal y se pasa a encriptar junto con la llave previamente procesada
5. En el proceso de encriptación, perimero se permuta el texto a 64 bits
6. Se divide el texto en mitades iguales
7. En un proceso de repetición de 16 veces, la mitad derecha permuta de 32 a 48 bits
8. Se aplica un proceso de XOR junto con la llave previamente procesada
9. Se realiza un proceso de S-Box sobre los datos previos
10. Permuta de nuevo a 32 bits y se hace un proceso de XOR con la mitad izquierda
11. El resultado combinado es el texto cifrado
12. En el caso de desecriptar, se aplica el mismo proceso solamente saltando la parte de la conversión a hexadecimal y utilizando el opuesto de la llava procesada
