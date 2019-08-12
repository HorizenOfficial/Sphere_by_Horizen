**Version:** 1.1.2-beta

**Due to significant improvements to data handling, users who took part in the version 1.0.1-beta or earlier are advised to create new accounts and restore their wallet seeds.**

An upgrade mechanism will be included in a future release to remove the requirement on the user to perform this step.

For a list of changes implemented in this version, please view the [changelog](CHANGELOG.md).

**User manual:** [https://horizenofficial.atlassian.net/wiki/spaces/ZEN/pages/714604770/Sphere+By+Horizen+User+Manual](https://horizenofficial.atlassian.net/wiki/spaces/ZEN/pages/714604770/Sphere+By+Horizen+User+Manual)

Sphere by Horizen is envisioned as a launching point for Horizen services. Version 1.1.0-beta hosts wallet functions with the following features:

* Full client with both transparent, private transactions

* Lite client with transparent transactions

* The wallet is deterministic, meaning if you lose your account, you can restore cryptocurrency funds through a user-friendly process involving a unique 24-word phrase 

* Secure messaging with full client version 

* Ability to switch between a full or light client 

* Ability to run a full node

* `zen-cli` restricted terminal for advanced wallet users

* More features coming soon!

Supported Operating Systems

For beta launch, we are currently only supporting 64 bit x86 CPUs. 32 bit and ARM64 support may be considered in future releases.

* Windows 10 64 bit

* macOS Sierra and above 64 bit

* Ubuntu 18.04.1 LTS 64 bit

* Linux Mint 19 Tara 64 bit

* Debian 9 64 bit

Recommended system specifications for running in full mode.

* Available memory 4GB (RAM + swap).  

* Intel Haswell architecture CPUs (or AMD equivalent) and newer.

* Due to the size of the blockchain at this point we would recommend keeping a minimum of 30GB of storage space free. This requirement will increase over time  with blockchain growth. 

Installation instructions

* All installers are available here [https://github.com/ZencashOfficial/Sphere_by_Horizen/releases/latest](https://github.com/ZencashOfficial/Sphere_by_Horizen/releases/latest) 

* For Windows, download and run the .exe installer package and follow the standard windows installation procedure. 

* For macOS, download and run the latest standard macOS package

  macOS packages have the ".dmg" file extension.

  Please install as you would any other non-app store macOS package by launching the file  (double click) and moving the app    to your Applications folder via the installer window.

* For Linux we supply both .deb packages for Debian systems and also a standalone AppImage to support other Linux based   distributions.

  ".deb" images can be opened and installed via a graphical package manager should you have one installed.

  You may also install via the terminal for example.
  ```
  $ sudo dpkg -i example_file_name.deb
  ```
  AppImage files are self-contained and can be launched by firstly making the AppImage file executable via
  ```
  $ chmod a+x example_file_name*.AppImage
  ```
  And then run
  ```
  $ ./example_file_name*.AppImage
  ```
Licensing Requirements:

* Use of the software and services is provided pursuant to the following [Terms of Use](https://www.horizen.global/terms)

* Disclaimer
Horizen is committed to user privacy. Sphere by Horizen (the “Service”) does not store or collect data that can be attributed to any individual user. The Service includes a Horizen news feed that is served from an NGINX web server. The logs from this web server are fed to our Matomo web analytics platform, which by default anonymizes user data. The Service does not include a tracking code from Matomo and only ingests web server logs. The news feed server logs are deleted after import into Matomo and the visitor ID is anonymized. The service also includes up to date coin price metrics from a Horizen hosted api server. This is served from an NGINX web server. The logs from this server are NOT sent to matomo and are deleted on rotation. These logs are NOT used for tracking in any way.
