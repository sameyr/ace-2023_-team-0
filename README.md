<h3 align="center">High-Performance Computing System</h3>

## Table Of Contents
- [5.Software Installation](#5software-installation)
  - [5.1 SLURM Configuration](#51-slurm-configuration)
  - [7. Performance Evaluation: Develop a strategy for evaluating HPC system performance.](#7-performance-evaluation-develop-a-strategy-for-evaluating-hpc-system-performance)
  - [8. Software and OS Maintenance:](#8-software-and-os-maintenance)
  - [9. Task Implementation:](#9-task-implementation)
    - [9.1. How to Create Machine Learning for Predict Crypto Currencies](#91-how-to-create-machine-learning-for-predict-crypto-currencies)
  - [10. Performance Evaluation:](#10-performance-evaluation)
  - [References](#references)
  - [Authors](#authors)
  
## About The Project
The provided documentation outlines the comprehensive process undertaken by Team 0 for the design of a High Performance Computing (HPC) system as part of the Advanced Computer Engineering Module for the Computer Engineering Program at the University of Greenwich for the academic year 2023/24. This report guides the reader through a detailed step-by-step procedure encompassing both hardware and software aspects of the project. By following this documentation, readers will gain insights into the systematic approach employed by the team, enabling them to replicate and create their own HPC systems.  

## Built With
- [JavaScript](https://www.javascript.com/)
- [VueJS](https://vuejs.org/)


## Introduction


## 1. System Design And Architecture ## 4. Housing and Cooling Solutions: 
***Design and implement housing/structure using laser cutting or additive manufacturing. Discuss convection principles (natural and forced) for cooling.***


[Specification of all the components can be found here!](hardware.md)

***Design the architecture, integrating 14 ASUS CS-8 motherboards and single-board computers. Provide critical reflections on the chosen design.***

# Original Design For The HPC Case
The original design for the case consisted of 3D printing of all components needed. This included the shelves, floor, roof, and side/back panels of the case. Multiple aspects have to be considered when designing the case such as the components requirements, ventilation, and accessibility. All original shelf and case piece that have been uploaded were designed to be durable and well ventilated and were easily connected together using a pin system

## Problems Encountered
While waiting to receive the initial components from 3d printing I was informed that it would take to long to 3d print all my required components as there were many other students looking to 3d print components at this time Aswell. To solve this issue, we decided to order the shell of our case and print the brackets and laser cut the shelves as well as the front and back panels in stead of printing all the components

# Chosen Shell  
The case we ordered was a 21U tall server racking system which was perfect for the purpose of our projects. It came with slots all down the left and ride side of the case which ensured enough ventilation for the fans to disperse the heat 

![Shell](case.jpeg)<br>
<b>Figure 1:Case</b>
<br><br>

The 1U brackets were 3d printed in order to hold the acrylic shelves that were laser cut. They were mounted in the holes that were ment for the racking system of the case. An extension cord was placed at the back and mounted to the top of the case. Whis acted as a way to limit the amount of cables that would exit the case. Instead, we could power each of the motherboards power sources internally 

![Push button](brackets.jpeg)<br>
<b>Figure 1:3D printed brakets </b>
<br><br>

The front and back of the case was laser cut in acrylic with 120x120 fan holes at the base and the top in order to mount the fan to then in a way that allowed them to get a strong enough air pull. Hence the small circles that fill the 120x120 frame. the back panel was made to be slightly smaller to allow room for the extension cord 


![Push button](panels.jpeg)<br>
<b>Figure 1:3D back panel of case  </b>
<br><br>

# Other alterations
Rubber feet will be used on the motherboards and the SSDs to limit the directs contact onto the shelves to allow air underneath the boards when necessary. The extension cable will run down the side of the case into an outlet. The power button will drill through the roof of the case to allow Instant power to the application we have also decided to cover the back of the case to limit the light inside the case to utilize the led fans. All power supply will plug directly into the extension cord build into the case

# Design reflection and future improvements 
During the course of this assignment there have been a few development problems and issues that arose in regard to the specific design of the case such as the time impairment, material acquisition, ventilation and change in requirements. In this report I will discuss how each of these problems were analyzed and resolved to display a design that fit the requirements of the projects while also remaining affordable and simple to construct.

# Time impairment 
The first and possible largest issue we faced in constructing the case was time. As we had a fixed amount of time to build and submit the Hpc the case had to be completed in about a month and a half. My first idea was 3D printing the part required to build the frame/shelfing unit. After sending my designs of to be printed I was told that all part would take over 80 das as there was over 65 pieces to print along with other student needing to use the printing facilities as well.to work around this problem I decided that purchasing a frame could be cheaper and less time consuming as well as having more stability. This way I could focus more on altering the internal of the case as well as making a front and rear for the frame. This cut the time to create a case by at least a month allowing more time for alterations if need be 

# Material acquisition 
An issue arose with the materials as some materials were ordered before the time issues were realized. This issue was fixed by ordering the correct components and altering the lengths of some of the cables needed like the ethernet cable and the power cable along with some cable management. I mention these issues as it highlighted the need to double-check the design before ordering any components as well as communicating with my teams to avoid these mistakes happening in the future.

# Ventilation
The ventilation of the case was considered from the very beginning as it essential to keep the system cool under prolonged periods of time.  With 5 motherboards being used in sync I decided to go with a 2 in 2 out fans system. 2 fans would take air in at the top front of the case and 2 would blow air out of the case at the bottom rear. This would allow decent air flow that would keep a steady current around the case. Temperature sensors inside the case can monitor how hot the components get and alert the user if the temperature exceeds the recommended limit.

# Change in requirements 
Throughout the course pf this project there were a number of alterations that needed to be made to counter errors in judgement as well as new components that needed to be added to achieve complete networking between the boards. By altering the size of the shelves and by utilizing the space in the side of the case for storing the wires, all new components and power sources fit as needed 

# Reflection 
If I were to design this case again, I believe there are a few changes that could be made. I think the biggest change I would make is I would have made holes across the laser cut shelves as it would increase the ventilation in the case however if I did this, I would make the shelf out of wood as with to many holes cut the structural integrity would be compromised and they may not be able to hold the components at the current thickness. By changing the material to wood and increasing the thickness of the shelves, adding the holes will not impair the performance. It is important to keep in mind the ultimate stress point and the fracture point of the material used as well as the elastic point. The brackets that were built were perfectly fit for purpose so I will utilize them for similar case frames in the future and if given the opportunity to improve this case

   
   
## 2. Technology Research: 
***Conduct comprehensive research on HPC technologies, power management, non-volatile storage, and RAM. Justify technology choices based on problem domain appropriateness.*** 

### 2.1 Operating System Selection: 

Initially, an attempt was made to determine which operating system the ASUS CS-B motherboard supports. However, the information available suggests that the ASUS CS-B is only compatible with Ubuntu 13.10, as indicated in the provided image.

![Os](https://github.com/TeachingMaterial/ace-2023_-team-0/assets/85470428/3f1fbdae-3522-4e26-841c-ef19f4888d5a)
Figure: OS Compatibility of Asus CS-B 

#### 2.1.1 Install Operating System in Head Node

1. Once the operating system was determined, below steps are followed to install ubuntu desktop 13.10:
      - Downloaded the Ubuntu Desktop from the official Ubuntu website (https://old-releases.ubuntu.com/releases/13.10/). As Intel processor is used, PC (Intel x86) desktop image is chosen when downloading the image.
      - Created a bootable USB drive using Rufus.
      - Booted the motherboard from the USB drive.
      - Followed the installation wizard to install Ubuntu Desktop on the system.


                  sudo apt update                                           
            
                  sudo apt upgrade

3. Given its role as the head node in our setup, the desktop image is transformed into a server. Let's quickly delve into the significance of the head node within the realm of High-Performance Computing (HPC).

- The head node serves as a central control unit in an HPC environment, orchestrating and managing the entire cluster. Its primary purposes include task scheduling, resource allocation, and overall coordination of computational tasks within the cluster. By installing      the Ubuntu Server and setting the default target to multi-user mode optimize resource allocation, conserving RAM and CPU resources by eschewing unnecessary graphical sessions. This ensures that the head node operates efficiently, enabling it to efficiently manage and    oversee the computational workload of the entire HPC cluster.
  
            To install Ubuntu Server  : sudo apt install ubuntu-server
            To disable GUI            : sudo systemctl set-default multi-user.target
     
Although the documentation states that the ASUS CS-B motherboard can only run Ubuntu 13.10, a brief test was run to see how the motherboard would react to installing Ubuntu 24.04 (Nobel Numbat), a more recent version of the operating system. The Ubuntu 24.04      
operating system ran on the system very well, with no noticeable glitches. This surprising finding prompted more investigation into the motherboard's compatibility with the latest Ubuntu versions. 
Although documentation indicates otherwise, one plausible explanation for Ubuntu 24.04's successful running on the ASUS CS-B motherboard could be the hardware compatibility enhancements included in later Ubuntu editions. The Ubuntu operating system is continuously improved and optimised by its developers throughout time to improve compatibility with a wider variety of hardware setups. Because of this, more recent versions of Ubuntu might by nature support a greater range of motherboards, including the ASUS CS-B. Moreover, improvements in system libraries, kernel updates, and device drivers in Ubuntu 24.04 can also be responsible for its smooth operation on the ASUS CS-B motherboard. These updates might take care of any compatibility problems that earlier motherboard models might have had, making it possible to use current Ubuntu editions more smoothly.

After noticing that Ubuntu 24.04 operated steadily on the ASUS CS-B motherboard, the group chose to switch from Ubuntu 13.10 to this more recent version. This choice was driven by the goal of utilising Ubuntu 24.04's most recent software features, security updates, and hardware compatibility changes to provide the best possible computing environment for the team's activities.

#### 2.1.2 Install Operating System in Compute Node

The process of installing the operating system on a compute node is similar to that of the head node, with the exception that it is not required the installation of Ubuntu Server specifically.

### 2.2 Power Management
   Following a thorough examination of individual components, research has been conducted to determine the optimal power distribution among them. Initially, the plan was to utilize two 750W Power Supply Units (PSUs). However, due to technical malfunctions in one of the PSUs, the decision has been made to employ smaller PSUs for each motherboard separately. The power consumption of each hardware component is provided below for reference.
  
   |      Components        |     Power Consumption (approx)       |       Description        |
   |------------------------|-----------------------------|--------------------------|
   |Asus CS-B Intel Core i3 4th Gen | 25W - 40W       | CPU Power Management can be handeled directly from BIOS. It provides subitems that allows to manipulate the CPU ratio and feature.|
   |SAMSUNG V-NAND 500GB SSD| 3W (Active), 50mW (idle)|Each Motherboard will be connected to one of this SSD which can be powered by a same PSU.|  
   |NVIDIA QUADRO           |    45W (Max.)           |Only one of the GPU will be used in the entire system which will be connected to the head node. |        

   |Power Supply Unit (PSU)| Capacity | Description|
   |---|---|---|
   |FSP220-50LC|220W (total output) | This PSU has a maximum wattage of 60W. And the sum of the power requirements for all the components connected to the PSU should not exceed 220W. |


* Active Power Consumption:

        CPU: 25W - 40W
        SSD: 3W
        GPU: 45W
        Total Active Power Consumption = CPU + SSD + GPU
        = (25W - 40W) + 3W + 45W
        = 73W - 88W

* Idle Power Consumption (Assuming SSD and GPU are in idle state):


* Power Supply Unit (PSU) Capacity:

        Total Output Capacity: 220W
        Maximum Wattage: 60W

* Conclusion:

    The single PSU in our system will be connected to one motherboard, one SSD, and one graphics card. The total power consumption of the system should not exceed the PSU capacity.
    
    The system is expected to consume between 73W - 88W during active use and between 25.05W - 40.05W when idle. Although a single 220W PSU could theoretically handle the load for two motherboards, practical constraints like cable and port limitations restrict each PSU to power only one motherboard in our setup


### 2.3 Network Interconnect:
   
***Cluster Network is two or more computing device working together for a common computing purpose. This Network follows the principle of the parallel processing. Parallel processing is the method of using two or more processors(CPUs) to handle seperate chuncks of a same complex tasks.*** 

There are several interconnect technologies available with their own strength and specefic use-cases. Some of them are :

1. **Infiniband** : Computer Networking communication standard used in high-performance computing that features high throughput and very low latency. It supports Remote Direct Memory Access(RDMA), which means the ability to access host memory directly without CPU intervention. Infiniband is widely used in supercomputer clusters and it is preferred network interconnection technology for GPU servers.
2. **NVIDIA NVLink** : World's first high-speed GPU interconnect technology that can connect two graphics card , with low latency, and high bandwidth. It is ideal for the system that uses NVIDIA graphics card, such as those in deep-learning and GPU accelerated computing. It is not best option for our project,as it is only compatible with NVIDIA graphics card and we will be using intel graphics card for our HPC.
3. **Intel Omni-Path Architecture(OPA)** : OPA is communication architecture developed by intel which aims for low communication latency, low power consumption and a high throughput. It is often used for HPC application with Intel processor. OPA directly competes with infiniband.
4. **Ethernet** : Ethernet is one of the commonly used interconnect technology because of its versatility, scalability and compatibility.It migh not provide same low-latency level as specialised interconnect like infiniband but it provides various speed, ranging from 10 megabyte to 100 gigabyte per second.    

The type of interconnect technology one needs lies on what kind of system they are building and what kind of interconnect is compatible with the system. For our system, specefication and hardware is given above.

For this project, Ethernet cables will be utilized due to their accessibility and sufficient speed for project requirements. These cables will serve dual purposes: data transfer and network bridging. The motherboard provided includes two Ethernet ports, both of which will be utilized for interconnecting nodes.

The head node will establish connections with all other nodes via a switch. Two switches will be employed: one for interconnecting all nodes to facilitate data transfer, and the other to distribute internet connectivity from the head node to all compute nodes. 

By default, one of the ports is enabled. However, to activate the second port, users must adhere to the following steps:

            Reboot the motherboard 

            Press the 'F2' or 'Del' button to access the BIOS settings 

            Navigate to Advanced settings using arrow keys.

            Proceed to Network Interface Stack Setting

            Enable the Second Interface named "Retalke Interface" (most of the cases, name may vary)

            Esure that your "Intel Interface" is also enabled.

Once the steps are followed and both interfaces are activated, users can proceed to configure each interface to perform specific tasks. Detailed instructions can be found in the following link: [Configuring Interface using Nm-Connection-Editor](https://github.com/TeachingMaterial/ace-2023_-team-0/tree/documentation/nm-connection-editor-Harishanan)

Ethernet cables were manually crimped for this project, adhering to the Registered Jack 45 (RJ-45) standard. The figure below illustrates the color standard for RJ-45 cables..


![RJ-45 Standard](pictures/rj45_standard.PNG)<br>
      <b>Figure 1: RJ-45 Standard</b>
      <br>

Step wise Step  process is shown in figure 2 below:

![Ethernet-Crimp](pictures/stepwisestepcrimp.PNG)<br>
      <b>Figure 2: Step by Step Ethernet Cimp</b>
      <br>

## 3. System Construction:
***Assemble the HPC system, implementing power management and resource-efficient configurations. Configure non-volatile storage and RAM to meet performance requirements.***


## 4. System Configuration

### 4.1. Networking
To enable parallelisation in HPC, networking must be established between the head node and compute nodes. Therefore, this section will discuss how the network is established in this project's HPC and will also discuss components such as IP address configuration, network topology, and network bridging in more detail. As an introduction, for this networking setup, a star networking topology, static IP configuration and nm-connection editor have been used and will be discussed in more detail below. Note: In the HPC, the operating system is downloaded separately on each node.

[Step by Step Configuration File Can be Found Here](nm-connection-editor.md)

Through this successful networking implementation, future works such as SLURM configuration, Wake On LAN, OpenSSH and many more can be enabled.


### **Open-SSH connection**

OpenSSH, or Open Secure Shell, is an open-source implementation of the SSH protocol. It provides secure communication between two or more computers over an unsecured network, ensuring data exchange confidentiality and integrity. OpenSSH is widely used in Linux and other Unix-like operating systems as the standard SSH implementation for remote administration, secure file transfer, and tunnelling other network services.

In this project, Secure Shell (SSH) is employed to establish secure connections between all nodes. The OpenSSH server facilitates access from one node to another, enabling seamless communication and interaction between systems. OpenSSH is an essential component in configuring servers such as NFS and SLURM, ensuring secure and encrypted communication channels for data transfer and remote management tasks.

[Step by step configuration guide available here!](openssh.md)


### 4.2. Background for power on and off function in HPC

Due to failures experienced with the power-on button for the entire HPC system, the strategy was changed to power the HPC on and off. In this project, a bash script was created using Wake-on-LAN communication and OpenSSH. Initially, the HPC's head node will be turned on using the power-on button. Afterwards, to turn on the compute nodes, a bash script will be run, which turns on the other compute nodes at intervals. Through this method, the compute nodes can be successfully powered on, allowing the whole HPC system to function. Then, to turn off all the compute nodes, the OpenSSH function was incorporated into the script, with the sudo shutdown command for all compute nodes. Through this, it is possible to turn off the entire compute nodes. Finally, to turn off the head node, one can press the power button or enter a separate sudo shutdown command for the head node.

[Step by Step Configuration File Can be Found Here](power-on-off.md)


# 5.Software Installation

## 5.1 SLURM Configuration

SLURM, an acronym for Simple Linux Utility for Resource Management, is an open-source workload manager developed for supercomputers and Linux-based cluster systems. It offers three primary functions: 

1. It allocates both exclusive and non-exclusive access to compute node resources from a central head node, allowing tasks to be executed efficiently.
2. It furnishes a structured framework for initiating, executing, and overseeing tasks across a designated set of allocated nodes.
3. It resolves resource contention by administering a queue of pending work, ensuring fair access to resources among multiple users or processes.  

The primary commands for submitting, allocating, and monitoring jobs in SLURM are outlined as follows:

1. **sbatch**: Employed to submit batch jobs, allowing users to send job requests to the SLURM scheduler. Job parameters and requirements are defined within a job script, and SLURM schedules and executes the job accordingly.

2. **salloc**: Facilitates interactive resource allocation, enabling users to acquire compute resources in real-time. Once resources are allocated, users can execute commands within this dedicated resource environment.


3. **srun**: Used to execute parallel tasks within allocated resource environments, whether obtained interactively through `salloc` or as part of a batch job submitted with `sbatch`. It manages the execution of parallel tasks across specified nodes.

4. **squeue**: Utilized for monitoring the status of jobs in the SLURM job queue, providing details such as job ID, user, status, and resource utilization. This allows users to monitor job progress and identify queued or running jobs.

5. **scancel**: Enables users to terminate running or queued jobs within the SLURM job queue by specifying the job ID(s) of the targeted jobs to be canceled.

6. **scontrol**: Used for modifying or querying the configuration and state of the SLURM cluster, granting users the ability to manage SLURM resources by configuring nodes, partitions, and accounts, as well as accessing information about jobs and nodes.

These commands serve as essential tools for effectively interacting with SLURM and managing job execution on high-performance computing clusters.

[Step by Step Configuration File Can be Found Here!](slurm.md)

## 5.2. Apptainer Configuration

Apptainer, formerly known as Singularity, is a containerization platform designed to bring containers and reproducibility to scientific computing and the high-performance computing (HPC) environment. Apptainer is specifically optimized for HPC systems, providing a seamless way to package entire scientific workflows, software, libraries, and even data into a single file (Kurtzer et al., 2017).

## 5.2.1. Reasons for Using Apptainer

| Benefit         | Description                                                                                                                     | Reference             |
|-----------------|---------------------------------------------------------------------------------------------------------------------------------|-----------------------|
| **Portability** | Apptainer containers can be executed across different computing environments consistently, ensuring that workflows are reproducible across different HPC systems. | Muster et al., 2018   |
| **Compatibility** | Designed with HPC environments in mind, Apptainer does not require root privileges, aligning with the security policies of most HPC centers.                  | Doe, 2019             |
| **Efficiency**    | Containers encapsulate all dependencies, streamlining installations and avoiding software version conflicts.                                                | Smith, 2020           |
| **Reproducibility** | Packaging software with its dependencies ensures computational work is reproducible, crucial for scientific research validation.                              | Lee and Thompson, 2021|

Below, you can find details on how Apptainers function with images and how they can be configured:

[Learn More about Apptainer and How to Configure apptainer](configure_apptainer.md)

## 5.4. Prometheus and Grafana Configuration

[Configure Prometheus and Grafana](https://github.com/TeachingMaterial/ace-2023_-team-0/blob/dev/configure_Prometheus_Grafana.md)

## 6. Task Implementation:
### 6.1. How to Create Machine Learning for Predict Crypto Currencies

To predict cryptocurrency prices with machine learning, start by fetching historical data (prices, volumes, timestamps) using APIs like Alpha Vantage. Process this data, compute technical indicators (RSI, EMA, SMA), and normalize to ensure uniformity. Split the data into training, validation, and testing sets for model development and evaluation. Consider machine learning models such as Random Forest for its robustness, Gradient Boosting for error minimization, LSTM for capturing long-term dependencies, and GRU for efficient sequential data handling. Fine-tune models using the validation set and assess their performance with metrics like RMSE and MAE on the test set, aiming to select the model that best captures cryptocurrency market dynamics. (<b>This needs to be rewritten</b>)

[Access the detailed step-by-step guide here](Predicting_Cryptocurrency_Prices_with_ML.md)

### 6.2. Implementation of Cryptocurrency Price Prediction Application
<b>Write a introduction of this topic</b>

[Access the detailed step-by-step guide here](https://github.com/TeachingMaterial/ace-2023_-team-0/blob/dev/Implementation_of_ML.md)
## 7. Performance Evaluation: Develop a strategy for evaluating HPC system performance. 

## 8. Software and OS Maintenance: 
***Implement a system for updating software and the operating system using cron and Git. • Reflect on the importance of software and OS maintenance in an HPC environment.***



## References
1. The button can be find here: https://uk.rs-online.com/web/p/push-button-switches/2099127?cm_mmc=UK-PLA-DS3A-_-google-_-CSS_UK_EN_PMAX_RS+PRO-_--_-2099127&matchtype=&&gad_source=1&gclid=EAIaIQobChMIpP3xg7-mhAMVFAUGAB0t5QD5EAQYByABEgIy1_D_BwE&gclsrc=aw.ds

2. How to install WOL : https://pimylifeup.com/ubuntu-enable-wake-on-lan/#:~:text=Wake%2Don%2DLAN%20is%20a,functionality%20through%20your%20devices%20BIOS.

3. Power button and Front panel connections : https://www.pcinq.com/how-to-connect-motherboard-front-panel-headers/
                            https://www.electronicshub.org/power-button-on-motherboard/#:~:text=Ans%3A%20The%20power%20switch%20on,for%20the%2020-pin%20header

1. https://www.diva-portal.org/smash/get/diva2:1778251/FULLTEXT03
2. https://www.sharpsightlabs.com/blog/machine-learning-hyperparameters-explained/
3. https://scikit-learn.org/stable/index.html
4. https://www.warse.org/IJATCSE/static/pdf/file/ijatcse351942020.pdf
5. https://hpc.uni.lu/infrastructure/network
6. https://dlcdnimgs.asus.com/websites/global/aboutASUS/OS/Linux_Status_report_202312.pdf



## Authors


