# NVDLA-summary
A summary of what I have studied

----------
## Content
- Architecture of NVDLA
- NVDLA Operation
- Data Structure

----------
## 1. Architecture of NVDLA

NVDLA structure is divided to partitions.
Partition_o : Interface
Partition_c : Convolution Buffer (CBUF - Data buffer & Weight buffer)
Partition_m : MAC array (Multiplication)
Partition_a : Accumulator
Partition_p : Activation Function

![image](https://user-images.githubusercontent.com/87763197/128123118-2028676a-9b77-40de-b687-60b0959e8398.png)


## 2. NVDLA Operation

This example is googlenet_conv2_3x3_int16.

### Simulation (Testbench)
MSEQ_CMD (csb_master_seq.v) --> NVDLA
 * CPU(MCU) --> Instruction (Machine language) --> NVDLA
 * CSB_MASTER_SEQ generating MSEQ_CMD is responsible for CPU. (for simulation)

### Memory Setting (Simulation)
Data load to DRAM (or SRAM)

![image](https://user-images.githubusercontent.com/87763197/128124740-b6dbc06d-f8f4-4e1d-ad93-db955a8d249f.png)

### Configuration Value Setting
Write the configaration value to the corresponding registers of NVDLA sub-modules. 

![image](https://user-images.githubusercontent.com/87763197/128124757-ff1638a6-fb5b-41fe-aa16-a8c16bc1335a.png)


Detail of Configuration Setting
![image](https://user-images.githubusercontent.com/87763197/128125184-8b6359d1-5e17-4701-bd9c-2ded40fa9d5d.png)

