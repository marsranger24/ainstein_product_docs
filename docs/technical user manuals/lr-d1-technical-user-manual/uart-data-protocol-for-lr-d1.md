---
title: UART Data Protocol for LR-D1
deprecated: false
hidden: true
metadata:
  robots: index
---
## 5. UART Data Protocol For LR-D1:

- Protocol: UART 
- I/O Standard: RS-232 (Default) and RS-422 (Per Request)
- Baud Rate: 115200 b/s
- Data length: 8 bits, plus one start bit and one stop bit, and no parity bit  
  Caution! If the data received for the malfunction alert code is not equal to 0x0000 (Normal  
  function) for data 5 and data 6 in the table below, then please check the malfunction alert  
  code table in the Appendix 1 for details.

**Caution!** If the data received for the malfunction alert code is not equal to 0x0000 (Normal  
function) for data 5 and data 6 in the table below, then please check the malfunction alert  
code table in the Appendix 1 for details.