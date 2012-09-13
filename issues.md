Datasheet 1.2r0
---------------

 1. The purpose of the "LO Leakage" label at the "Figure 1: Functional block diagram" is not to show the path of LO leakage. :) Actually it means "LO Leakage Cancellation" and refers to DACs used for that purpose. Refer to the "Calibration and Initialization" section of the datasheet.
 2. "Figure 3.8: RX FE control" misses an important configuration register "SELOUT[1:0]: Select output buffer in RX PLL". This configuration register must be used together with LNASEL_RXFE to choose LMS6002D input.
 3. "4.1 General DC Calibration Procedure" procedure is incomplete and often shows failure when it actually completes fine. Refer to FAQ, question 4.7 for a workaround.

Contacts
--------

Found an issue? Let me know and I'll try to get it fixed in the next release of documentation.

-- Alexander Chemeris &lt;Alexander.Chemeris@fairwaves.ru&gt;
