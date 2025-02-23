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

https://github.com/user-attachments/assets/710975c5-bbe0-446b-9b0f-c7d1512a6e0b

Extras:

- Game Tour: https://youtu.be/swrrQ_0j5DE?si=cN1iBRgLWX2Z9qY2

- GamePlay: https://youtu.be/qFOiHHwKd64?si=ej-gxXfbJI7-AQw7
