# System Requirements

## Functional Requirements (FR)

FR-01 The system shall acquire audio from an analog microphone.  
FR-02 The system shall convert the analog audio into digital samples using an ADC.  
FR-03 The system shall perform a band-stop FIR filter on the digital samples.  
FR-04 The system shall operate in continuous real-time mode.  
FR-05 The system shall output the filtered digital audio stream.  

## Performance Requirements (PR)

PR-01 The system shall support audio bandwidth up to 10 kHz.  
PR-02 The system shall use a sampling rate of 16 kHz.  
PR-03 The FIR filter shall implement a band-stop notch at 1 kHz ± 200 Hz.  
PR-04 The filter attenuation at stopband shall be ≥ 40 dB.  
PR-05 The processing latency shall be ≤ 1 sample period.  

## Hardware Requirements (HR)

HR-01 The system shall run on a TI MSP432P401R microcontroller.  
HR-02 The system shall use a microphone compatible with ADC input.  
HR-03 The system shall support floating-point FIR filtering.  

## Interface Requirements (IR)

IR-01 The system shall interface with the microphone via analog input.  
IR-02 The system shall interface with validation tools via digital debug output.  

## Development Requirements (DR)

DR-01 The system shall use Model-Based Design techniques.  
DR-02 The system shall follow a V-Model development workflow.  
DR-03 The system shall maintain traceability from requirements to test cases.  
DR-04 The system shall maintain source control using Git/GitHub.