#include "stdio.h"
#include "main.h"

typedef void (isr) (void);
extern void asm_timer_irq();
extern void asm_key_irq();
volatile int key_flag;
volatile int time;

void irq_init(void)
{
	timer_init(0, 65, 4);

	/* 在中断控制器里使能timer0中断 */
	VIC0INTENABLE |= (1<<23);
	VIC0INTSELECT =0;

	isr** isr_timer_array = (isr**)(0x7120015C);
	isr_timer_array[0] = (isr*)asm_timer_irq;

	/* 配置GPN0~5引脚为中断功能 */
	GPNCON &= ~(0xff);
	GPNCON |= 0xaa;
	/* 设置中断触发方式为: 下降沿触发 */
	EINT0CON0 &= ~(0xff);
	EINT0CON0 |= 0x33;
	/* 禁止屏蔽中断 */
	EINT0MASK &= ~(0x0f);
	/* 在中断控制器里使能这些中断 */
	VIC0INTENABLE |= (0x3); /* bit0: eint0~3, bit1: eint4~11 */ 

	isr** isr_key_array = (isr**)(0x71200100);
  	isr_key_array[0] = (isr*)asm_key_irq;


	/*将GPK4-GPK7配置为输出口*/
	GPKCON0 = 0x11110000;

	// set GPF14 as output
	GPFCON |= 1<<28;
	GPFCON &= ~(1<<29);
	
	/*熄灭四个LED灯*/
	GPKDATA = 0xff;
}

// timer0中断的中断处理函数
void timer_irq_handler()
{
	unsigned long uTmp;

	time = time + 1;


    //清timer0的中断状态寄存器
	uTmp = TINT_CSTAT;
	TINT_CSTAT = uTmp;
	VIC0ADDRESS=0x0;	
}

void key_irq_handler()
{
	int i = 0;
	/* 分辨是哪个中断 */
	for (i = 0; i < 4; i ++)
	{
		if (EINT0PEND & (1<<i))
		{
			key_flag = i+1;	
		}
	}
	//清中断
	EINT0PEND   = 0x3f;
	VIC0ADDRESS = 0;
}

void delay(int s)  //最小计时精度为1ms
{
	time = 0;
	// 1s = 125000hz
	TCNTB0 = 625*s;
	TCMPB0 = 0;

	// 手动更新
	TCON |= 1<<1;

	// 清手动更新位
	TCON &= ~(1<<1);

	// 默认开启自动加载和启动timer0
	TCON |= (1<<0) | (1<<3);
		

	while(time < 1)
	{
	}

	//关闭定时器
    timer_off();
}

// 初始化timer
void timer_init(unsigned long utimer,unsigned long uprescaler,unsigned long udivider)
{
	unsigned long temp0;

	// 定时器的输入时钟 = PCLK / ( {prescaler value + 1} ) / {divider value} = PCLK/(65+1)/16=62500hz

	//设置预分频系数为66
	temp0 = TCFG0;
	temp0 = (temp0 & (~(0xff00ff))) | (uprescaler<<0);
	TCFG0 = temp0;


	// 16分频
	temp0 = TCFG1;
	temp0 = (temp0 & (~(0xf<<4*utimer))& (~(1<<20))) |(udivider<<4*utimer);
	TCFG1 = temp0;


	// 使能timer0中断
	temp0 = TINT_CSTAT;
	temp0 = (temp0 & (~(1<<utimer)))|(1<<(utimer));
	TINT_CSTAT = temp0;
}


