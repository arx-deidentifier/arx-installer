# Installer for the ARX Data Anonymization Tool

This project contains configuration files for building the ARX installer.
The installer is based on BitRock InstallBuilder.

## Instructions

1. Place runnable JAR files for all platforms in the root of this repository.

2. Download JRE/JDKs from [here](https://installbuilder.com/java/) and place the folders `java-[platform]` in the `java` folder in the root of the repository. Current Java version: **21.0.3**.

3. Copy `java.xml` from one of the downloads into the folder `java`.

4. In `java.xml` replace *all* `<origin>` values according to the following scheme, for example:

   Replace:
   ```xml
   <origin>java-osx/*</origin>
   ```
   With:
   ```xml
   <origin>${build_project_directory}/java/java-osx/*</origin>
   ```

5. Update the version number in `arx.xml`.

6. Build the installers using InstallBuilder.

7. For macOS apply the following [bugfix](https://git.eclipse.org/r/#/c/105553/1/features/org.eclipse.equinox.executable.feature/bin/cocoa/macosx/x86_64/Eclipse.app/Contents/Info.plist) manually after the app has been bundled:

   In `Info.plist` replace:
   ```xml
   <array>
      <string>ar</string>
      <string>cs</string>
      ...
      <string>zh_TW</string>
      <string>zh</string>
   </array>
   ```
   With:
   ```xml
   <array>
      <string>en</string>
   </array>
   ```

8. Create hashes and signatures. Hashes can be created with **HashMyFiles** and signed with **Gpg4win**.

---

More details about [BitRock InstallBuilder](http://installbuilder.bitrock.com/)  
More details about [ARX](http://arx.deidentifier.org/)
