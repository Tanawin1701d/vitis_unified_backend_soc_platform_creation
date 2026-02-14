# SOC Platform for HLS4ML Unified Back-end Tutorial

- This section exemplifies how to create the platform for HLS4ML backend

## 1. create Vivado Project

- create common vivado project BUT YOU MUST click ```Project is extensible to vitis platform```

![ZCU102 Board](./images/extensible.png)


## 2. Create Block Diagram

The block name MUST be ```vitis_diagram``` only

![ZCU102 Board](./images/createBlock.png)

## 3. Build Block Diagram

The block diagram should be like in this picture

![ZCU102 Board](./images/connections.png)



## 4. Platform Setup


- AXI Port

![ZCU102 Board](./images/platform_axi.png)
![ZCU102 Board](./images/platform_axi2.png)


- AXI Stream Port

![ZCU102 Board](./images/platform_axis.png)

- Clock

![ZCU102 Board](./images/clock.png)

- Interrupt

![ZCU102 Board](./images/interrupt.png)


## 5. Create HDL wrapper and Generate Output Product

Click HDL wrapper and Generate Output Product

![ZCU102 Board](./images/createHDLWrapper.png)

## 6. Generate Bit Stream File


## 7. Export Platform


### 7.1 check is there dcp file exist
- IF DCP FILE EXIST AT UTILS_1, YOU MUST DELETE IT BEFORE NEXT STEP

![ZCU102 Board](./images/dcpDelete.png)

### 7.2 begin export

- follow the popup window, it will generate the XSA file. put the XSA wherever you want
- the XSA file can be used instead XPFM file.

![ZCU102 Board](./images/export_platform.png)