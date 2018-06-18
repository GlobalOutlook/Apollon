# Apollon
Shell script to install an [Apollon Masternode](http://apolloncoin.io/) on a Linux server running Ubuntu 16.04. Use it on your own risk.  
***

## Installation for version 2.0.0
```
rm apollon_install.sh >/dev/null 2>&1
wget -q https://raw.githubusercontent.com/zoldur/Apollon/master/apollon_install.sh
bash apollon_install.sh
```
***

## Desktop wallet setup  

After the MN is up and running, you need to configure the desktop wallet accordingly. Here are the steps:  
1. Open the ApollonCore Desktop Wallet.  
2. Go to RECEIVE and create a New Address: **MN1**  
3. Send **25000** XAP to **MN1**.  
4. Wait for 16 confirmations.  
5. Go to **Tools -> "Debug Console"**  
6. Type the following command: **masternode outputs**  
7. Go to  **Tools -> "Open Masternode Configuration File"**
8. Add the following entry:
```
Alias Address Privkey TxHash TxIndex
```
* Alias: **MN1**
* Address: **VPS_IP:PORT**
* Privkey: **Masternode Private Key**
* TxHash: **First value from Step 6**
* TxIndex:  **Second value from Step 6**
9. Save and close the file.
10. Go to **Masternode Tab**. If you tab is not shown, please enable it from: **Settings - Options - Wallet - Show Masternodes Tab**
11. Click **Update status** to see your node. If it is not shown, close the wallet and start it again. Make sure the wallet is un
12. Select your MN and click **Start Alias** to start it.
13. Alternatively, open **Debug Console** and type:
```
masternode start-alias MN1
``` 
14. Login to your VPS and check your masternode status by running the following command. If you get **Status 9**, it means your masternode is active.
```
apollon-cli masternode status
```
***

## Usage:
```
apollon-cli mnsync status
apollon-cli masternode status  
apollon-cli getinfo
```
Also, if you want to check/start/stop **Apollon**, run one of the following commands as **root**:
```
systemctl status ApollonCore.service #To check if Apollon service is running  
systemctl start ApollonCore.service #To start Apollon service  
systemctl stop ApollonCore.service #To stop Apollon service  
systemctl is-enabled ApollonCore.service #To check if Apollon service is enabled on boot  
```  
***

## Donations

Any donation is highly appreciated  

**XAP**: AMyyebyE8N5f79xLGtXRqLswjeHqbe2cBP  
**BTC**: 3MQLEcHXVvxpmwbB811qiC1c6g21ZKa7Jh  
**ETH**: 0x39d10fe57611c564abc255ffd7e984dc97e9bd6d  
**LTC**: LNZpK4rCd1JVSB3rGKTAnTkudV9So9zexB
