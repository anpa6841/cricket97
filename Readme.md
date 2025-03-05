### Game Setup

- Download Cricket97: https://www.myabandonware.com/game/cricket-97-2bo
- Extract the ZIP file
- Install DOSBox: brew install --cask dosbox
- Move the Extracted Folder to Documents and Rename it Cricket97
- Execute these steps once to support voice mode:
    - Launch DosBox
    - mount C ~/Documents/Cricket97
    - setup.exe
        - Select Sound Blaster 16 or Sound Blaster Pro for both music and digital sound.
        - Set the following values:
            Port: 220
            IRQ: 7
            DMA: 1
        - Save and Exit

- In dosbox.conf, set the following values to match that of Sound Blaster 16/Sound Blaster Pro

[sblaster]
sbtype=sb16
sbbase=220
irq=7
dma=1

- Verify Auto-Mount & Launch Commands point to the correct folder path.

<pre>
[autoexec]
mount C ~/Documents/Cricket97
C:
cd "Game Fi~1"
CRICKDX2.BAT
</pre>

- dosbox-x -conf dosbox.conf

https://github.com/user-attachments/assets/890b1426-e511-461a-a586-3772d3fa34e1

https://github.com/user-attachments/assets/b7a736dc-95cb-412b-9eee-94588e895a02

### macOS Automator App Setup

-  Package DOSBox-X with your cricket97 directory and configuration as a standalone app

    - Open Automator (Cmd + Space, search for Automator).
    - Select "Application" as the document type.
    - Add a "Run Shell Script" Action:
        - cd ~/path/to/cricket97 && /opt/homebrew/bin/dosbox-x -conf dosbox.conf
    - Save the Automator workflow as Cricket97.app.

<img src="Automator Workflow.png" alt="drawing" width="400"/>

- Set the App Logo
    - Right-click the .app and select "Get Info".
    - Drag and drop the .jpeg onto the icon in the top-left corner.

- Launch App
    - Cmd + Space, search for cricket97.
