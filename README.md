# LMIC for Nucleo L152RE

- LMIC code obtained from here: https://www.research.ibm.com/labs/zurich/ics/lrsc/lmic.html
- CMSIS git cloned from here: https://github.com/ARM-software/CMSIS_5
- `STM32L152RE_FLASH.ld` file was obtained from the Internet and copied to the `lmic/stm32` directory
- Paths are set in `lmic/examples/projects.gmk`

## Build
- Go to `examples/hello`
- Run `make`
- Plug the Nucleo L152RE board in USB
- Copy `exmples/hello/build/hello.bin` to `/media/drasko/NODE_L152RE` (replace this by your mount point of USB storage)
- Open Minicom:
```
minicom -D /dev/ttyACM0
```
- In `./stm32/debug.c` we can see: `USART1->BRR = 277; // 115200`. So set-up this baud rate in Minicom.
- According to [this pinout image]https://developer.mbed.org/platforms/ST-Nucleo-L152RE/, UART1_TX is on PA_9 that is on the 11th pin from the top on outer connector (ST extension connector, male, next to inner Arduino connector). So connect your UART RX (the one on PC USB FTDI adpter) to this pin. GND is located near to PA_9, on pin 10 of the most outer connector row.

