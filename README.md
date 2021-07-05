# Learning Pentaho ETL Basics
Project lists the various exercises that can be done to learn the most used concepts in Pentaho DI (Kettle) ETL

---
**Notes / Assumptions**:
- <run_project> in the ktr or kjb
  - Name of the Project you have Setup for organizing your code. 
  - This is just a naming convention I follow for easier tracking of Owner.
  - ex. kb_pdiproj
- Organization of the PDI project followed in this exercise:
  - kb_pdiproj
    - pdi
      - Will include all Jobs organized by Functional Modules.
      - ex. in [exercise 1](#ex-1), Module name : `Input_Basics`
    - scripts
      - Will include all PDI Caller Script organized by Functional Modules.
---
[Exercise 1 : Input Step - 'CSV File Input' + Output Step - 'Text File Output'](#ex-1)

`Transformation name : Input_Basics/pkt_ce_<run_project>_100_01_Copy_Files.ktr`
- Create Transformation to Copy File from /tmp/in/file01.CpA to /tmp/out/file01.CpB
  - Input File (`/tmp/in/file01.CpA`) has **No Header**
  - Input File Schema
    - ColA (`Integer`)
    - ColB (`Date`) (Format in Input as `YYYY-MM-DD`)
    - ColC (`Timestamp`) (Format in Input as `YYYY-MM-DD HH:mm:ss.zzz`)
    - ColD (`String`) (with `Fixed Length`. Length = `5`)
    - ColE (`String`) (with `Variable` Length)
    - ColF (`Decimal`) (with `2` decimal places) 
    - Delimiter : Comma (`,`)
  - Output Fle (`/tmp/out/file01.CpB`) should **have** header
  - Output File Schema
    - ColA (`Integer`)
    - ColB (`Date`) (To be Formatted in output as `YYYY-MM-DD`)
    - ColC (`Timestamp`) (To be Formatted in output as `YYYY-MM-DD_HHmmss`)
    - ColD (`String`) (Should maintain)
    - ColE (`String`)
    - ColF (`Decimal`) (with `1` decimal places)
    - Delimiter : Pipe (`|`)

---
[Exercise 2 : Input Step - 'Text File Input'](#ex-2)

`Transformation name : Input_Basics/pkt_ce_<run_project>_100_02_Copy_from_Multiple_Files.ktr`
- Create Transformation to Copy Data from multiple file, /tmp/in/file02.Cp00, /tmp/in/file02.Cp01 .... /tmp/file02.Cp9999, to /tmp/out/file02.CpC
  - Input Files `/tmp/in/file02.Cp00, /tmp/in/file02.Cp01 .... /tmp/file02.Cp9999` have **No Header**
  - Input File Schema
    - ColA (`Integer`)
    - ColB (`Date`) (Format in Input as `YYYY-MM-DD`)
    - ColC (`Timestamp`) (Format in Input as `YYYY-MM-DD HH:mm:ss.zzz`)
    - ColD (`String`) (with `Fixed Length`. Length = `5`)
    - ColE (`String`) (with `Variable` Length)
    - ColF (`Decimal`) (with `2` decimal places)
    - Delimiter : Comma (`,`)
  - Output Fle `/tmp/out/file02.CpC` should **have** header
  - Output File Schema
    - ColA (`Integer`)
    - ColB (`Date`) (To be Formatted in output as `YYYY-MM-DD`)
    - ColC (`Timestamp`) (To be Formatted in output as `YYYY-MM-DD_HHmmss`)
    - ColD (`String`) (Should maintain)
    - ColE (`String`)
    - ColF (`Decimal`) (with `1` decimal places)
    - Delimiter : Pipe (`|`)
  
---
[Exercise 3 : Input Step - 'Table Input'](#ex-3)

`Transformation name : Input_Basics/pkt_ce_<run_project>_100_03_Extract_DB_Table_to_File.ktr`
- Create Transformation to Copy Data from Table input_data_test to /tmp/out/file03.CpB
  - MySQL Table `input_data_test` schema
    - ColA (`Integer`)
    - ColB (`Date`)
    - ColC (`Timestamp`)
    - ColD (`String`) (Length = `5`)
    - ColE (`String`) (`Nullable`)
    - ColF (`Decimal`)
  - Output File `/tmp/out/file03.CpB` should **have** header
  - Output File Schema
    - ColA (`Integer`)
    - ColB (`Date`) (To be Formatted in output as `YYYY-MM-DD`)
    - ColC (`Timestamp`) (To be Formatted in output as `YYYY-MM-DD HH:mm:ss.zzz`)
    - ColD (`String`) (Should be Fixed Length. Padded with `Blank Space` to fit size. Length = 5)
    - ColE (`String`) (Transformation Rule : `'N/A'` if Input Column ColE is `Null`)
    - ColF (`Decimal`) (with `1` decimal places)
    - Delimiter : Pipe (`~`)

