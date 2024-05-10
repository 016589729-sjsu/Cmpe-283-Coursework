# Cmpe-283-Coursework
# Homework 1
The idea of this project is for you to deliver a Hypervisor based in instruction emulation for MIPs processor. Each assignment will incrementally build on the previous one so it is key you deliver each and every one of the assignments on time. You must use C++ for this project.
The input to your hypervisor will have two components: one will be the ASSEMBLY code of the binary to be run by a given VM and the other input file will contain configuration for the hypervisor with the line format:
config_parameter=value
For this phase you will support arithmetic and logical instructions and your hypervisor will support a single VM.
In this phase you must support the para-instruction DUMP_PROCESSOR_STATE that will pretty print the state of the processors including all registers
The following configuration parameters are to be supported:
vm_exec_slice_in_instructions=<number of instructions to execute before we context switch to another VM>
vm_binary = path of file containing assembly for this vm
Support multiple VM passed to your program as files in command line arguments:
myvmm -v assembly_file_vm1 -v assembly_file_vm2
Instructions for MIPS https://www.dsi.unive.it/~gasparetto/materials/MIPS_Instruction_Set.pdf
Links to an external site.
mips registers: http://homepage.divms.uiowa.edu/~ghosh/1-28-10.pdf


# Homework 2: Add support for VM snapshotting to your hypervisor
Your VMM should now be able to create a snapshot of a VM when it encounters the SNAPSHOT <filename> instruction in the VM assembly code and store it in a file. You should also support the capability for your VMM to support starting a VM from a given snapshot instead of the beginning of the assemebly code:
 
myvmm -v assembly_file_vm1 -s snapshot_vm1 -v assembly_file_vm2 
In the example above we will start vm1 from the snapshot but vm2 will start from the beginning

Homework 3: Add Support for live migration in your Hypervisor
In this assignment you will add support for live migration of a virtual machine. You will do so by adding support for the command MIGRATE [HOSTNAME or IP ADDRESS]. At this point the full vm and its current state will be migrated to a remote one that should receive it and complete the execution from the point where the MIGRATE was initiated.



# Project: Hypervisor Development (C++, MIPS processor emulation)

Developed a C++ hypervisor emulating a MIPS processor for instruction-level virtualization.
Supported arithmetic and logical instructions for multiple virtual machines (VMs) using assembly code.
Integrated a flexible configuration system for customizing hypervisor settings.
Implemented the DUMP_PROCESSOR_STATE para-instruction to display processor state.
Added VM snapshotting capability for efficient state preservation and restoration.
Enabled VM startup from snapshots or from the beginning of the assembly code.
Supported live migration of running VMs for workload balancing and fault tolerance.
