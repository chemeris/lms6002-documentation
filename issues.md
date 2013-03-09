Datasheet 1.2r0
---------------

 1. The purpose of the "LO Leakage" label at the "Figure 1: Functional block diagram" is not to show the path of LO leakage. :) Actually it means "LO Leakage Cancellation" and refers to DACs used for that purpose. Refer to the "Calibration and Initialization" section of the datasheet.
 2. "Figure 3.8: RX FE control" misses an important configuration register "SELOUT[1:0]: Select output buffer in RX PLL". This configuration register must be used together with LNASEL_RXFE to choose LMS6002D input.
 3. "4.1 General DC Calibration Procedure" procedure is incomplete and often shows failure when it actually completes fine. Refer to FAQ, question 4.7 for a workaround.
 4. SRXEN/STXEN registers are equivalent to TXEN/RXEN pins. Internal control signals are constructed using logical AND in the following way:
<pre>
iTXEN = TXEN and STXEN
iRXEN = RXEN and SRXEN
</pre>
 5. RXTIA is a synonim for RXVGA1. TIA stands for Trans Impedance Amplifier. That was the initial block name but changed later to RX VGA1 for simplicity. "RX TIA" may still be used somewhere in the documents.
 6. Peak detector measures signal level at the TX output. The idea was to use it for TX LO leakage calibration but its dynamic range is not good enough. Even uncalibrated TX chain produces LO leakage of about -40dBm which is out of the on chip detector range.
 7. Envelop detector is in fact peak detector of peak detector, it shows IQ imbalance (phase/gain error). Unfortunately, its dynamic range limits its use as a calibration tool.
 8. LOOPBBEN register is not specified entirely in the documentation. Check the "LMS6002D IF-RF LoopBack Options.pdf" for a diagram of its connections and the values below for details about controlling it. To use BB loopback you must power down the stage preceding to the one you're connecting loopback to.
<pre>
LOOPBBEN[1:0]: Baseband loopback switches control
    00 – All switches are open (default)
    01 – provides TXLPF output to baseband loopback
    10 – provides TXVGA1 output to baseband loopback
    11 – provides envelop/peak detector output to baseband loopback
</pre>

Contacts
--------

Found an issue? Let me know and I'll try to get it fixed in the next release of documentation.

-- Alexander Chemeris &lt;Alexander.Chemeris@gmail.com&gt;
