Installer for the ARX Data Anonymization Tool
====

This project contains configuration files for building the ARX installer. The installer is based on BitRock InstallBuilder.

Instructions
----

Download JRE/JDKs from [here](https://installbuilder.com/java/) and place the folders java-[platform] in the java folder
in the root of the repository (ignore the other files, i.e. java.xml). Current Java version: 17.0.3.

For OSX, the following [bugfix](https://git.eclipse.org/r/#/c/105553/1/features/org.eclipse.equinox.executable.feature/bin/cocoa/macosx/x86_64/Eclipse.app/Contents/Info.plist) currently needs to be applied manually after the app has been bundled.

Hashes are created with HashMyFiles.

Hashes are signed with Gpg4win.

More details about BitRock InstallBuilder can be found at: http://installbuilder.bitrock.com/   

More details about ARX can be found at: http://arx.deidentifier.org/   
