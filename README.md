# DigitalElectronics2_Lab4
Timers

# Lab04: Timers
## Link GitHub:

Link to my GitHub: (https://github.com/raulgoi/DigitalElectronics2_Lab4)

## Complete the table

| **Module** | **Number of bits** | **1** | **8** | **32** | **64** | **128** | **256** | **1024** |
| ------ | -------------- | - | - | -- | -- | --- | --- | ---- |
|Timer/Counter0 | 8 | 16u | 128u | -- | 1024 | -- | 4096 |
| Timer/Counter1 | 16 | 4096 | 32768 | -- | 262144 | -- | 1048576 |
| Timer/Counter2 | 8 | 16u | 128u | 512 | 1024 | 2048 | 4096 |


## Differences between function and interrupt service routine:

 Interrupt call generated when an outside stimulus or signal come to an interrupt input of any uP. And the related interrupt rutin is run.
 
Function call is realized deleberately by the programmer in any part of the code. You write a function for a repeated part of code. And you call it when you need in the code instead of rewritting the repeated code. Besides This saves part in memory. Because the repeated code will not be repeated in the memory, instead the routin will go to the function part of the code in memory. After the function is run the program counter will turn back to the place in the original code


## Code:

    int main (void) {

    timer0_config(TMR0_PRE_64);
  
    TCLOCK  F_CPU = 16 MHz
 
    DDRC = 0x20; // Configure pin 5 as an output
  
    // Assume that port C, pin 5 is already in logic 0 state
  
    timer0_set(0); // timer 0 counter to zero
  
    PORTC |= 0x20; // Turn on the PIN
  
    // Could do some additional computations here
  
    while(timer0_get() < 250) {
  
    PORTC &= ~0x20; //Turn off the PIN
     
     }
     
  }
  
### Flowchart figure
  
  
## Knight Rider

![Lab04_Timers](https://user-images.githubusercontent.com/91128806/137778729-a83df751-49d9-4017-a108-6da652a26a29.png)



