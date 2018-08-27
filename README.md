SaveNode Masternode Setup Guide

This guide is for a single masternode setup on Ubuntu 16.04 64bit server (VPS), controlled from your local computer / SaveNode wallet.
You will need:

- 2000 SNO (check latest collateral)
- Main computer to run your SaveNode wallet (this holds your 2000 SNO collateral)
- Masternode Server (VPS – will be running 24/7)
- A unique IP address for your VPS

Setting up your VPS:
There are many hosting services available online that will allow you to create a VPS. We use Vultr.com and their $5 a month VPS running 1 CPU core, 1GB RAM and Ubuntu 16.04.
First you will need to create your VPS and make a note of the IP address of the machine.
Using Putty On your VPS go to the home directory and type:

wget -q https://raw.githubusercontent.com/savenode/MN/master/sndinstall.sh

chmod +x sndinstall.sh

./sndinstall.sh

Let this run, and when prompted for a masternode key, or press enter to generate one, press enter.

This will take a couple of minutes to complete and then will present you with your masternode key.
Do not close your terminal/ command prompt window at this point, just so you can keep your masternode key to hand.

Now on to the local wallet.
Configuring Local Wallet:
On your local machine, download the wallet for your operating system here:
https://github.com/savenode/SaveNodeCore/releases/tag/V1.2.1

Once the wallet is installed you will need to ensure you have your 2000 SNO collateral for your MN.
An easy way to do this is to go to Receive on your wallet, for label type in MN1 or the chosen name for your masternode, 2000 in the amount and click request payment.
Copy the receiving address in the dialog box.
Now, go to the Send tab in your wallet and paste this address, which should then automatically populate the label as MN1 or your chosen label.

Once your transaction has over 20 confirmations, you should be able to get your masternode outputs.
To do this go to Tools > Debug Console and type in masternode outputs.
You should see something like: “txhash” : “334545645643534534324238908f36ff4456454dfffff51311”,
“outputidx” : 0,
Now you need to put all of this together in your masternode config file.
Go to Tools > Open Masternode configuration file.
In here, you need to put the details of your masternode on a new line (with no # as shown in the examples) as such:
MN1 IP:29711 Masternode Key TXHASH Outputindex
Paste the key from your VPS, and then the masternode output and output id you just generated from your wallet.
Save the file, close it and then restart your wallet.
Once the wallet has restarted and sync’d you can go to the masternode tab in the wallet, and you should see it there. Now, right click the masternode and click start missing.
You have successfully setup your masternode.
