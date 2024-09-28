#include "stdio.h"
#include "main.h"


void timer_init(unsigned long utimer,unsigned long uprescaler,unsigned long udivider);

void work_mode(void);
void set_mode(void);
void delay(int ms);

extern int key_flag = 0;

volatile int mode;

void allClose()
{
	LEDALL_off();
   	timer_off();
   	buzzer_off();
	
}

void k1()
{
	LED2_on();LED3_on();delay(200);LED2_off();LED3_off();delay(20);
      LED2_on();LED3_on();delay(20);LED2_off();LED3_off();delay(20);  //LED2闪烁，LED3闪烁
      LED2_on();LED3_on();delay(20);LED2_off();LED3_off();delay(20);
      LED2_on();LED3_on();delay(20);LED2_off();LED3_off();delay(20);
      LED1_on();LED4_on();delay(200);LED1_off();LED4_off();delay(20);
      LED1_on();LED4_on();delay(20);LED1_off();LED4_off();delay(20);  //LED1闪烁，LED4闪烁
      LED1_on();LED4_on();delay(20);LED1_off();LED4_off();delay(20);
      LED1_on();LED4_on();delay(20);LED1_off();LED4_off();delay(20);
      LED2_on();LED3_on(); 	
}

void k2()
{
	LED2_on();LED3_on();delay(100);LED2_off();LED3_off();delay(20);
      LED2_on();LED3_on();delay(20);LED2_off();LED3_off();delay(20);  //LED2闪烁，LED3闪烁
      LED2_on();LED3_on();delay(20);LED2_off();LED3_off();delay(20);
      LED2_on();LED3_on();delay(20);LED2_off();LED3_off();delay(20);
      LED1_on();LED4_on();delay(100);LED1_off();LED4_off();delay(20);
      LED1_on();LED4_on();delay(20);LED1_off();LED4_off();delay(20);  //LED1闪烁，LED4闪烁
      LED1_on();LED4_on();delay(20);LED1_off();LED4_off();delay(20);
      LED1_on();LED4_on();delay(20);LED1_off();LED4_off();delay(20);
}

void k3()
{
	LED2_on();LED3_on();delay(50);LED2_off();LED3_off();delay(20);
      LED2_on();LED3_on();delay(20);LED2_off();LED3_off();delay(20);  //LED2闪烁，LED3闪烁
      LED2_on();LED3_on();delay(20);LED2_off();LED3_off();delay(20);
      LED2_on();LED3_on();delay(20);LED2_off();LED3_off();delay(20);
      LED1_on();LED4_on();delay(200);LED1_off();LED4_off();delay(20);
      LED1_on();LED4_on();delay(20);LED1_off();LED4_off();delay(20);  //LED1闪烁，LED4闪烁
      LED1_on();LED4_on();delay(20);LED1_off();LED4_off();delay(20);
      LED1_on();LED4_on();delay(20);LED1_off();LED4_off();delay(20);
}

void success_k1()
{
	LEDALL_on();
      delay(200);	//2s延时
      LEDALL_off();
      delay(200);	//2s延时
      LEDALL_on();
      delay(200); //2s延时
      LEDALL_off();
	key_flag = 0;
	mode = 1;
}
void success_k2()
{
	buzzer_on();
      delay(100);		//1s延时
      buzzer_off();
      delay(100);		//1s延时
      buzzer_on();
	delay(100);		//1s延时
	buzzer_off();
	key_flag = 0;
	mode = 2;	
}

void success_k3()
{
	LEDALL_on();
	buzzer_on();
      delay(20);
      LEDALL_off();
	delay(20);
      LEDALL_on();
      delay(20);
      LEDALL_off();
	delay(20);
      LEDALL_on();
      delay(20);
      LEDALL_off();
	buzzer_off();
	key_flag = 0;
	mode = 3;
}

int main()
{
    mode = 2;
    work_mode();
    while (1)
    {
    }

    return 0;
}

void work_mode(void)
{
    allClose();   
    switch (mode)
    {
    case 1: // 模式1动作代码
	while(1)
	{
		k1();
	}
        break;
    case 2: // 模式2动作代码
       while(1)
         {
            k2();         
        } 
        break;
    case 3: // 模式3动作代码
       while(1)
         {
            k3();          
        }  
        break;
    default:
        break;
    }
}

void set_mode(void)
{
    allClose();
    while (1)
    {
        switch (key_flag)
        {
        case 1: // 按键1按下动作代码
            success_k1();
		break;
	
        case 2: // 按键2按下动作代码
        	success_k2();
            break;

        case 3: // 按键3按下动作代码
            success_k3();
            break;
        default:
            break;
        }
    }
}
