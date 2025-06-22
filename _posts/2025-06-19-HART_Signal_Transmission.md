---
title: HART signal transmission.
date: 2025-06-19 01:10:00 +100
categories: [Industry_Automation, HART]
tags: [HART, Industry_Automation]
---

# <span style="color:olive">HART - Signals</span> 
---

### <span style="color:orange">Overview</span> 

HART (Highway Addressable Remote Transducer) <b>operates on two layers</b> at the same time:
<ol>
    <li><b>Analog (4–20 mA)</b> – traditional process measurement.</li>
    <li><b>Digital (FSK - <em>Frequency Shift Keying</em>)</b> – smart digital communication between devices</li>
</ol>

<b>Both signals</b> are transmitted simultaneously <b>over the same two wires</b>.

* The analog HART signal is the main measurement signal, sent as current (DC) in the 4–20 mA range.

* The digital FSK signal carries additional information (config, diagnostics, ID) using audio-frequency tones (1200/2200 Hz), added as a small AC signal.

* Both signals share the same physical wires, which is the key advantage of HART: digital communication without needing new wiring.

---
### <span style="color:orange"> Analog Signal</span> 
<ul>
<li><b><u>Carrier: current level.</u></b></li>
<li>The current in the loop varies between 4 and 20 mA.</li>
<li>This current also powers the field device.</li>
</ul>

Examples:

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→ 4 mA = 0°C

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→ 12 mA = 50°C

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;→ 20 mA = 100°C


---
### <span style="color:orange"> Digital Signal</span> 
<ul>
<li>On the same wires, on top of the analog signal, small AC signals (±0.5–1 mA) are superimposed.</li>
<li>These fluctuations use two tones:

- 1200 Hz = bit 1
- 2200 Hz = bit 0
</li>
</ul>

----
### <span style="color:orange"> More about FSK...</span> 

FSK (Frequency Shift Keying) is the method HART uses to send digital data. Instead of sending 0s and 1s as electrical voltages (like in regular digital communication), it sends them as two different tones (frequencies).

Think of it like:
<ul>
    <li> Tone A (1200 Hz) = digital 1 </li>
    <li> Tone B (2200 Hz) = digital 0 </li>
</ul>
The device quickly switches between these two tones to send messages.
</br>
</br>
If the message is: <em>101100</em>

The FSK signal will sound like:
1200Hz → 2200Hz → 1200Hz → 1200Hz → 2200Hz → 2200Hz
</br>
</br>This is happening super fast—so fast that you don’t hear it or see it interfering with the analog current.


Using FSK, HART can send:
<ul>
    <li>Device info (model, serial number)</li>
    <li>Status or diagnostics</li>
    <li>Calibration data</li>
    <li>Configuration settings</li>
</ul>
All without stopping the analog signal.


---
### <span style="color:orange"> Analog Signal vs Digital Signal - comparison</span> 

![localImage](/assets/images/industry_automation/hart_analogsig_digitalsig_comparison.png)

---
### <span style="color:orange"> Summary</span> 
How data is transmitted using HART?

Here’s the step-by-step way:

1. Analog Signal Is Still There
The normal 4-20 mA analog signal keeps doing its job (e.g., representing temperature or pressure). This signal is not disturbed.

2. Digital FSK Signal Is Superimposed
The HART device (like a smart sensor) sends digital information on top of the analog signal by quickly switching between 1200 Hz and 2200 Hz tones.

3. Why It Works
Because these tones are small and switch fast, they don’t affect the analog signal. Special devices on the other end can separate the analog and digital parts.

![localImage](/assets/images/industry_automation/hart_fsk.png)

When we say a wave oscillates, we mean that something moves up and down (or side to side) repeatedly in a fast, regular pattern.

In electricity or sound: oscillation means that the voltage or current changes – up and down – at a certain speed.

If you have a 1200 Hz wave, it means the up–down–up cycle happens 1200 times per second.

A 2200 Hz wave completes 2200 such cycles per second – that’s a faster oscillation.

If you connect a 1200 Hz wave to a speaker, you’ll hear a lower-pitched tone.
If you connect a 2200 Hz wave, you’ll hear a higher-pitched tone.

That’s why we say the wave "oscillates faster or slower" – it's about how often the wave cycles.

In HART, these oscillations aren’t audible, but they happen in the electrical signal.

When we say a wave “oscillates at 1200 Hz,” it means:
<ul>
<li>The voltage (or current) moves up and down 1200 times per second.</li>
<li>The electronics in the device "see" this and interpret it as a digital 1 or 0.</li>
</ul>

</br>
<b>Real-World Analogy</b>

Imagine you’re listening to soft background music (the analog signal), and someone is tapping Morse code on the table (the FSK tones). You can still enjoy the music and also decode the message if you know how to "listen" for it. That’s what HART devices and controllers do.