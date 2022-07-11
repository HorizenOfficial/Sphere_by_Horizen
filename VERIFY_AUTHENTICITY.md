# Verifying Installer Files

It is highly recommended to verify the authenticty of the downloaded files before installing them by checking the PGP signatures. Alternatively you can verify the file integrity by calculating the checksums. You may do so by following the instructions provided here.

## Windows
### Verify File Authenticity
1. Download Sphere_by_Horizen-1.4.0-beta.exe and Sphere_by_Horizen-1.4.0-beta.exe.asc and store the files in your Downloads folder.
2. Download the GNUPG package from https://www.gpg4win.org/get-gpg4win.html
3. Proceed with the installation and launch Kleopatra.
4. Unless you already have a personal GPG key, you will have to create one (required for step 6):
    - Select the menu item File -> New keypair -> Create a personal OpenPGP key pair.
    - Enter a name and an email address that suit you personally.
    - Choose a passphrase to protect your personal key (NOTE: the passphrase can be empty, but it is not recommended if you intend to use GNUPG in future).
5. Import the key used to sign releases:
    - File -> Lookup on Server
    - Allow network access to 'dirmngr', if the prompt arises
    - Search for cronic@horizenlabs.io
    - Select and import the key
    - Do not certify the key just yet
    - Right-click on the key, and choose "Details"
    - Ensure that the fingerprint is 219F 5574 0BBF 7A1C E368  BA45 FB70 53CE 4991 B669
    - If it's not, the wrong key was imported, right click and delete
    - If it is, we are good to go
6. Certify the key (this designates trust and is required for the next step):
    - Once you have a personal GPG key, right-click on the imported key and choose Certify
    - Enable the user ID
    - Tick the I have verified the fingerprint checkbox (since you did, as per step 5), and proceed.
    - You should receive a message saying Certification successful
7. Verify the installer binary:
    - Click the Decrypt/Verify button on the Kleopatra toolbar
    - Choose the Downloads\Sphere_by_Horizen-1.4.0-beta.exe file in the file dialog (the .asc signature file must reside in the same directory)
8. If the verification is successful, you will receive a green-tinted message box saying:
    - Valid signature by cronic@horizenlabs.io
    - Date of signature
    - With certificate 219F 5574 0BBF 7A1C E368 BA45 FB70 53CE 4991 B669
    - Anything else would constitute a signature verification failure.
### Verify File Integrity
1. Download Sphere_by_Horizen-1.4.0-beta.exe and Sphere_by_Horizen-1.4.0-beta.exe.sha256 and store the files in your Downloads folder
2. Open a PowerShell window
3. Verify the checksums by copy/pasting the following commands:
    ```
    cd ~\Downloads
    $targetHash = (Get-Content -Path Sphere_by_Horizen-1.4.0-beta.exe.sha256 -Delimiter " ")[0].Trim()
    $fileName = (Get-Content -Path Sphere_by_Horizen-1.4.0-beta.exe.sha256 -Delimiter " ")[2].Trim()
    if ($(certutil -hashfile $fileName SHA256)[1] -replace " ","" -eq $targetHash) {
      Write-Host $fileName":  OK"
    } else {
      Write-Host $fileName": FAILED`nWARNING: 1 computed checksum did NOT match"
    }
    
    ```
4. The output of the command should equal:
    ```
    Sphere_by_Horizen-1.4.0-beta.exe: OK
    ```

## MacOS
### Verify File Authenticity
1. Download Sphere_by_Horizen-1.4.0-beta.dmg and Sphere_by_Horizen-1.4.0-beta.dmg.asc and store the files in your Downloads folder.
2. If you already have the GPG Suite installed, and a personal key generated, please skip to step 5, and if not, proceed with the next step.
3. Go to https://gpgtools.org, head to the GPG Suite section, download the .dmg file and install it:
    - Right-click the .dmg file, then Open, which will open a new window with two icons: Install and Uninstall
    - Right-click the Install icon, and choose Open with.. -> Installer, which should start the GPG Suite installer
    - Follow through the installation wizard
4. Once GPG Suite installation completes, it will ask you to create a new key pair (this is required for step 6, so please don’t skip it):
    - Enter a name and an email that suit you personally.
    - Choose a passphrase to protect your personal key (NOTE: the passphrase can be empty, but it is not recommended if you intend to use this key and GPG Suite in future).
5. Import the key used to sign releases:
    - Select Key -> Lookup Key on Key Server in the application menu
    - Search for cronic@horizen.io
    - Choose the key with fingerprint 4991B669 with the user ID "cronic <cronic@horizenlabs.io>", then click Retrieve Key
    - Verify (right-click the imported key, then Details) that the fingerprint of the imported key is 219F 5574 0BBF 7A1C E368 BA45 FB70 53CE 4991 B669
    - If it’s not, the wrong key was imported, right-click and delete
    - If it is, we are good to proceed with the next step.
6. Sign the imported key (this designates trust and is required for the next step):
    - Right-click on the imported key, then "Sign".
7. Verify the installer binary:
    - Right-click the Sphere_by_Horizen-1.4.0-beta.dmg file in Finder (do NOT right click on the .asc file, that will not work), then select Services -> OpenPGP: Verify Signature of File (the .asc signature file must reside in the same directory)
    - The Verification Results dialog will then appear with the verdict:
    ```
    Trusted signature
    cronic <cronic@horizenlabs.io>
    219F 5574 0BBF 7A1C E368  BA45 FB70 53CE 4991 B669
    ```
    - Anything different means there was no valid signature for the installer.
### Verify File Integrity
1. Download Sphere_by_Horizen-1.4.0-beta.dmg and Sphere_by_Horizen-1.4.0-beta.dmg.sha256 and store the files in your Downloads folder
2. Open a Terminal window
3. Verify the checksums by copy/pasting the following command:
    ```
    cd ~/Downloads \
    && shasum -a256 -c Sphere_by_Horizen-1.4.0-beta.dmg.sha256
    
    ```
4. The output of the command should equal:
    ```
    Sphere_by_Horizen-1.4.0-beta.dmg: OK
    ```

## Linux
### Verify File Authenticity
1. Download Sphere_by_Horizen-1.4.0-beta.deb and Sphere_by_Horizen-1.4.0-beta.deb.asc and store the files in your Downloads folder for Debian based systems, or Sphere_by_Horizen-1.4.0-beta.AppImage and Sphere_by_Horizen-1.4.0-beta.AppImage.asc and store the files in your Downloads folder for all other Linux systems.
2. Ensure that the gpg2 command is available (assuming Ubuntu Linux) in your shell, and if not execute the following shell command:
    ```
    sudo apt-get update \
    && sudo apt-get install gnupg2 dirmngr
    ```
3. Unless you already have a personal GPG key, create one (this is required for step 5):
    ```
    gpg2 --generate-key
    ```
    - Supply a user ID (real name and email) that suit you personally
    - Choose a passphrase to protect your personal key (NOTE: the passphrase can be empty, but it is not recommended if you intend to use this key and GNUPG in future)
4. Import the key used to sign releases:
    ```
    gpg2 --keyserver hkps://keys.openpgp.org --recv-keys 219F55740BBF7A1CE368BA45FB7053CE4991B669
    ```
    - The output of the command should show:
    ```
    gpg: key FB7053CE4991B669: public key "cronic <cronic@horizenlabs.io>" imported
    gpg: Total number processed: 1
    gpg:               imported: 1
    ```
5. Sign the key (this designates trust and is required for the next step):
    ```
    gpg2 --lsign 219F55740BBF7A1CE368BA45FB7053CE4991B669
    ```
6. Verify the installer binary using the .asc signature (the .asc signature file must reside in the same directory as the installer binary):
    ```
    cd ~/Downloads \
    && gpg2 --verify Sphere_by_Horizen-1.4.0-beta.*.asc
    ```
    - Successful verification should produce a message like follows:
    ```
    gpg: assuming signed data in 'Sphere_by_Horizen-1.4.0-beta.{extension}'
    gpg: Signature made Tue 26 Oct 2021 14:48:10 UTC
    gpg:                using RSA key FB7053CE4991B669
    gpg: checking the trustdb
    gpg: marginals needed: 3  completes needed: 1  trust model: pgp
    gpg: depth: 0  valid:   1  signed:   1  trust: 0-, 0q, 0n, 0m, 0f, 1u
    gpg: depth: 1  valid:   1  signed:   0  trust: 1-, 0q, 0n, 0m, 0f, 0u
    gpg: next trustdb check due at 2023-04-06
    gpg: Good signature from "cronic <cronic@horizenlabs.io>" [full]
    gpg:                 aka "cronic <cronic@zencash.com>" [full]
    gpg:                 aka "cronic <cronic@zensystem.io>" [full]
    gpg:                 aka "cronic <cronic@horizen.global>" [full]
    ```
### Verify File Integrity
1. Download Sphere_by_Horizen-1.4.0-beta.deb and Sphere_by_Horizen-1.4.0-beta.deb.sha256 and store the files in your Downloads folder for Debian based systems, or Sphere_by_Horizen-1.4.0-beta.AppImage and Sphere_by_Horizen-1.4.0-beta.AppImage.sha256 and store the files in your Downloads folder for all other Linux systems.
2. Open a Terminal window
3. Verify the checksums by copy/pasting the following command:
    ```
    cd ~/Downloads \
    && sha256sum -c Sphere_by_Horizen-1.4.0-beta.*.sha256
    
    ```
4. The output of the command should equal:
    ```
    Sphere_by_Horizen-1.4.0-beta.{extension}: OK
    ```
