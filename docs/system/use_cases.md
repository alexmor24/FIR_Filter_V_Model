# Use Case Model

## Use Case List
UC1 — Acquire Audio  
UC2 — Convert Audio to Digital  
UC3 — Filter Audio (Band-Stop)  
UC4 — Output Filtered Signal  
UC5 — Validate Signal Performance  
UC6 — Configure System Parameters (Engineering Use)

---

## Use Case Templates

### UC1 — Acquire Audio
**Primary Actor:** Microphone  
**Trigger:** Audio present in environment  
**Preconditions:** Microphone powered and active  
**Main Scenario:**
1. Microphone captures analog audio waveform
2. Signal transmitted to ADC front-end  
**Postconditions:** Analog waveform available for sampling  

---

### UC2 — Convert Audio to Digital
**Primary Actor:** ADC Hardware  
**Trigger:** Sampling timer tick  
**Preconditions:**
- Analog waveform available
- Sampling rate stable  
**Main Scenario:**
1. ADC samples analog input
2. ADC quantizes sample
3. ADC sends digital sample to MCU buffer  
**Postconditions:** Digital sample sequence available  

---

### UC3 — Filter Audio (Band-Stop)
**Primary Actor:** MCU Firmware  
**Trigger:** New digital sample ready  
**Preconditions:**
- FIR coefficients loaded
- Processing pipeline active  
**Main Scenario:**
1. MCU receives digital sample
2. MCU performs FIR convolution
3. Band-stop filtering is applied  
**Postconditions:** Filtered sample generated  

---

### UC4 — Output Filtered Signal
**Primary Actor:** MCU Firmware  
**Trigger:** Filtered sample ready  
**Main Scenario:**
1. MCU forwards filtered sample to debug/output
2. Data consumed by external tools  
**Postconditions:** Filtered data available  

---

### UC5 — Validate Signal Performance
**Primary Actor:** System Developer  
**Main Scenario:**
1. Developer injects test signal
2. Developer captures filtered signal
3. Frequency response measured
4. Noise rejection validated  
**Postconditions:** Behavior validated against requirements  

---

### UC6 — Configure System Parameters
**Primary Actor:** System Developer  
**Main Scenario:**
1. Developer adjusts filter parameters (freqs, order, Fs)
2. System updates design model
3. Coefficients regenerated  
**Postconditions:** New configuration loaded