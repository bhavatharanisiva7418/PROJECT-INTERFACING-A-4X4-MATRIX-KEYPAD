# PROJECT-INTERFACING-A-4X4-MATRIX-KEYPAD
## AIM:
To Interface a 4X4 matrix keypad and show the output on 16X2 LCD display to ARM controller , and simulate it in Proteus
## Components required:
STM32 CUBE IDE, Proteus 8 simulator .
## Theory:

![image](https://github.com/user-attachments/assets/bd6d6ca8-3918-4947-97cf-f688710776d8)
4×4 Keypad Module Pin Diagram

4x4 Keypad module Pin Diagram 4×4 Keypad module Pin Diagram Pin Number Pin Name
Description 1 R1 Taken out from 1st ROW 2 R2 Taken out from 2nd ROW 3 R3 Taken out
from 3rd ROW 4 R4 Taken out from 4th ROW 5 C1 Taken out from 1st COLUMN 6 C2 Taken
out from 2nd COLUMN 7 C3 Taken out from 3rd COLUMN 8 C4 Taken out from 4th COLUMN 
4×4 Matrix Keypad Module Hardware Overview These Keypad modules are made of thin,
flexible membrane material. The 4 x4 keypad module consists of 16 keys, these Keys are
organized in a matrix of rows and columns. All these switches are connected to each other
with a conductive trace. Normally there is no connection between rows and columns. When 
we will press a key, then a row and a column make contact.

## Procedure :

## LCD 16X2

16×2 LCD is named so because; it has 16 Columns and 2 Rows. There are a lot of combinations available like, 8×1, 8×2, 10×2, 16×1, etc. But the most used one is the 16*2 LCD, hence we are using it here

All the above mentioned LCD display will have 16 Pins and the programming approach is also the same and hence the choice is left to you. Below is the Pinout and Pin Description of 16x2 LCD Module:
![image](https://github.com/user-attachments/assets/a6ee9ed0-9011-4e91-a902-cf5916cac5e5)
![image](https://github.com/user-attachments/assets/25216faa-5fd8-462d-931b-3f74ce2ddf4f)
![image](https://github.com/user-attachments/assets/23c8ce30-d0f6-4ae2-b5e1-f485b3ce3a1b)

4-bit and 8-bit Mode of LCD:

The LCD can work in two different modes, namely the 4-bit mode and the 8-bit mode. In 4 bit mode we send the data nibble by nibble, first upper nibble and then lower nibble. For those of you who don’t know what a nibble is: a nibble is a group of four bits, so the lower four bits (D0-D3) of a byte form the lower nibble while the upper four bits (D4-D7) of a byte form the higher nibble. This enables us to send 8 bit data.

Whereas in 8 bit mode we can send the 8-bit data directly in one stroke since we use all the 8 data lines.

8-bit mode is faster and flawless than 4-bit mode. But the major drawback is that it needs 8 data lines connected to the microcontroller. This will make us run out of I/O pins on our MCU, so 4-bit mode is widely used. No control pins are used to set these modes. LCD Commands:

There are some preset commands instructions in LCD, which we need to send to LCD through some microcontroller. Some important command instructions are given below:

Hex Code

Command to LCD Instruction Register

0F

LCD ON, cursor ON

01

Clear display screen

02

Return home

04

Decrement cursor (shift cursor to left)

06

Increment cursor (shift cursor to right)

05

Shift display right

07

Shift display left

0E

Display ON, cursor blinking

80

Force cursor to beginning of first line

C0

Force cursor to beginning of second line

38

2 lines and 5×7 matrix

83

Cursor line 1 position 3

3C

Activate second line

08

Display OFF, cursor OFF

C1

Jump to second line, position 1

OC

Display ON, cursor OFF

C1

Jump to second line, position 1

C2

Jump to second line, position 2

## Procedure:
1.click on debug option
![image](https://github.com/user-attachments/assets/fa1342cb-cb55-41ee-bc7a-0b218db5facd)
2.click on FILE, click on new stm 32 project
![image](https://github.com/user-attachments/assets/d4744806-5ae9-4432-9f49-e3053354e401)
![image](https://github.com/user-attachments/assets/ed248037-6ac3-441a-8511-86478cc5fd9d)
3.select the target to be programmed as shown below and click on next
![image](https://github.com/user-attachments/assets/1fb8c3e5-d403-4927-b2f8-20251a763dfc)
4.select the program name
![image](https://github.com/user-attachments/assets/87e61adc-e8cb-4157-b072-ca17da345bbe)
5.corresponding ioc file will be generated automatically
![image](https://github.com/user-attachments/assets/45f286d7-829f-4ffe-98c8-40181a73a5d3)
6.select the appropriate pins as gipo, in or out, USART or required options and configure
![image](https://github.com/user-attachments/assets/284b283b-c842-4a5b-98ba-dfa2d0d62f02)
![image](https://github.com/user-attachments/assets/14132bb4-ebb4-4a02-ac6d-00caf43b4768)
7.click on cntrl+S , automaticall C program will be generated
![image](https://github.com/user-attachments/assets/f6232417-7fbe-496c-bf23-ce9b8e241937)
![image](https://github.com/user-attachments/assets/feca6749-a25f-418e-b5f3-0f50d1c42fae)
8. edit the program and as per required
![image](https://github.com/user-attachments/assets/07535ff9-3cb7-4a73-86a7-29a82ace4b3d)
9.Add necessary library files of LCD 16x2 , write the program and use project and build
![image](https://github.com/user-attachments/assets/8ce2b2d2-ceee-45be-a37e-cdc976f110ec)
10. once the project is bulild
![image](https://github.com/user-attachments/assets/6000356a-1342-4f15-ab3c-02b53d23ca82)

11.click on debug option 

![image](https://github.com/user-attachments/assets/688151bd-e900-479f-b6fb-c227badee701)

12.Creating Proteus project and running the simulation We are now at the last part of step by step guide on how to simulate STM32 project in Proteus.

13.Create a new Proteus project and place STM32F40xx i.e. the same MCU for which the project was created in STM32Cube IDE.

14.After creation of the circuit as per requirement as shown below

![image](https://github.com/user-attachments/assets/30f1af11-e337-4e00-a9d5-edf48cac2e95)

15.Double click on the the MCU part to open settings. Next to the Program File option, give full path to the Hex file generated using STM32Cube IDE. Then set the external crystal frequency to 8M (i.e. 8 MHz). Click OK to save the changes. https://engineeringxpert.com/wp-content/uploads/2022/04/26.png

16.click on debug and simulate using simulation as shown below

![image](https://github.com/user-attachments/assets/926fefd5-9703-4759-bd16-62dba70f5ad9)
![image](https://github.com/user-attachments/assets/55d9534e-ceec-46f4-ada5-faa27f164223)

## STM 32 CUBE PROGRAM :
```
#include "main.h"
#include <stdbool.h>
#include "lcd.h"
bool row1,row2,row3,row4;
void key();
void SystemClock_Config(void);
static void MX_GPIO_Init(void);
int main(void)
{
  HAL_Init();
  SystemClock_Config();
  MX_GPIO_Init();
  while (1)
  {
	  key();
	  HAL_Delay(500);
  }
}
void key()
{
	Lcd_PortType ports[] = { GPIOA, GPIOA, GPIOA, GPIOA };
	Lcd_PinType pins[] = {GPIO_PIN_3, GPIO_PIN_2, GPIO_PIN_1, GPIO_PIN_0};
	Lcd_HandleTypeDef lcd;
	lcd = Lcd_create(ports, pins, GPIOB, GPIO_PIN_0, GPIOB, GPIO_PIN_1, LCD_4_BIT_MODE);

	HAL_GPIO_WritePin(GPIOC,GPIO_PIN_4,GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC,GPIO_PIN_5,GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC,GPIO_PIN_6,GPIO_PIN_SET);
	HAL_GPIO_WritePin(GPIOC,GPIO_PIN_7,GPIO_PIN_RESET);

	row1 =HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_0);
	row2 =HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_1);
	row3 =HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_2);
	row4 =HAL_GPIO_ReadPin(GPIOC,GPIO_PIN_3);
 	if(!row1)
	{
		Lcd_cursor(&lcd,0,1);
		Lcd_string(&lcd, "key\\n");
		row1=1;
	}
	if(!row2)
		{
			Lcd_cursor(&lcd,0,1);
			Lcd_string(&lcd, "key*\n");
			row2=1;
		}
	if(!row3)
		{
			Lcd_cursor(&lcd,0,1);
			Lcd_string(&lcd, "key-\n");
			row3=1;
		}
	if(!row4)
		{
			Lcd_cursor(&lcd,0,1);
			Lcd_string(&lcd, "key+\n");
			row4=1;
		}
	HAL_Delay(500);

	}
```

## Output screen shots of proteus :

![Screenshot 2025-04-28 084457](https://github.com/user-attachments/assets/21c02598-6cc9-49fa-b37a-496fa0251a09)

## CIRCUIT DIAGRAM

![image](https://github.com/user-attachments/assets/cf3049a6-b834-4a97-aecc-29f1ec5ea189)

## Result :
Interfacing a 4x4 keypad with ARM microcontroller are simulated in proteus and the results are verified.





