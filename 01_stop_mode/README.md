## <b>01_stop_mode Description</b>


### <b>Measures</b>
1) Stop mode 2 current consumption 7.8 uA
2)

### <b>Tricks a tips</b>
  
  
Tricks a tips:
  
1) Some When using RTC in Stop0/1/2 we must enable RTC autonomous mode by:
   __HAL_RCC_RTCAPB_CLKAM_ENABLE();
  
2) In stop mode 2 and deeper systick clock will be halted, in others low
   power modes systick keeps running and interrups will wake up STM32, so to
   not abort low power mode following code will be needed:
   HAL_SuspendTick();
   ... // go to low power mode code.
   HAL_ResumeTick();


### <b>Keywords</b>

STM32, nucleo-575, low power, stop mode.

### <b>Directory contents</b>

  
### <b>Hardware and Software environment</b>

  - This example runs on STM32U575xx devices.
  - In this example, the clock is set to 160 MHz.

  - This example has been tested with STMicroelectronics NUCLEO-U575ZI-Q
    board and can be easily tailored to any other supported device 
    and development board.

  - NUCLEO-U575ZI-Q Set-up
    - Connect the external signal to measure to the TIM1 CH2 pin (PE.11 (pin 6 in CN10 connector)).

### <b>How to use it ?</b>


