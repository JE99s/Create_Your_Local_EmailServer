<h1>Creating Your hMailServer</h1>


<br />
<h2>Utilities Used</h2>

- <b>Windows 10 Operating System</b>
- <b>Browser (e.g., Google Chrome and Firefox)</b>
<h2>Environments Used</h2>
- <b>VirtualBox Hypervisor </b>

<h2>Lab Walk-through:</h2>
<p>This demonstration will go through the installation and configurations of a lightweight email server. Once the hMail Email Server is initialized, we'll utilize the Thunderbird email application to test the newly created email server.</p>
<br />
<h3>Install hMailServer on Windwos 10 VM</h3>
On my Google Chrome browser, I'll navigate to the hMailServer <a href="https://www.hmailserver.com/" target="_blank">Download</a> page. It is a 4MB setup file easy to configure. Fortnunately, there are not many prerequisites required to install this setup.
<br/>
<img src="https://i.imgur.com/ZlNDSuG.png" height="80%" width="80%" alt="hMail Server Download page"/>
<br />
Once the installer is downloaded, double-click it from wherever you downloaded it to start the setup process.
<br/>
<img src="https://i.imgur.com/x1U9zOk.png" height="65%" width="65%" alt="hMailServerSetup Select Destination Location"/>
<br />
Once we launch the setup it asks us to select the components we want to install. I am selecting all including Server and Administrative tools. Next, for selecting database server type, we'll be using the default one and using the built-in database engine (Microsoft SQL Compact). Make sure to select this option to ensure that there is a full installation, and the built-in database will be utilized.
<br/>
<img src="https://i.imgur.com/DqFWc1w.png" height="70%" width="70%" alt="Select Components"/>
<br />
<img src="https://i.imgur.com/n4yrjnw.png" height="70%" width="70%" alt="Select database server type"/>
<br />
Next, you'll be taken to the hMailServer security window to establish an administrative login password. This is the main password that we'll <b>NEED</b> to remember. Go ahead and click install once you're ready!
<br/>
<img src="https://i.imgur.com/T9JIeMy.png" height="70%" width="70%" alt="hMailServer Security"/>
<br />
<img src="https://i.imgur.com/MeQzPSe.png" height="65%" width="65%" alt="Ready to Install"/>
<br />
⚠️<b>Hold up!!! You might come across this error during installation.</b>⚠️
<br/>
<img src="https://i.imgur.com/RkNAvyo.png" height="55%" width="55%" alt="The Following applications..."/>
<br />
<img src="https://i.imgur.com/gxqpi45.png" height="55%" width="55%" alt="Error opening"/>
<br />
To fix this error, go to your Windows search bar and type in <b>Turn Windows features on or off</b> to open this section of the control panel. Select that search result.
<img src="https://i.imgur.com/mWRcXHK.png" height="45%" width="45%" alt="Turn Windows features..."/>
<br />
Make sure that the checkbox next to <b>.NET Framework 3.5</b> is filled in and click <b>OK</b>.
<br />
<img src="https://i.imgur.com/5o9XZMm.png" height="65%" width="65%" alt="Click OK"/>
<br />
Then, select the <b>Let Windows Updates Download the File for You</b> option.
<br />
<img src="https://i.imgur.com/iTQ1mex.png" height="70%" width="70%" alt="Downloading required files"/>
<br />
<img src="https://i.imgur.com/r0Na0JN.png" height="70%" width="70%" alt="Applying changes"/>
<br />
Now, we'll retry the process to install hMailServer.
<br />
<img src="https://i.imgur.com/L8yt2zb.png" height="65%" width="65%" alt="hMailServer Setup Wizard"/>
<br />
Now, when we start up hMailServer, a Connect window will show up to enable us to configure our email server. Click the <b>Administrator</b> option and sign in with the password we created earlier.
<br />
<img src="https://i.imgur.com/2h9YIEo.png" height="80%" width="80%" alt="please enter hMailServer passwd"/>
<br />
<h3>Configure Your hMailServer</h3>
Now, we'll start configuring our hMailServer. Click on the <b>Domains</b> section and select the <b>Add</b> button, then type your domain name. Keep it enabled and save the configuration.
<br/>
<img src="https://i.imgur.com/JnfiYlO.png" height="80%" width="80%" alt="Select Domains"/>
<br />
<img src="https://i.imgur.com/C9ZwOXk.png" height="80%" width="80%" alt="Click Save"/>
<br />
Next, we'll create user accounts. Expand <b>Domains</b> (by clicking the + icons) and on the <b>Accounts</b> page, click the <b>Add</b> button, and add addresses with their respective passwords. Save the settings.
<br/>
<img src="https://i.imgur.com/w78SbdQ.png" height="80%" width="80%" alt="Add Accounts"/>
<br />
<img src="https://i.imgur.com/JkGgeLw.png" height="80%" width="80%" alt="Save Accounts"/>
<br />
<img src="https://i.imgur.com/dfcrYFt.png" height="80%" width="80%" alt="Created Accounts"/>
<br />
Next, we'll proceed to disable SMTP authentication when sending emails. This option is best suited for this demonstration. You wouldn't want to provide a password every time you're sending an email, or you have an email fail to send because no authentication is provided. Expand <b>Settings</b> >> <b>Advanced</b> >> <b>IP Ranges</b> >> <b>Internet</b>. On the <b>Internet</b> section, uncheck all the check boxes under <b>Require SMTP authentication</b> and save these settings.
<br />
<img src="https://i.imgur.com/FlRsoJv.png" height="80%" width="80%" alt="Disable SMTP authentication"/>
<br />
<h3>Install and Configure Thunderbird Application</h3>
The email server should be ready to go and it is time to test it right now. Here, we'll be <a href="https://www.thunderbird.net/en-US/" target="_blank">installing</a> and using the open-source email client, Thunderbird.
<br/>
<img src="https://i.imgur.com/ODKzhwk.png" height="80%" width="80%" alt="Download Thunderbird Setup.exe"/>
<br />
Once it is installed, we'll configure the user accounts we created earlier during our hMailServer configurations. On the Local folders, create a new account and select <b>Email</b>. Let's make sure we choose the option to use an existing email. If a pop-up named <b>Mail Account Setup</b> appears, provide the usernames, Email addresses, and passwords we created earlier.
<br/>
<img src="https://i.imgur.com/nL24ToQ.png" height="60%" width="60%" alt="Mail Account Setup"/>
<br />
In case your configuration of Thunderbird is failing, use a manaul configuration to define the server names in the <b>IMAP</b> and <b>SMTP</b> sections. Set the server name as "localhost" for outgoing configurations. I did this for both users accounts <b>jacob@utsarr.com</b> and <b>user1@utsarr.com</b>.
<br/>
<img src="https://i.imgur.com/mUwUxSF.png" height="60%" width="60%" alt="Manual Configuration"/>
<img src="https://i.imgur.com/iR5zHwK.png" height="60%" width="60%" alt="Manual Configuration for user1"/>
<br />
Then, we should receive a warning message. Let's check the box that says, "I understand the risks", and click <b>Confirm</b> to continue.
<br/>
<img src="https://i.imgur.com/alm6uXG.png" height="60%" width="60%" alt="Warning!"/>
<br />
Then, we'll log in to user accounts we finished configuring.
<br/>
<h3>Send Yourself an E-mail</h3>
Once we have create Thunderbird profiles based from the hMailServer accounts, we'll try sending a couple of test emails to ensure communication between these accounts.
<br/>
<img src="https://i.imgur.com/Zfee9lp.png" height="75%" width="75%" alt="Tunderbird incoming email"/>
<br />
<img src="https://i.imgur.com/nfjFkSw.png" height="75%" width="75%" alt="Greetings message received"/>
<br />
Success!
