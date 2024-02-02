 <h1>Deploying a Security Solution with Wazuh</h1>

 ### 

<h2>Description</h2>
This project covers the deployment of Wazuh, enabling us to monitor file and Windows registry changes, identify unauthorized processes, and implement comprehensive security measures. This open-source Security Information and Event Management (SIEM) system serves as a powerful tool designed to empower users in safeguarding their devices and networks with the expertise of cybersecurity professionals. 
<br />


<h2>Tools Used</h2>

- <b>Wazuh</b>

<h2>Environments Used </h2>

- <b>Windows 10</b> (22H2)

<h2>Program walk-through:</h2>



<br />
 Let's begin by creating a new Ubuntu 22.04.3 LTS VM in VMware.   <br/>
                                              <br />
<img src="https://i.imgur.com/GJQEXwl.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

<br />
<br />
                                      <br/>
                                      <br />
<img src="https://i.imgur.com/owoEwae.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="https://i.imgur.com/HtM6M5a.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
Once created, open terminal and copy and paste this script (curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh && sudo bash ./wazuh-install.sh -a) to download and install Wazuh installation assistant.                                                                                <br/>
                                      <br />
<img src="https://i.imgur.com/0AIRWHZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="https://i.imgur.com/SmR71Ey.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="https://i.imgur.com/iSSnsMJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
Once that's done, it will display the Username and Password for the web interface. Make sure to save the password in a secure place, as we will need it shortly.                 <br/>
                                      <br />
<img src="https://i.imgur.com/20L0HfI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
Now, type the command: (ip a s) to get the IP Address of your VM and we'll use that to access the web interface of Wazuh. Make sure to enter the credentials we just received after installation like below.                                          <br/>
                                      <br />
<img src="https://i.imgur.com/AtiLp1h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
 After logging in, it will come to a page like this.                                      <br/>
                                                                                    <br />
<img src="https://i.imgur.com/FZsRFyT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
Now we can add agents to monitor.     <br/>
                                      <br />
<img src="https://i.imgur.com/DeG4x3s.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
 All I did was create a new Linux virtual machine and added that as an agent.                                    <br/>
                                      <br />
<img src="https://i.imgur.com/8BnC47u.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
 Make sure to add the server address which is our Wazuh manager address. It's optional, but I added an agent name. Then copy the command under the optional name portion and now well head over to the agent VM and install the Wazuh client in terminal.                                  <br/>
                                      <br />
<img src="https://i.imgur.com/wvl6sRo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
Ok, now open terminal and paste that code we copied from Wazuh client documentation and press enter, enter sudo password and it will download.                                        <br/>
                                      <br />
<img src="https://i.imgur.com/7dw4nvi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
Now that it is installed, let's start the agent. So let's head back over to the Wazuh documentation one more time to get the code we need to start our agent. Once entered we need to check if the client is running, so we can run the command (sudo systemctl status wazuh-agent)             <br/>
                                      <br />
<img src="https://i.imgur.com/dcWtLf9.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
And as you can see, it is up and running!   <br/>
                                      <br />
<img src="https://i.imgur.com/iXMkywE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
Heading back over to the Wazuh manager dashboard, we can see that the agent has been added!                                      <br/>
                                      <br />
<img src="https://i.imgur.com/S550CHf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
Click agents and it will show you more details about the device.    <br/>
                                      <br />
<img src="https://i.imgur.com/xS5aKSm.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
In this example, I purposely locked the screen on the VM agent and entered the wrong password to see if the agent would send this info to our Wazuh manager. And it did!                                      <br/>
                                      <br />
<img src="https://i.imgur.com/pgab1kR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />

<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                    <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>

  
<br />
<br />
                                      <br/>
                                      <br />
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br/>


<br />
<br />

