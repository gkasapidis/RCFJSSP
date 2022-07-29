# RCFJSSP

This repository includes generated problem instance for the FJSSP with multiple renewable, non-renewable and cumulative resources. Such resources are used in the form of tool resources, utility resources, limited capacity machine buffers, WIP buffers and arbitrary non-renewable resources.




## Repository Contents


Instances are organized into four folders:


* Folder "Experiment 1" includes problem instance considering only limited capacity buffers

* Folder "Experiment 2" includes problem instance considering only tool resources

* Folder "Experiment 3" includes problem instance considering only WIP buffer and non-renewable arbitrary resources

* Folder "Experiment 4" includes large-scale problem instance considering all types of resources simulateneously




## Instance Format

In general the format of the RCFJSSP is based on the well establised format of the clasical FJSSP instances (see Brandimarte et. al. (1998) and Dauzere-Peres, S. and Paulli, J. (1997)) that is extended to provide information regarding multiple types of resources.


### Header

The header (first line) of the file contains 9 numbers: the number of jobs, the number of machines, the problem flexibility, the number of utility resources, the number of tool resources, the number of WIP buffers, the number of arbitrary non-renewable resources as well as two seeds used from the instance generator

#### Resources Section

The next section of the file includes the definition of all the resources of the problem (if any)

The first line of this section includes the size of the limited capacity buffers for every machine. 

The following *number of utilities* lines define the available utility resources (if any). Each line includes the ID of the utility resource and the maximum resource usage at any time of the schedule. 

The following *number of tools* lines, define the available tool reosurces (if any). Each line includes the ID of the tool resource as well as the number of copies that it is available. 

The following *number of WIP buffers* lines, define the available WIP buffers (if any). Each line includes the ID of the buffer as well as the capacity of the buffer. 

The following *number of arbitrary resources* lines, define all the non-renewable resources (if any). Each line includes the ID of the resource, the UID of the WIP buffer that it it stored as well as the start and maximum quantities of the resource.



#### Job Section

The next section of the file includes the definition of all the jobs and job operations as well as their correlation with the available resources.

Every line corresponds to a single job. The first number of the line includes the amount of resources that are **required** by the job. In the following and for every required resource two numbers are provided: the UID of the required resource as well as its required quantity. The next number includes the amount of resources that are **produced** by the job. Similarly, the UID and the produced resource quantity are provided for every produced resource. The next number includes the number of operations of the job.

The remainder of the line includes information about every job operation. For every operation the following information is provided: At first, the UID of the tool resource required for the processing of the operation is provided. The next number contains the number of machines that the operation can be processed to. For every available machine 1 + *number of utilities* numbers are provided which include : a) the processing time of the operation and b) the utility consumption rates of the operation when processed on the given machine. Note that the order tha the consumption rates are stored in the file corresponds to the order that utility resources are defined, i.e. the first rate corresponds to the first utility resource etc.







