# MasterNode-Setup

SaveNode Masternode Setup Guide (Ubuntu 16.04)
This guide will assist you in setting up a Rhenium Masternode on a Linux Server running Ubuntu 16.04. (Use at your own risk)

If you require further assistance contact the support team @ Discord

Requirements
Check collateral and send exact coins.
A VPS (Vultr) running Linux Ubuntu 16.04.
A Windows or MAC OS X local wallet.
An SSH client such as Bitvise
Contents
Section A: Creating the VPS within Vultr.
Section B: Downloading and installing Bitvise.
Section C: Connecting to the VPS and installing the MN script via Bitvise.
Section D: Preparing the local wallet.
Section E: Connecting & Starting the masternode.
Section A: Creating the VPS within Vultr
Step 1

Register at Vultr
Step 2

After you have added funds to your account go here to create your Server
Step 3

Choose a server location (preferably somewhere close to you) Example-Location
Step 4

Choose a server type: Ubuntu 16.04 Example-OS
Step 5

Choose a server size: $5/mo will be fine Example-OS
Step 6

Set a Server Hostname & Label (name it whatever you want) Example-hostname
Step 7

Click "Deploy now"
Example-Deploy

Section B: Downloading and installing BitVise.
Step 1

Download Bitvise here
Step 2

Select the correct installer depending upon your operating system. Then follow the install instructions.
Example-PuttyInstaller

Section C: Connecting to the VPS & Installing the MN script via Bitvise.
Step 1

Copy your VPS IP (you can find this by going to the server tab within Vultr and clicking on your server. Example-Vultr
Step 2

Open the bitvise application and fill in the "Hostname" box with the IP of your VPS then click "Open" Example-PuttyInstaller
Step 3

Once you have clicked open it will open a security alert (click yes).
Step 4

Type "root" as the login/username then press enter
Example-Root

Step 5

Copy the root password from the VULTR server page. Example-RootPass
Step 6

Paste the password into the Bitvise terminal by right clicking (it will not show the password so just press enter) Example-RootPassEnter
Step 7

Paste the code below into the Bitvise terminal then press enter (it will just go to a new line)
wget -q https://github.com/savenode/MasterNode-Setup/blob/master/sndinstall.sh

Step 8

Paste the code below into the putty terminal then press enter
chmod +x sndinstall.sh
./sndinstall.sh

Click Enter when asked to generate Masternode Priv Key.

Step 11

You will now see all of the relavant information for your server.
Keep this terminal open as we will need the info for the wallet setup. Example-installing
Section D: Preparing the Local wallet
Step 1

Download and install the SaveNode wallet here
Step 2

Send EXACT collateral to a receive address within your wallet.
Step 3

Create a text document to temporarily store information that you will need.
step 4

Go to the console within the wallet
Example-console

Step 5

Type the command below and press enter
masternode outputs

Example-outputs

Step 6

Copy the long key (this is your transaction ID) and the 1, 0 or 2 at the end (this is your output index)
Paste these into the text document you created earlier as you will need them in the next step.
Section E: Connecting & Starting the masternode
Step 1

Go to the tools tab within the wallet and click open "masternode configuration file" Example-create
Step 2

Fill in the form.
For Alias type something like "MN01" don't use spaces
The Address is the IP and port of your server (this will be in the putty terminal that you still have open).
The PrivKey is your masternode private key (This is also in the putty terminal that you have open).
The TxHash is the transaction ID/long key that you copied to the text file.
The Output Index is the 0 or 1 that you copied to your text file. Example-create
Click "File Save"

Step 3

Close out of the wallet and reopen Wallet *Click on the Masternodes tab "My masternodes"
Click start all in the masternodes tab
step 4

Check the status of your masternode within the VPS by using the command below:
Rhenium-cli masternode status

*You should see *status 4

If you do, congratulations! You have now setup a masternode. If you do not, please contact me or any other support.

