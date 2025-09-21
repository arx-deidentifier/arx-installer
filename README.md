Installer for the ARX Data Anonymization Tool
====

This project contains configuration files for building the ARX installer. The installer is based on BitRock InstallBuilder.

Instructions
----

0. Place runnable jar files for all platforms in the root of this repository. Adjust ```arx.xml``` to refer to the correct version.

1. Download JRE/JDKs from [here](https://installbuilder.com/java/) and place the folders ```java-[platform]``` in the ```java``` folder
in the root of the repository. Current Java version: 17.0.3.

2. Copy ```java.xml``` from one of the downloads into the folder java.

3. In java.xml replace _all_ origin values according to the following scheme, e.g.:

replace

```<origin>java-osx/*</origin>```

with

```<origin>${build_project_directory}/java/java-osx/*</origin>```

6. Update the version number in arx.xml

7. Now build the installers using InstallBuilder.

8. For OSX, the following [bugfix](https://git.eclipse.org/r/#/c/105553/1/features/org.eclipse.equinox.executable.feature/bin/cocoa/macosx/x86_64/Eclipse.app/Contents/Info.plist) currently needs to be applied manually after the app has been bundled, i.e.:

replace

```
<array>
   <string>ar</string>
   <string>cs</string>
     ...
   <string>zh_TW</string>
   <string>zh</string>
</array>
```

with

```
<array>
   <string>en</string>
</array>
```

8. Create hashes and signatures. Hashes can be created with HashMyFiles and signed with Gpg4win.

More details about BitRock InstallBuilder can be found at: http://installbuilder.bitrock.com/   

More details about ARX can be found at: http://arx.deidentifier.org/   
