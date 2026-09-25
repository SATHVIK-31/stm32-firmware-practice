# STM32 LED Blinking

## Experiment 01 — GPIO Output

This is my first STM32 firmware practice project using STM32CubeIDE and the STM32 HAL library.

## Objective

Configure a GPIO pin as an output and control an LED using Embedded C.

## Hardware

- STM32F103C8T6
- On-board / external LED
- ST-LINK programmer/debugger

## Software

- STM32CubeIDE
- STM32CubeMX
- Embedded C
- STM32 HAL

## Concepts Practiced

- GPIO configuration
- GPIO output mode
- GPIO SET and RESET
- `HAL_GPIO_WritePin()`
- `HAL_Delay()`
- Infinite `while(1)` loop

## GPIO Configuration

| Parameter | Configuration |
|---|---|
| Microcontroller | STM32F103C8T6 |
| GPIO Port | GPIOC |
| GPIO Pin | PC13 |
| Mode | GPIO Output |
| Pull-up/Pull-down | No Pull |
| Output Speed | Low |

## Program Logic


Initialize STM32
      ↓
Initialize GPIO
      ↓
Set GPIO PC13 → RESET
      ↓
Delay 1 second
      ↓
Set GPIO PC13 → SET
      ↓
Delay 1 second
      ↓
Repeat continuously

Main Code
while (1)
{
    HAL_GPIO_WritePin(GPIOC, GPIO_PIN_13, GPIO_PIN_RESET);
    HAL_Delay(1000);

    HAL_GPIO_WritePin(GPIOC, GPIO_PIN_13, GPIO_PIN_SET);
    HAL_Delay(1000);
}

HAL Functions Used
HAL_GPIO_WritePin()
Used to set or reset a GPIO output pin.
HAL_GPIO_WritePin(GPIOC, GPIO_PIN_13, GPIO_PIN_SET);

HAL_Delay()
Creates a delay in milliseconds.
HAL_Delay(1000);

1000 ms = 1 second
Expected Output
The LED continuously toggles between ON and OFF with a 1-second delay.
What I Learned
- How to configure GPIO using STM32CubeMX.
- How STM32CubeIDE generates initialization code.
- How to control GPIO pins using STM32 HAL.
- How GPIO_PIN_SET and GPIO_PIN_RESET control the output.
- How an embedded while(1) loop is used for continuous operation.
Status
✅ Completed
