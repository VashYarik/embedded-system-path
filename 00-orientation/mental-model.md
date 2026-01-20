# Firmware Mental Model

## High-level view
I currently think of firmware as the layer that sits between the hardware and any higher-level software. Its main role is to bring the system into a known, working state and then continuously manage hardware resources in a predictable way.

## What happens when power is applied
When power is applied to a microcontroller, execution starts from a predefined location in memory. The firmware is responsible for initializing the system, setting up memory, configuring peripherals, and eventually running the main application logic.

At this stage, there is no operating system unless the firmware explicitly includes one or runs on top of a real-time operating system (RTOS).

## Where my code fits
My code lives as part of the firmware image stored in the device’s non-volatile memory. In the case of ESP-IDF, my application code begins execution at the `app_main()` function, which is called after lower-level system initialization has already occurred.

## How firmware interacts with hardware
Firmware interacts with hardware by configuring and controlling peripherals such as GPIO, timers, and communication interfaces. This is done either by directly manipulating hardware registers or by using hardware abstraction layers provided by the SDK.

Timing, memory usage, and hardware state must be carefully managed because the firmware operates under strict resource constraints.

## How firmware interacts with higher-level software
If an operating system or application layer exists, firmware provides the foundation that allows it to run. This may include task scheduling, interrupt handling, and communication between software components.

In some systems, firmware itself *is* the main application and runs without any higher-level software on top.

## What still feels unclear
Some parts of the system are still unclear to me, such as:
- The exact sequence of the boot process on the ESP32
- How much initialization is handled by ESP-IDF versus user code
- How control flows between interrupts, tasks, and main application logic

I expect these areas to become clearer as I work with real examples and debug actual behavior.

