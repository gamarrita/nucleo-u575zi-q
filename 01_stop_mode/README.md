### <b>01_stop_mode Description</b>
The STM32 runs in active mode x mili-seconds and go to lo power
mode y seconds. The blue LED will be on during active mode.
<br>
<br>
### <b>Measures</b>
1) Stop mode 2 current consumption 7.8 uA
<br>
<br>
### <b>Tricks a tips</b>
1) Some When using RTC in Stop0/1/2 we must enable RTC autonomous mode by:
   __HAL_RCC_RTCAPB_CLKAM_ENABLE();
2) In stop mode 2 and deeper systick clock will be halted, in others low
   power modes systick keeps running and interrups will wake up STM32, so to
   not abort low power mode following code will be needed:
   HAL_SuspendTick();
   ... // go to low power mode code.
   HAL_ResumeTick();
<br>
<br>
### <b>Keywords</b>
STM32, nucleo-575, low power, stop mode.
<br>
<br>
### <b>Hardware and Software environment</b>
  - This example runs on STM32U575xx devices.
  - This example has been tested with STMicroelectronics NUCLEO-U575ZI-Q


