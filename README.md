# AgentBasedMonitor-Linux

step 1 : create VM-Linux Machine
step 2 : Create agent group : In Tenable ->Settings -> Sensors -> Nessus Agents -> Agent Groups -> Add Agent Group -> write your name of the group.
step 3 : scan-> create scan ->Nessus Agent ->basic agent scan -> Basic -> select Agent Group(our own the one which we created) -> Scan type : Triggered scan ->  select filename  -> write the file name -start.txt -> Save.
step 4 :  In Tenable ->Settings -> Sensors -> Nessus Agents -> Linked Agent -> add nessus agent ->  copy the code to install the agent on Linux platform :  curl -H 'X-Key: 58aab372289ac80911e4c5ad40a07b23b5524319f9ff5c010aa50ec625ccf389' 'https://sensor.cloud.tenable.com/install/agent?name=agent-name&groups=agent-group' | bash
step 5: in the above script copy to the notepad of the vm and edit the following
a) remove the -name "<agent name>" and edit group name as our group name that we made earlier.

the updated version is : curl -H 'X-Key: 58aab372289ac80911e4c5ad40a07b23b5524319f9ff5c010aa50ec625ccf389' 'https://sensor.cloud.tenable.com/install/agent?groups=Qasim-agentgroup' | bash

step 6 : copy and paste the script in the powershell and run
step 7 : then cd to this lcoation /opt/nessus_agent/var/nessus/triggers, touch start.txt  (creating a new file in the folder which is the name of trigger file)
step 8 : Watch until the file disappears. This signifies the local agent scan has begun.
step 9 : Go back to the Tenable Portal (https://cloud.tenable.com/) and observe your nessus agent should be showing up in: (settings -> Sensors -> Nessus Agents)
Ensure YOURS is in there; there could be some in there already from other people. See the “LINKED ON” date and name to find yours. If it’s not there, you may have to wait a bit longer. 
step10 :  once the file is gone go and check the scan -> select name of name and check the File name triggered as start.txt
