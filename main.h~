#ifndef _MAIN_H
#define _MAIN_H
//≈‰÷√ledµ∆
#define GPKCON0     		(*((volatile unsigned long *)0x7F008800))
#define GPKDATA     			(*((volatile unsigned long *)0x7F008808))
//≈‰÷√∞¥º¸
#define GPNCON     			(*((volatile unsigned long *)0x7F008830))
#define GPNDAT     			(*((volatile unsigned long *)0x7F008834))
//≈‰÷√∑‰√˘∆˜
#define GPFCON (*(volatile unsigned int *)0x7F0080A0)
#define GPFDAT (*(volatile unsigned int *)0x7F0080A4)

#define EINT0CON0  			(*((volatile unsigned long *)0x7F008900))
#define EINT0MASK  			(*((volatile unsigned long *)0x7F008920))
#define EINT0PEND  			(*((volatile unsigned long *)0x7F008924))
#define PRIORITY 	    	(*((volatile unsigned long *)0x7F008280))
#define SERVICE     		(*((volatile unsigned long *)0x7F008284))
#define SERVICEPEND 		(*((volatile unsigned long *)0x7F008288))
#define VIC0IRQSTATUS  		(*((volatile unsigned long *)0x71200000))
#define VIC0FIQSTATUS  		(*((volatile unsigned long *)0x71200004))
#define VIC0RAWINTR    		(*((volatile unsigned long *)0x71200008))
#define VIC0INTSELECT  		(*((volatile unsigned long *)0x7120000c))
#define VIC0INTENABLE  		(*((volatile unsigned long *)0x71200010))
#define VIC0INTENCLEAR 		(*((volatile unsigned long *)0x71200014))
#define VIC0PROTECTION 		(*((volatile unsigned long *)0x71200020))
#define VIC0SWPRIORITYMASK 	(*((volatile unsigned long *)0x71200024))
#define VIC0PRIORITYDAISY  	(*((volatile unsigned long *)0x71200028))
#define VIC0ADDRESS        	(*((volatile unsigned long *)0x71200f00))

#define		PWMTIMER_BASE			(0x7F006000)
#define		TCFG0    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x00)) )
#define		TCFG1    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x04)) )
#define		TCON      	( *((volatile unsigned long *)(PWMTIMER_BASE+0x08)) )
#define		TCNTB0    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x0C)) )
#define		TCMPB0    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x10)) )
#define		TCNTO0    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x14)) )
#define		TCNTB1    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x18)) )
#define		TCMPB1    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x1C)) )
#define		TCNTO1    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x20)) )
#define		TCNTB2    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x24)) )
#define		TCMPB2    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x28)) )
#define		TCNTO2    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x2C)) )
#define		TCNTB3    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x30)) )
#define		TCMPB3    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x34)) )
#define		TCNTO3    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x38)) )
#define		TCNTB4    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x3C)) )
#define		TCNTO4    	( *((volatile unsigned long *)(PWMTIMER_BASE+0x40)) )
#define		TINT_CSTAT 	( *((volatile unsigned long *)(PWMTIMER_BASE+0x44)) )

#define buzzer_on() GPFDAT |= 1 << 14
#define buzzer_off() GPFDAT &= ~(1 << 14)
#define LED1_on() GPKDATA &= ~(1 << 4)
#define LED1_off() GPKDATA |= (1 << 4)
#define LED2_on() GPKDATA &= ~(1 << 5)
#define LED2_off() GPKDATA |= (1 << 5)
#define LED3_on() GPKDATA &= ~(1 << 6)
#define LED3_off() GPKDATA |= (1 << 6)
#define LED4_on() GPKDATA &= ~(1 << 7)
#define LED4_off() GPKDATA |= (1 << 7)
#define LEDALL_on() GPKDATA = 0x00
#define LEDALL_off() GPKDATA = 0xf0

#define timer_off() TCON &= ~(1<<0)


#endif
