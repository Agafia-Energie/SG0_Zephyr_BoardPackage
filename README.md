# Agafia-SG0+ Zephyr Framework Setup under PlatformIO

Welcome to the Agafia-SG0+ board setup guide for the Zephyr framework. Using Zephyr, you can follow these steps to get started with embedded development on Agafia-SG0+.

## Installation Steps

1. **Install CMake**  
   Download and install CMake from the [Cygwin website](https://cygwin.com/install.html).

2. **Install PlatformIO**  
   Ensure PlatformIO is installed on your system.

3. **Create a Sample STM32-Based Project**  
   Create a sample project for any STM32-based board in PlatformIO. This step allows PlatformIO to install the necessary STM32 board files.

4. **Modify Board Configuration**  
   - Navigate to:
     ```
     C:\Users\username\.platformio\platforms\ststm32\boards\agafia_sg0.json
     ```
   - Open `agafia_sg0.json` and add **Zephyr** under the `frameworks` tag:

     ```json
     "frameworks": [
         "arduino",
         "cmsis",
         "libopencm3",
         "stm32cube",
         "zephyr"
     ]
     ```

   - Save the file.

5. **Copy Board Package Installation Files**  
   - Locate the board package installation files in:
     ```
     /boardfiles/agafiasg0
     ```
   - Copy the `agafiasg0` folder and paste it into:
     ```
     C:\Users\username\.platformio\packages\framework-zephyr\boards\st
     ```

6. **Restart VS Code**  
   - Close and reopen Visual Studio Code.
   - Create a new PlatformIO project for the **Agafia-SG0+** board.
   - Select the **Zephyr** framework.

7. **Write, Compile, and Run Code**  
   Use example projects to write, compile, and execute code on the Agafia-SG0+ board.
