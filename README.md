[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/vcAhwuzK)
# ELEE1119 Advantage Computer Engineering 2023

## Introduction
---todo

## Step 1: Define Requirements

1. Purpose of the HPC System
2. Performance Requirements
   Determine the performance specifications required for the applications, including processing power, memory, storage, and interconnectivity.

## Step 2: Hardware Components

1. Motherboards
2. Single board computers
3. Processor (CPU)
   Select CPUs based on performance requirements. Consider multi-core processors for parallel processing.
4. Memory (RAM)
   Choose sufficient RAM for each node to handle the workload efficiently.
5. Storage:
   Decide on the storage configuration, considering the need for fast access times. SSDs are commonly used for HPC systems.
6. Network Interconnect:
   Choose a high-speed network interconnect, such as InfiniBand or 10/25/40/100 Gigabit Ethernet, depending on your needs.
   ### Interconnect
         --Cluster Network is two or more computing device working together for a common computing purpose. This Network follows the principle of the parallel processing. Parallel processing is the method of using two or more processors(CPUs) to handle seperate chuncks of a same complex tasks.
      
      In today's time, most computer have multi-cores (i.e., anywhere from two to tewelve cores) which follows the concept of parallel processing. These multi-cores set-ups are similar to having seperate processors installed in a same computer, which can executes more tasks than a single-core processors. In HPC, this concept is extended to multiple nodes, each equipped with its own set of processors where large computational tasks is broken down into smaller sub-tasks that can be executed simultaneously by multile processor at a same time. 

      High-Speed interconnect are crucial for High-Performance Computer(HPC), as we want high data analysis and transfer rate between two nodes to move large amount of data quickly. Along with data transfer, low latency is equally imporatant in HPC, to minimize the time it takes for data to travel between different components of the system. If designing  stock prediction system, developing accurate models often requires extensive training and optimization processes. High-speed interconnects facilitate the rapid exchange of information during these iterative processes, allowing the model to be trained and refined more quickly. 

      There are several interconnect technologies available with their own strength and specefic use-cases. Some of them are :
      
      1. **Infiniband** : Computer Networking communication standard used in high-performance computing that features high throughput and very low latency. It supports Remote Direct Memory Access(RDMA), which means the ability to access host memory directly without CPU intervention. Infiniband is widely used in supercomputer clusters and it is preferred network interconnection technology for GPU servers.
      2. **NVIDIA NVLink** : World's first high-speed GPU interconnect technology that can connect two graphics card , with low latency, and high bandwidth. It is ideal for the system that uses NVIDIA graphics card, such as those in deep-learning and GPU accelerated computing. It is not best option for our project,as it is only compatible with NVIDIA graphics card and we will be using intel graphics card for our HPC.
      3. **Intel Omni-Path Architecture(OPA)** : OPA is communication architecture developed by intel which aims for low communication latency, low power consumption and a high throughput. It is often used for HPC application with Intel processor. OPA directly competes with infiniband.
      4. **Ethernet** : Ethernet is one of the commonly used interconnect technology because of its versatility, scalability and compatibility.It migh not provide same low-latency level as specialised interconnect like infiniband but it provides various speed, ranging from 10 megabyte to 100 gigabyte per second.    

      The type of interconnect technology one needs lies on what kind of system they are building and what kind of interconnect is compatible with the system. For our system, specefication and hardware is given above.


# Install Operating System in Head Node
Initially, an attempt was made to determine which operating system the ASUS CS-B motherboard supports. However, the information available suggests that the ASUS CS-B is only compatible with Ubuntu 13.10, as indicated in the provided image.
![Os](https://github.com/TeachingMaterial/ace-2023_-team-0/assets/85470428/3f1fbdae-3522-4e26-841c-ef19f4888d5a)
Figure: OS Compatibility of Asus CS-B 

1. Once the operating system was determined, below steps are followed to install ubuntu desktop 13.10:
      - Downloaded the Ubuntu Desktop from the official Ubuntu website (https://old-releases.ubuntu.com/releases/13.10/). As Intel processor is used, PC (Intel x86) desktop image is chosen when downloading the image.
      - Created a bootable USB drive using Rufus.
      - Booted the motherboard from the USB drive.
      - Followed the installation wizard to install Ubuntu Desktop on the system.

2. After the installation process, the system undergoes a series of commands to ensure it possesses the latest security patches and software updates:

                                                                  `(sudo apt update
                                                                                                                                          
                                                                  sudo apt upgrade)`

3. Given its role as the head node in our setup, the desktop image is transformed into a server. Let's quickly delve into the significance of the head node within the realm of High-Performance Computing (HPC).

- The head node serves as a central control unit in an HPC environment, orchestrating and managing the entire cluster. Its primary purposes include task scheduling, resource allocation, and overall coordination of computational tasks within the cluster. By installing      the Ubuntu Server and setting the default target to multi-user mode optimize resource allocation, conserving RAM and CPU resources by eschewing unnecessary graphical sessions. This ensures that the head node operates efficiently, enabling it to efficiently manage and    oversee the computational workload of the entire HPC cluster.
  
                                                To install Ubuntu Server  : (`sudo apt install ubuntu-server`)
                                                To disable GUI            : (`sudo systemctl set-default multi-user.target`)
     
Although the documentation states that the ASUS CS-B motherboard can only run Ubuntu 13.10, a brief test was run to see how the motherboard would react to installing Ubuntu 22.04 (Jammy Jellyfish), a more recent version of the operating system. The Ubuntu 22.04       
operating system ran on the system very well, with no noticeable glitches. This surprising finding prompted more investigation into the motherboard's compatibility with the latest Ubuntu versions. 
Although documentation indicates otherwise, one plausible explanation for Ubuntu 22.04's successful running on the ASUS CS-B motherboard could be the hardware compatibility enhancements included in later Ubuntu editions. The Ubuntu operating system is continuously       improved and optimised by its developers throughout time to improve compatibility with a wider variety of hardware setups. Because of this, more recent versions of Ubuntu might by nature support a greater range of motherboards, including the ASUS CS-B. Moreover,         improvements in system libraries, kernel updates, and device drivers in Ubuntu 22.04 can also be responsible for its smooth operation on the ASUS CS-B motherboard. These updates might take care of any compatibility problems that earlier motherboard models might have     had, making it possible to use current Ubuntu editions more smoothly.
After noticing that Ubuntu 22.04 operated steadily on the ASUS CS-B motherboard, the group chose to switch from Ubuntu 13.10 to this more recent version. This choice was driven by the goal of utilising Ubuntu 22.04's most recent software features, security updates,      and hardware compatibility changes to provide the best possible computing environment for the team's activities.

# Install Operating System in Compute Node
The process of installing the operating system on a compute node is similar to that of the head node, with the exception that it is not required the installation of Ubuntu Server specifically.

# SLURM Configuration

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

**SLURM CONFIGURATION IN HEAD NODE**
---
To begin configuring Slurm on the head node, the initial step involves defining and exporting an environment variable representing the user ID (UID) for the 'munge' group. This variable serves as a placeholder for the UID that will later be assigned to the 'munge' group. Additionally, a user account named 'munge' is established. MUNGE is employed as the default authentication mechanism. This process is accomplished using the following command:

      export MUNGEUSER=1001 
      sudo groupadd -g $MUNGEUSER munge 
      sudo useradd -m -c "MUNGE Uid 'N' Gid Emporium" -d /var/lib/munge -u $MUNGEUSER -g munge -s /sbin/nologin munge 

Likewise, an environment variable for SLURM is established, exported, and associated with the SLURM group. Concurrently, a user account named 'slurm' is created. This process is executed using the following command:

      export SLURMUSER=1002 
      sudo groupadd -g $SLURMUSER slurm 
      sudo useradd -m -c "SLURM workload manager" -d /var/lib/slurm -u $SLURMUSER -g slurm -s /bin/bash slurm

Finally MUNGE is installed using the following command:

      sudo apt-get install -y munge 

Upon installing MUNGE, ownership and permissions for MUNGE across various parts of the system are modified to "munge:munge". This task is accomplished using the following command:

      sudo chown -R munge: /etc/munge/ /var/log/munge/ /var/lib/munge/ /run/munge/
      sudo chmod 0700 /etc/munge/ /var/log/munge/ /var/lib/munge/ /run/munge/

Following the configuration of MUNGE, the munge.key file is copied to the `/nfs/slurm` directory. This action facilitates the utilization of the same munge key for authentication purposes on the client node. The command utilized for this step is:

      sudo scp /etc/munge/munge.key /nfs/slurm/

MUNGE services can be enabled and started utilising following command:

      sudo systemctl enable munge
      sudo systemctl start munge

After setting up MUNGE, the following command can be used to check the status of MUNGE:

      sudo systemctl status munge 

After configuring MUNGE, the next step involves downloading a database server that will store job history and scheduling reports. For this project, Mariadb is chosen due to its simplicity in configuration. The following command is utilized to download the Mariadb server:

      sudo apt-get install mariadb-server

In addition to installing the mariadb-server, the Slurm Database Daemon and Slurm-wlm are also installed using the following command:

      sudo apt-get install slurmdbd
      sudo apt-get install slurm-wlm

The database is configured to grant permissions to the 'localhost'. Furthermore, a Slurm database is created to store all the logs of Slurm activities. Following command can be employed to achieve this process:

      mysql
      grant all on slurm_acct_db.* TO 'slurm'@'localhost' identified by 'toor' with grant option; 
      create database slurm_acct_db;
      exit

 Once the database is configured, the slurmdbd.conf file is created. The following line can be used to make slurmdbd.conf file.

      sudo nano /etc/slurm/slurmdbd.conf

The database configuration file should contain the following line of code:

      AuthType=auth/munge
      DbdAddr=localhost
      #DbdHost=headnode
      DbdHost=localhost
      DbdPort=6819
      SlurmUser=slurm
      DebugLevel=4
      LogFile=/var/log/slurm/slurmdbd.log
      PidFile=/run/slurm/slurmdbd.pid
      StorageType=accounting_storage/mysql
      StorageHost=localhost
      StorageLoc=slurm_acct_db
      StoragePass=toor
      StorageUser=slurm
      ###Setting database purge parameters
      PurgeEventAfter=12months
      PurgeJobAfter=12months
      PurgeResvAfter=2months
      PurgeStepAfter=2months
      PurgeSuspendAfter=1month
      PurgeTXNAfter=12months
      PurgeUsageAfter=12months
 
 Required Ownership and Permission should be give to the conf file.
      chown slurm:slurm /etc/slurm/slurmdbd.conf
      chmod -R 600 slurmdbd.conf
 
  The Slurm configuration file can be generated based on the system requirements using the provided link: [Slurm Configuration Generator](https://slurm.schedmd.com/configurator.html).

The following command can be used to create the configuration file and place it inside the /etc/slurm/ directory

      sudo nano /etc/slurm/slurm.conf 
      (Add the configuration file which is created using the link)

The firewall is deactivated to enable inbound traffic on ports 6817, 6818, and 6819 using the following command:

      sudo ufw allow 6817
      sudo ufw allow 6818
      sudo ufw allow 6819

Directories are created to store logs and reports generated by SLURM. Subsequently, permissions and ownership are adjusted accordingly.

      mkdir /var/spool/slurmctld
      chown slurm:slurm /var/spool/slurmctld
      chmod 755 /var/spool/slurmctld

      mkdir  /var/log/slurm
      touch /var/log/slurm/slurmctld.log
      touch /var/log/slurm/slurm_jobacct.log /var/log/slurm/slurm_jobcomp.log
      chown -R slurm:slurm /var/log/slurm/
      chmod 755 /var/log/slurm



After completing the configuration of SLURM on the Head Node, following commands is utilised to enable and start all the necessary SLURM services:

      systemctl daemon-reload
      systemctl enable slurmdbd
      systemctl start slurmdbd
      systemctl enable slurmctld
      systemctl start slurmctld

Lastly, following command is employed to check the status of the SLURM services:

      systemctl status slurmdbd
      systemctl status slurmctld
**SLURM CONFIGURATION IN CLIENT NODE**
--
The process of configuring SLURM on the client node closely resembles that of the head node, with the primary distinction being the absence of the need to set up a database. Similar to the head node, MUNGE must be configured by creating MUNGE and SLURM groups, as well as MUNGE and SLURM users. Following this setup, MUNGE should be installed. The following command is employed to accomplish these tasks:

      export MUNGEUSER=1001 
      $ sudo groupadd -g $MUNGEUSER munge 
      $ sudo useradd -m -c "MUNGE Uid 'N' Gid Emporium" -d /var/lib/munge -u $MUNGEUSER -g munge -s /sbin/nologin munge 
      $ export SLURMUSER=1002 
      $ sudo groupadd -g $SLURMUSER slurm 
      $ sudo useradd -m -c "SLURM workload manager" -d /var/lib/slurm -u $SLURMUSER -g slurm -s /bin/bash slurm
      sudo apt-get install -y munge

Now, the munge.key file, previously copied to `/nfs/slurm`, can be further distributed to each client node by copying it to `/etc/munge/`. This can be achieved using the following command:

      sudo scp /nfs/slurm/munge.key /etc/munge/
      sudo chown munge:munge /etc/munge/munge.key
      sudo chmod 400 /etc/munge/munge.key

Once the key has been copied and permissions have been adjusted, the MUNGE service is ready to be enabled and started. This task can be accomplished using the following command:

      sudo systemctl enable munge
      sudo systemctl start munge

After setting up Munge, SLURM should be installed in the compute node. To install SLURM on the compute node, you can use the following command:

      sudo apt-get install slurm-wlm

For compute node, the same configuration file should be used as headnode. Therefore, all the configuration file from headnode must be copied to `/nfs/slurm`, which then can be copied to `/etc/slurm/` directory in compute node. 

**Copying `slurm.conf` and `slurmdbd.conf` to `/nfs/slurm` directory in headnode** 

      sudo scp /etc/slurm/slurm.conf /nfs/slurm/
      sudo scp /etc/slurm/slurmdbd.conf /nfs/slurm/

**Copying `slurm.conf` and `slurmdbd.conf` from  `/nfs/slurm` to `/etc/slurm/` directory in compute node**

      sudo scp /nfs/slurm/slurm.conf /etc/slurm
      sudo scp /nfs/slurm/slurmdbd.conf /etc/slurm

Once all the configuration files are copied, the following commands are used to set up the required directories and log files for SLURM, ensuring ownership and permissions are appropriately configured to collect SLURM messages.

      mkdir /var/spool/slurmd 
      chown slurm: /var/spool/slurmd
      chmod 755 /var/spool/slurmd

      mkdir /var/log/slurm/
      touch /var/log/slurm/slurmd.log
      chown -R slurm:slurm /var/log/slurm/slurmd.log
      chmod 755 /var/log/slurm

      mkdir /run/slurm
      touch /run/slurm/slurmd.pid (For compute node)
      chown slurm /run/slurm
      chown slurm:slurm /run/slurm
      chmod -R 770 /run/slurm

After setting up the file, the path of slurmd.pid has to be changed inside slurmd.service file, slurmd.service can be accessed using following command:

      nano /usr/lib/systemd/system/slurmd.service

After completing the configuration of SLURM on the Compute Node, following commands is utilised to enable and start the SLURM services:

      systemctl daemon-reload
      systemctl enable slurmd
      systemctl start slurmd

Lastly, following command is employed to check the status of the SLURM services:

      systemctl status slurmd


## References
1. https://hpc.uni.lu/infrastructure/network
2. https://dlcdnimgs.asus.com/websites/global/aboutASUS/OS/Linux_Status_report_202312.pdf
3. 

## Authors


