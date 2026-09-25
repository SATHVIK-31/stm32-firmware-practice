\# STM32 LED Blinking



\## Experiment 01 — GPIO Output



This is my first STM32 firmware practice project using STM32CubeIDE and the STM32 HAL library.



\## Objective



Configure a GPIO pin as an output and control an LED using Embedded C.



\## Hardware



\- STM32F103C8T6

\- On-board / external LED

\- ST-LINK programmer/debugger



\## Software



\- STM32CubeIDE

\- STM32CubeMX

\- Embedded C

\- STM32 HAL



\## Concepts Practiced



\- GPIO configuration

\- GPIO output mode

\- GPIO SET and RESET

\- `HAL\_GPIO\_WritePin()`

\- `HAL\_Delay()`

\- Infinite `while(1)` loop



\## GPIO Configuration



| Parameter | Configuration |

|---|---|

| Microcontroller | STM32F103C8T6 |

| GPIO Port | GPIOC |

| GPIO Pin | PC13 |

| Mode | GPIO Output |

| Pull-up/Pull-down | No Pull |

| Output Speed | Low |



\## Program Logic



```text

Initialize STM32

&#x20;     ↓

Initialize GPIO

&#x20;     ↓

Set GPIO PC13 → RESET

&#x20;     ↓

Delay 1 second

&#x20;     ↓

Set GPIO PC13 → SET

&#x20;     ↓

Delay 1 second

&#x20;     ↓

Repeat continuously



Main Code

while (1)

{

&#x20;   HAL\_GPIO\_WritePin(GPIOC, GPIO\_PIN\_13, GPIO\_PIN\_RESET);

&#x20;   HAL\_Delay(1000);



&#x20;   HAL\_GPIO\_WritePin(GPIOC, GPIO\_PIN\_13, GPIO\_PIN\_SET);

&#x20;   HAL\_Delay(1000);

}

