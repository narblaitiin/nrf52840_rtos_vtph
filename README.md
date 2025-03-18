# Code for 6Sens Project : conversion and storage application of MDBT50Q SoC ADC (AIN1 - P0.03) and SHT31 sensor (I2C)

## Overview
This first code allows us to convert a voltage and digital values and adds processing to it:

 - take sample of battery level (Analog-to-Digital), temperature and humidity levels (serial data)
 - store the different values in an area of partitioned external QPSI flash memory (kbytes at the end of flash memory)

This allows us to test SHT31 ennvironmental sensor and the internal ADC of the MDBT50Q. The final goal will be to send the samples to a lorawan server and clear the memory location once a day.

## Building and Running
The following commands clean build folder, build and flash the sample:

**Command to use**

west build -t pristine

west build -p always -b mdbt50q_lora_dev applications/nrf52840_rtos_vtph

west flash --runner pyocd