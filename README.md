# Cell Selection Criterion S: Srxlev Calculator
online calculate: https://dustinchen26.github.io/S_criteria

## Description & example
```
Cell Selection Criterion S: Srxlev Calculator
◼️ 3GPP Spec
     ● TS 38.304 chap 5.2.3.2 Cell Selection Criterion
         The cell selection criterion S is fulfilled when:
            Srxlev > 0 AND Squal > 0
         where:
            Srxlev = Qrxlevmeas – (Qrxlevmin + Qrxlevminoffset ) – Pcompensation – Qoffsettemp
            Pcompensation = max(p-Max – MTPL, 0)
     ● TS 38 101-1 Table 6.2.1-1: UE Power Class
         UeCapabilityInformation ue-PowerClass pc2 => MTPL = 26 dBm
         UeCapabilityInformation ue-PowerClass pc3 => MTPL = 23 dBm
     ● TS 38 331 Q-RxLevMin
         Actual value Q rxlevmin = field value * 2 [dBm].
         SIB1 ::= SEQUENCE {
             cellSelectionInfo             SEQUENCE {
                     q-RxLevMin                      Q-RxLevMin,
                     q-RxLevMinOffset            INTEGER (1..8) OPTIONAL, -- Need R
             }

◼️ Please enter the value below to calculate the Srxlev
      ● Qrxlevmeas(UE meas RSRP): -49
      ● q-RxLevMin(From SIB1): -60
      ● Qrxlevminoffset(From SIB1, INTEGER (1..8)): 0
      ● p-Max (from SIB1): 33
      ● MTPL (from UeCapabilityInformation ue-PowerClass pc3 is 23dBm, ue-PowerClass pc2 is 26dBm ): 23
      ● Qoffsettemp: 0
◼️ Calculate
      ● Qrxlevmin = q-RxLevMin * 2 = -60 * 2 = -120.00
      ● Pcompensation = max(p-Max - MTPL, 0) = max(33 - 23, 0) = 10.00
      ● Srxlev 
	  = Qrxlevmeas - (Qrxlevmin + Qrxlevminoffset) - Pcompensation - Qoffsettemp
      = -49.00     - (-120.00   + 0.00           ) - 10.00         - 0.00
      = 61.00
      Ans: Srxlev: 61.00  
```
