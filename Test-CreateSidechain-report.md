# Horizen SideChains Test
## Test sidechain functionalities with Sphere by Horizen 2.0.0

The goal is to test the new 'Sphere by Horizen' wallet 
in creating side chains and the interactions between side chains and the main chain. 

Here is the original call:
***********************************************************************************
HDE task

Starting points:

https://github.com/HorizenOfficial/Sidechains-SDK/blob/master/README.md
https://github.com/HorizenOfficial/zend_oo/blob/sidechains_testnet/README.md

Required steps:

* Download Sphere by Horizen 2.0.0: 
https://github.com/HorizenOfficial/Sphere_by_Horizen_Sidechain_Testnet/releases/tag/desktop-v2.0.0-beta-sidechain-testnet.

* Obtain free test ZEN (tZEN) via the Horizen Early Adopter Program (HEAP): https://heap.horizen.global/.

* Use the dedicated commands on Sphere by Horizen to declare a new sidechain.

* Perform a Forward Transfer from the mainchain to the sidechain.

* Produce a detailed report that includes screenshots of the different steps.

For more info: https://hde.horizen.global/tasks
*************************************************************************************
### **Here we have all the steps needed for the side chain creation, explained:** ###
*Test is done on a Windows 10, i5-7500*

First you need to download and install the wallet 

https://github.com/HorizenOfficial/Sphere_by_Horizen/releases/download/desktop-v1.2.8-beta/Sphere_by_Horizen-1.2.8-beta.exe,

and create account:
![Create account](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/CreateAcc.png)

After creating account you should wait for sync to finish. You can also start using wallet and create new address, but if so, you can lose that address - happened to me, so you will have to make new one (best after syncing is finished). 
Also if you close your wallet during syncing, you may experience "process already started" or similar when starting again, then you should kill/stop that proces (_zend) and start the app again.

While the wallet is syncing you should prepare your environment as mentioned here:
![Prepare your environment](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/requirements.jpg)

Check if you have adequate Java and Maven installed:
![check your java and maven!](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/java-and-maven.png)

Install Scala from: https://www.scala-lang.org/download/

Clone Zendoo SDK, 
`cd Sidechains-SDK`,
and finally `mvn package`:
![Zendoo](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/cloning%20Zendoo%20SDK.png)

This process can take a while depending on your intenet speed (>3 hours what I got), you may be prompt to enable this process trough your firewall in the middle of downloading/installing, so be cautious.
![Zendoo-package](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/package%20-%20Zendoo%20SDK.png)

If this process is finshed similar as above, you are almost ready for your first sidechain creation! :tada:

Just wait for the wallet to sync, create account and add funds from test faucet:

![syncing](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/syncing.jpg)
![ClaimFreeZEN](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/claim-free-ZEN.png)

![wallet_synced](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/synced.png)

:tada:
Now, if you've reached to this point, you're ready for the creation of your first SideChain:

First you need to open Command Prompt and navigate to your Sidechain-SDK folder. 

enter this command: 
`java -jar tools/sctool/target/sidechains-sdk-scbootstrappingtools-0.2.6.jar` *scbootstrappingtools-x.x.x.jar* depending on your version
of the tools.

enter these commands after starting java:
![bootstraping](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/start-bootstrapping2.png)
!!! Copy these keys - you gonna need them later !!!

Now to the Sidechain creation
![SideChainCreation](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/sidechain-creation.png)
![SideChainTransaction01](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/sidechain-transaction.png)
![SideChainConfirmation](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/sidechain-creation_wait-confirmation.png)

end the transaction:
![SideChainTransaction02](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/sidechain-transaction01.png)

confirmation:
![SideChainTransaction03](https://github.com/infinitEnigma/HorizenSideChains_test/blob/main/Assets/sidechain-transaction04.png)

## Conclusion ##
This was great experience, easy to follow instructions, good and clear interface and steady app, the only problem is syncing when internet isn't fast enough, it can last for days
