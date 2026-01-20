# Understanding Firmware

## Why this matters
As I move through the learning process of embedded systems, I need a clear mental model of what firmware actually is and what it is responsible for. Without this, it’s easy to get lost in tools and code without understanding their role in the system.

## What firmware is (my current understanding)
My current understanding of firmware is that it is a type of software closely tied to the device’s hardware. It is responsible for enabling the system to function at a low level, before or alongside higher-level software.

Firmware is not meant to be frequently changed by end users, and it operates under strict hardware constraints such as limited memory, timing requirements, and direct hardware control.

## What firmware is responsible for
Based on my current understanding, firmware typically handles:
- The boot process of the device
- Initialization and management of hardware components
- Communication between hardware and higher-level software (such as an operating system or application layer)
- Providing a stable and predictable execution environment for the system

## What firmware is NOT
Firmware is not a full-featured application like desktop or web software. It usually does not have access to large libraries, dynamic memory allocation freedom, or an operating system unless explicitly designed to run on top of one.

## Where firmware lives
Firmware is stored in non-volatile memory on the device, such as flash memory, and is executed directly by the processor when the system powers on.

## How my understanding might change
I expect this definition to evolve as I gain more hands-on experience with microcontrollers, boot sequences, and real-time systems.
