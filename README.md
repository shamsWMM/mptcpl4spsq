# mptcpl4spcq
CloudLab Experiment
0.1. Creating MPTCP Kernel Image on CloudLab
   Prerequisites:
     Create a CloudLab Account.
   1. Log in to your CloudLab account.
   2. Navigate to Experiments > Create Experiment Profile.
   3. Create a name for the profile such as "mptcpsixonekernel".
   4. Click on Edit Code and copy and paste the following code into the Source pop up window:
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
