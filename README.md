# mptcpl4spcq CloudLab Experiment
> Prequisite: Creating a CloudLab Account.
## Part 1. Creating MPTCP Kernel Image on CloudLab
### Section 1.1 Creating a basic profile and instantiating it
   1. Log in to your CloudLab account.
   2. Navigate to Experiments > Create Experiment Profile.
   3. Create a name for the profile such as "mptcpsixonekernel".
   4. Click on Edit Code and copy and paste the following code into the "Source" pop-up window:
      ```python
      """An example of constructing a profile with a single raw PC.
      
      Instructions:
      Wait for the profile instance to start, and then log in to the host via the
      ssh port specified below.
      """
      #Based on "8.2 A single physical host" - http://docs.cloudlab.us/geni-lib.html
      
      import geni.portal as portal
      import geni.rspec.pg as rspec
      
      # Create a Request object to start building the RSpec.
      request = portal.context.makeRequestRSpec()
       
      # Create a raw PC
      node = request.RawPC("node")
      
      # Print the RSpec to the enclosing page.
      portal.context.printRequestRSpec()
      ```
   5. Click Accept then click Create.
      You will be redirected to the profile page.
   6. Click on Instantiate.
   7. Give the experiment a name such as "sixonekernel".
   8. Select CloudLab Wisconsin.
   9. Click Next then click Finish.
      Once the node is ready, move on to the section 1.2 "Installing MPTCP 6.1.49".

> At the time of this experiment,
                  the latest LTS Ubuntu version is 22.04.2, which is also the current default Ubuntu version installed on the RawPC node created above.
                  the latest LTS Linux kernel release is 6.1.49, which we will need to install.

### Section 1.2 Installing MPTCP 6.1.49
> Resources and Instructions found on https://github.com/multipath-tcp/mptcp_net-next
   1. Navigate to the <a href='https://github.com/multipath-tcp/mptcp_net-next'> Linux Kernel Development GitHub repository for Multipath TCP</a> and as instructed on the repository's main README file, explore the Documentation/admin-guide/README.rst file.
   2. Explore the <a href='https://github.com/multipath-tcp/mptcp_net-next/blob/export/Documentation/process/changes.rst'>https://github.com/multipath-tcp/mptcp_net-next/blob/export/Documentation/process/changes.rst</a> to ensure you have the necessary requirements for the kernel installation.
   3. Following steps 1 and 2 above, start by navigating to the instantiated profile created in [section 1.1](#section-11-creating-a-basic-profile-and-instantiating-it).
The Topology View tab contains the single node created in the previous section.
   4. Click on the node to view a popup menu, and click Shell.
A new tab is opened titled 'node' with a browser-based shell interface.
   5. Start by updating the package lists on the system and installing the necessary packages and tools:
   ```bash
   sudo apt update
   sudo apt install build-essential gcc make bison flex libssl-dev libncurses5-dev bc
   ```
   6. Install the full sources from the repo [http://kernel.org/](http://kernel.org/) on the user home directory.
   > longterm: 	6.1.49 	2023-08-27 	[tarball](https://cdn.kernel.org/pub/linux/kernel/v6.x/linux-6.1.49.tar.xz)
   7. 
   8. Unpack the tarball:
   ```bash
   xz -cd linux-6.1.49.tar.xz | tar xvf -
   ```
   9. Enter the linux-6.1.49 directory and ensure the kernel source directory is clean
> This instruction is part of the README file on [https://github.com/multipath-tcp/mptcp_net-next/tree/export/Documentation/admin-guide](https://github.com/multipath-tcp/mptcp_net-next/tree/export/Documentation/admin-guide#installing-the-kernel-source)https://github.com/multipath-tcp/mptcp_net-next/tree/export/Documentation/admin-guide#installing-the-kernel-source)
   ```bash
   cd linux-6.1.49
   make mrproper
   ```
   10. 
   11. 
