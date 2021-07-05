# Learning Pentaho ETL Basics
Project lists the various exercises that can be done to learn the most used concepts in Pentaho DI (Kettle) ETL

---
[Exercise 1 : Input Stage - 'CSV File Input'](#ex-1)

`Transformation name : Input_Basics/pkt_ce_<run_id>_100_01_Copy_Files.ktr`
- Create Transformation to Copy File from /tmp/file01.CpA to /tmp/file01.CpB
  - Input File has **No Header**
  - Input File Schema
    - ColA (`Integer`)
    - ColB (`Date`) (Format in Input as `YYYY-MM-DD`)
    - ColC (`Timestamp`) (Format in Input as `YYYY-MM-DD HH:mm:ss.zzz`)
    - ColD (`String`) (with `Fixed Length`. Length = `5`)
    - ColE (`String`) (with `Variable` Length)
    - ColF (`Decimal`) (with `2` decimal places) 
    - Delimiter : Comma (`,`)
  - Output Fle should **have** header
  - Output File Schema
    - ColA (`Integer`)
    - ColB (`Date`) (To be Formatted in output as `YYYY-MM-DD`)
    - ColC (`Timestamp`) (To be Formatted in output as `YYYY-MM-DD_HHmmss`)
    - ColD (`String`)
    - ColE (`String`)
    - ColF (`Decimal`) (with `1` decimal places)
    - Delimiter : Pipe (`|`)



