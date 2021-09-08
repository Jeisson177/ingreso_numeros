--Codigo creado para guardar y encender los leds de los numeros ingresados

LIBRARY IEEE;
USE ieee.std_logic_1164.all;
--------------------------------------------------
ENTITY ingreso_numeros IS
 PORT(    ledA   : OUT STD_LOGIC_VECTOR(6 DOWNTO 0);--Bits para encender los segmentos del numero A
          ledB   : OUT STD_LOGIC_VECTOR(6 DOWNTO 0);--Bits para encender los segmentos del numero B
			 swA    : IN  STD_LOGIC_VECTOR(3 DOWNTO 0);--Switchs para definir el numero A
			 swB    : IN  STD_LOGIC_VECTOR(3 DOWNTO 0));--Switchs para definir el numero B
END ENTITY ingreso_numeros;
--------------------------------------------------
ARCHITECTURE display OF ingreso_numeros IS
BEGIN
	 
   with swA select-- Se realiza un with select teniendo el cuenta el swA
	ledA <=--Dependiendo de este se le asigna un valor al ledA para encender los segmentos
	 "1000000" WHEN  "0000",
	 "1111001" WHEN  "0001",
	 "0100100" WHEN  "0010",
	 "0110000" WHEN  "0011",
	 "0011001" WHEN  "0100",
	 "0010010" WHEN  "0101",
	 "0000010" WHEN  "0110",
	 "1111000" WHEN  "0111",
	 "0000000" WHEN  "1000",
	 "0011000" WHEN  "1001",
	 "0000110" WHEN  OTHERS;
	 
	 with swB select--Se realiza un with select teniendo en cuenta el swB
	ledB <=--Dependiendo de este se le asigna un valor al ledB
	 "1000000" WHEN  "0000",
	 "1111001" WHEN  "0001",
	 "0100100" WHEN  "0010",
	 "0110000" WHEN  "0011",
	 "0011001" WHEN  "0100",
	 "0010010" WHEN  "0101",
	 "0000010" WHEN  "0110",
	 "1111000" WHEN  "0111",
	 "0000000" WHEN  "1000",
	 "0011000" WHEN  "1001",
	 "0000110" WHEN  OTHERS;
	 
END ARCHITECTURE display; 
