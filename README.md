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
- In `./stm32/debug.c` we can see: `USART1->BRR = 277; // 115200`

