/**
  @page CRYP_TDES_DMA  Encrypt data using TDES Algo in ECB mode, with DMA
  
  @verbatim
  ******************** (C) COPYRIGHT 2015 STMicroelectronics *******************
  * @file    CRYP/CRYP_TDES_DMA/readme.txt 
  * @author  MCD Application Team
  * @version V1.0.1
  * @date    21-September-2015
  * @brief   Description of the CRYP TDES DMA example.
  ******************************************************************************
  *
  * Redistribution and use in source and binary forms, with or without modification,
  * are permitted provided that the following conditions are met:
  *   1. Redistributions of source code must retain the above copyright notice,
  *      this list of conditions and the following disclaimer.
  *   2. Redistributions in binary form must reproduce the above copyright notice,
  *      this list of conditions and the following disclaimer in the documentation
  *      and/or other materials provided with the distribution.
  *   3. Neither the name of STMicroelectronics nor the names of its contributors
  *      may be used to endorse or promote products derived from this software
  *      without specific prior written permission.
  *
  * THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
  * AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
  * IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE
  * DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE LIABLE
  * FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL
  * DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR
  * SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER
  * CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY,
  * OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
  * OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
  *
  ******************************************************************************
  @endverbatim

@par Example Description 

This example provides a short description of how to use the CRYPTO peripheral to 
encrypt data using TDES Algorithm.

For this example, DMA is used to transfer data from memory to the CRYPTO processor
IN FIFO and also to transfer data from CRYPTO processor OUT FIFO to memory.

The data to be encrypted is a 384 bit data, which corresponds to 6 TDES Blocks.

This example behaves as follows:
- TDES Encryption   (PlainData --> EncryptedData)

STM32 Eval board's LEDs can be used to monitor the transfer status:
 - LED1 is ON when encryption is right.
 - LED3 is Toggle when encryption is wrong.
 - LED3 is ON when an initialization error occurred.

@note Care must be taken when using HAL_Delay(), this function provides accurate delay (in milliseconds)
      based on variable incremented in SysTick ISR. This implies that if HAL_Delay() is called from
      a peripheral ISR process, then the SysTick interrupt must have higher priority (numerically lower)
      than the peripheral interrupt. Otherwise the caller ISR process will be blocked.
      To change the SysTick interrupt priority you have to use HAL_NVIC_SetPriority() function.
      
@note The application needs to ensure that the SysTick time base is always set to 1 millisecond
      to have correct HAL operation.

@par Directory contents 

  - CRYP/CRYP_TDES_DMA/Inc/stm32f7xx_hal_conf.h    HAL configuration file
  - CRYP/CRYP_TDES_DMA/Inc/stm32f7xx_it.h          Interrupt handlers header file
  - CRYP/CRYP_TDES_DMA/Inc/main.h                  Header for main.c module  
  - CRYP/CRYP_TDES_DMA/Src/stm32f7xx_it.c          Interrupt handlers
  - CRYP/CRYP_TDES_DMA/Src/main.c                  Main program
  - CRYP/CRYP_TDES_DMA/Src/stm32f7xx_hal_msp.c     HAL MSP module
  - CRYP/CRYP_TDES_DMA/Src/system_stm32f7xx.c      STM32F7xx system source file

@par Hardware and Software environment

  - This example runs on STM32F756xx devices.

  - This example has been tested with STM32756G-EVAL board revB and can be
    easily tailored to any other supported device and development board.
 
  - STM32756G-EVAL Set-up :
    - To use LED1, ensure that JP24 is in position 2-3
    - To use LED3, ensure that JP23 is in position 2-3
    
@par How to use it ? 

In order to make the program work, you must do the following:
 - Open your preferred toolchain 
 - Rebuild all files and load your image into target memory
 - Run the example


 * <h3><center>&copy; COPYRIGHT STMicroelectronics</center></h3>
 */
