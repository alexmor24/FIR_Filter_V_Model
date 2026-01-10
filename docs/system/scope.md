# System Scope — Audio Band-Stop Filtering System

## 1. Purpose
The purpose of the system is to acquire audio from an analog microphone, convert it to digital samples, apply a real-time band-stop FIR filter, and output the filtered digital signal for further processing or debugging.

## 2. System Context
The system operates as a real-time embedded audio signal processing chain running on a Texas Instruments MSP432P401R microcontroller.

External components:
- Microphone (analog audio source)
- ADC (integrated or external)
- MCU firmware (filtering application)
- Debug/output interface (UART/USB/Scope/Plot)

## 3. Input and Output
**Input:**  
- Analog audio from electret microphone via microphone amplifier stage
- Frequency content up to ~10 kHz (voice/audio range)

**Output:**  
- Digital filtered audio stream (real-time)

## 4. Operational Scenario
The MCU continuously samples audio, processes FIR band-stop filtering, and outputs results with low latency.

## 5. System Boundaries
Included within system:
- Signal acquisition (ADC)
- FIR band-stop filtering
- Real-time scheduling
- Validation & measurement (latency, frequency response, noise rejection)

Not included:
- Power management
- Audio playback/actuation
- Advanced DSP (AGC, compression, EQ)

## 6. Key Assumptions
- Microphone bandwidth supports >10 kHz
- MCU supports floating-point FIR implementation
- Real-time performance achieved without RTOS
- ADC rate >= 44.1 kHz recommended (audio-grade), TBD

## 7. Primary Engineering Goals
- Real-time operation
- Stable FIR filtering
- Low-latency processing
- Embedded deployability
- Early model-based verification

## 8. Standards/Methodology
- Development approach: V-Model
- Design methodology: Model-Based Design (MBD)
- Traceability: MBSE practices