.. zephyr:board:: agafia_sg0 
   :soc: stm32g0
   :arch: arm
   :soc-variant: stm32g071cb

Overview
********
The Agafia G071CB board features an ARM Cortex-M0+ based STM32G071CB MCU
with a wide range of connectivity support and configurations. Here are
some highlights of the board:

- STM32 microcontroller in LQFP48 package
- Two types of extension resources:

  - Arduino Uno V3 connectivity 
  - MikroBUS* connectivity via Proto-shield*

- On-board ST-LINK/V2-1 debugger/programmer with SWD connector
- Flexible board power supply:

   - USB VBUS or external source(3.3V, 5V, 7 - 12V)
   - Power management access point

- Four LEDs:  USB (PWR), USER, LED1 (PF1), LED2 (PF2)
- Two push-buttons: USER and RESET
- One 32.768 kHz crystal oscillator

Hardware
********
Agafia G071CB provides the following hardware components:

- STM32 microcontroller in LQFP48 package
- Two types of extension resources:

  - Arduino* Uno V3 connectivity
  - Extension pin headers for full access to all remaining STM32 I/Os

- On-board ST-LINK/V2-1 debugger/programmer with SWD connector:

  - Selection-mode switch to use the kit as a standalone ST-LINK/V2-1

- Flexible board power supply:

  - USB VBUS or external source (3.3V, 5V, 7 - 12V)
  - Power management access point

- Three User LEDs:

  - LED (PC13), LED1 (PF1), LED2 (PF2)

- One push-buttons: RESET 
 

More information about STM32G071CB can be found here:

- `G071CB on www.st.com`_
- `STM32G071 reference manual`_


Supported Features
==================

.. zephyr:board-supported-hw::

Connections and IOs
===================

Each of the GPIO pins can be configured by software as output (push-pull or open-drain), as
input (with or without pull-up or pull-down), or as peripheral alternate function. Most of the
GPIO pins are shared with digital or analog alternate functions. All GPIOs are high current
capable except for analog inputs.

Default Zephyr Peripheral Mapping:
----------------------------------

- UART_1 TX/RX : PA9/PA10 
- UART_2 TX/RX : PA2/PA3 (Arduino Serial)
- I2C1 SCL/SDA : PB8/PB9 (Arduino I2C)
- I2C2 SCL/SDA : PA11/PA12
- SPI1 NSS/SCK/MISO/MOSI : PB0/PA5/PA6/PA7 (Arduino SPI)
- SPI2 NSS/SCK/MISO/MOSI : PB12/PB13/PB14/PB15
- LD4       : PA5
- User Key  : PB6
- PWM       : PA6
- ADC1 IN0  : PB1
- ADC1 IN1  : PB2
- DAC1_OUT1 : PA4
 

Programming and Debugging
*************************

AGAFIA G071CB board includes an ST-LINK/V3 embedded debug tool interface.

Applications for the ``agafia_sg0`` board configuration can be built and
flashed in the usual way (see :ref:`build_an_application` and
:ref:`application_run` for more details).

Flashing
========

The board is configured to be flashed using west `STM32CubeProgrammer`_ runner,
so its :ref:`installation <stm32cubeprog-flash-host-tools>` is required.

Alternatively, OpenOCD, JLink, or pyOCD can also be used to flash the board using
the ``--runner`` (or ``-r``) option:

.. code-block:: console

   $ west flash --runner openocd
   $ west flash --runner jlink
   $ west flash --runner pyocd

Flashing an application
----------------------------------------

Here is an example for the :zephyr:code-sample:`blinky` application.

.. zephyr-app-commands::
   :zephyr-app: samples/basic/blinky
   :board: agafia_sg0
   :goals: build flash

You will see the LED blinking every second.

Debugging
=========

You can debug an application in the usual way.  Here is an example for the
:zephyr:code-sample:`hello_world` application.

.. zephyr-app-commands::
   :zephyr-app: samples/hello_world
   :board: agafia_sg0
   :maybe-skip-config:
   :goals: debug

References
**********

.. target-notes::

.. _Agafia SG0 website:
   https://www.agafia.ca

.. _STM32G071 reference manual:
   https://www.st.com/resource/en/reference_manual/dm00371828.pdf
 
.. _G071CB on www.st.com:
   https://www.st.com/en/microcontrollers/stm32g071cb.html

.. _STM32CubeProgrammer:
   https://www.st.com/en/development-tools/stm32cubeprog.html
