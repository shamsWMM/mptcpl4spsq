# mptcpl4spcq CloudLab Experiment
      Prequisite: Creating a CloudLab Account.
## 1. Creating MPTCP Kernel Image on CloudLab
### 1.1 Creating a basic profile and instantiating it
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

            NOTE: At the time of this experiment,
                  the latest LTS Ubuntu version is 22.04.2, which is also the current default Ubuntu version
                  installed on the RawPC node created above.
                  the latest LTS Linux kernel release is 6.1.49, which we will need to install.

### 1.2 Installing MPTCP 6.1.49
      Resources and Instructions found on https://github.com/multipath-tcp/mptcp_net-next
   1. Navigate to the <a href='https://github.com/multipath-tcp/mptcp_net-next'> Linux Kernel Development GitHub repository for Multipath TCP</a>
