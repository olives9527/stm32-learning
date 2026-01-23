# stm32-learning
STM32F103 learning notes from scratch (freshman）
# My STM32 Journey 🚀

## Day 1 — Entering the World of STM32

Today is my **first day learning STM32**.

I am a freshman, and before this I:
- Had learned C language
- Had **never learned microcontrollers**
- Did not understand concepts like GPIO, registers, or binary

At the beginning, I felt confused.

---

## My First Clear Understanding ✨

Today, I clearly understood **one very important thing**:

> The LED on my STM32F103 board is connected to **PC13**.

This means:
- PC13 is a **real physical pin**
- When I control PC13 in code, the LED changes in the real world

This was the first time I truly felt:
> **Code can control reality.**

---

## What I Learned Today

- STM32 is a small computer used to control hardware
- GPIO is how the chip interacts with the outside world
- PC13 is not just a name — it is a real pin connected to an LED

I did not write much code today,  
but I **built a clear mental model**, which feels very meaningful.

---

## My Plan



- Learn STM32 step by step
- Focus on understanding, not memorizing
- Record my learning process honestly

This is just the beginning.



# Day 2 – Understanding GPIO Configuration

Today I learned how to configure a GPIO pin step by step.

I used the Standard Peripheral Library (not HAL yet).
The key things I learned are:

- The GPIO peripheral must be enabled by RCC before use
- GPIO configuration is done using a structure
- The configuration is written into hardware registers
- Setting or resetting a pin directly changes the LED state

Here is the code I studied today:

```c
RCC_APB2PeriphClockCmd(RCC_APB2Periph_GPIOC, ENABLE);

GPIO_InitTypeDef GPIO_InitStructure;
GPIO_InitStructure.GPIO_Mode = GPIO_Mode_Out_PP;
GPIO_InitStructure.GPIO_Pin = GPIO_Pin_13;
GPIO_InitStructure.GPIO_Speed = GPIO_Speed_50MHz;

GPIO_Init(GPIOC, &GPIO_InitStructure);

GPIO_SetBits(GPIOC, GPIO_Pin_13);
// GPIO_ResetBits(GPIOC, GPIO_Pin_13);




