# Actors

## 1. User
- Interacts by providing environment audio
- May observe system output through debug interface

## 2. Microphone
- Provides analog audio input to ADC
- Does not initiate actions

## 3. ADC Hardware
- Converts incoming analog audio to digital samples
- Provides data to MCU processing pipeline

## 4. MCU Firmware
- Executes FIR filtering
- Responsible for real-time system behavior

## 5. Debug/Visualization Tools
- Consumers of filtered digital audio
- Used to validate filtering performance (frequency plots, oscilloscope, etc.)

## 6. System Developer (Engineering Actor)
- Defines requirements
- Performs modeling, implementation, and verification