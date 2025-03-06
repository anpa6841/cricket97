### Standalone App with DOSBox-X

1. Install DOSBox-X

    - brew install --cask dosbox-x

2. Download Cricket97
    - Game Files: https://www.myabandonware.com/game/cricket-97-2bo
    - Commentary Files: https://archive.org/details/c97vox_zip

3. Organize Game Files

    - Create a new directory for your app bundle
        - mkdir -p ~/Desktop/Cricket.app/Contents/MacOS
    
    - Move your game files inside the app bundle

        - mkdir -p ~/Desktop/Cricket.app/Contents/Resources
        - cp -r ~/Downloads/Cricket_97_DOS_Files_EN/ ~/Desktop/Cricket.app/Contents/Resources/
        - cp -r ~/Downloads/c97vox/ ~/Desktop/Cricket.app/Contents/Resources/Game\ Files/VOX/


4. Make DOSBox-X Auto-Use dosbox.conf

    - git clone https://github.com/anpa6841/Cricket97
    - cp <path-to-dosbox.conf> ~/Desktop/Cricket.app/Contents/Resources/

5. Copy DOSBox-X Executable

    - cp /opt/homebrew/bin/dosbox-x ~/Desktop/Cricket.app/Contents/MacOS/Cricket
    - chmod +x ~/Desktop/Cricket.app/Contents/MacOS/Cricket

6. Create a wrapper script inside Contents/MacOS directory

    - cp <path-to-dosbox-x> ~/Desktop/Cricket.app/Contents/MacOS/dosbox-x


- chmod +x ~/Desktop/Cricket.app/Contents/MacOS/dosbox-x

7. Sound Test

https://github.com/user-attachments/assets/01c34df4-98ee-4cec-8f61-d6dcf3f0f3cd

8. Add Info.plist

    - cp <path-to-Info.plist>  ~/Desktop/Cricket.app/Contents/Info.plist

9. Add an App Icon

- mkdir icon.iconset
- cp <path-to-icon.png> .

<pre>
sips -z 16 16     icon.png --out icon.iconset/icon_16x16.png
sips -z 32 32     icon.png --out icon.iconset/icon_16x16@2x.png
sips -z 32 32     icon.png --out icon.iconset/icon_32x32.png
sips -z 64 64     icon.png --out icon.iconset/icon_32x32@2x.png
sips -z 128 128   icon.png --out icon.iconset/icon_128x128.png
sips -z 256 256   icon.png --out icon.iconset/icon_128x128@2x.png
sips -z 256 256   icon.png --out icon.iconset/icon_256x256.png
sips -z 512 512   icon.png --out icon.iconset/icon_256x256@2x.png
sips -z 512 512   icon.png --out icon.iconset/icon_512x512.png
sips -z 1024 1024 icon.png --out icon.iconset/icon_512x512@2x.png
iconutil -c icns icon.iconset
</pre>

- mv icon.icns ~/Desktop/Cricket.app/Contents/Resources/Cricket.icns

### Create DMG Installer

1. Organize Application files

- mkdir -p ~/Desktop/Cricket_DMG
- cp -r ~/Desktop/Cricket.app ~/Desktop/Cricket_DMG/
- ln -s /Applications ~/Desktop/Cricket_DMG/Applications

2. Generate the .dmg file

- hdiutil create -volname "Cricket" -srcfolder ~/Desktop/Cricket_DMG -ov -format UDZO ~/Desktop/Cricket97.dmg

### Cricket97 Pre-installed DMG Installer 

- Link: https://drive.google.com/file/d/1nDE2tit6WPedNj7whFC7nHaNy9HoB1h4/view?usp=drive_link

### Windows Installer

- https://www.myabandonware.com/game/cricket-97-ashes-tour-edition-ftc

https://github.com/user-attachments/assets/890b1426-e511-461a-a586-3772d3fa34e1

https://github.com/user-attachments/assets/b7a736dc-95cb-412b-9eee-94588e895a02


P.S. Most of the troubleshooting went in figuring out why the path to the Game Files were not getting mounted. The issue
    was with how DOSBox-X handles longer filenames. In DOS, filenames are converted to an 8-character name followed
    by a 3-character extension. The first 6 characters of the folder name are used. A `~1` is appended to indicate a
    shortened version. DOSBox-X uses DOS 8.3 filename format (short file names) which is why /Applications gets shortened to /applic~1. This can be avoided by simply enclosing the file paths in double quotes (the good ol' solution). Other
    improvements include a more organized and professional looking file structure for a typical MacOS App. DMG installer makes
    the game more accessible with a user-friendly installation support. And for some reason, voice commentary and the game itself
    is working much better now. And of course, you can launch it quickly using `Cmd + Space` now that it's a pre-installed application.
