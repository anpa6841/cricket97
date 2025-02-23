### Game Setup

- Download Cricket97: https://www.myabandonware.com/game/cricket-97-2bo
- Extract the ZIP file
- Install DOSBox: brew install --cask dosbox
- Move the Extracted Folder to Documents and Rename it to Cricket97
- Execute these steps once to support sound output:
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

<pre>
[sblaster]
sbtype=sb16
sbbase=220
irq=7
dma=1
</pre>


- Verify Auto-Mount & Launch Commands point to the correct folder path.

<pre>
[autoexec]
mount C ~/Documents/Cricket97
C:
cd "Game Fi~1"
CRICKDX2.BAT
</pre>

- Download commentary files from here: https://archive.org/details/c97vox_zip. Extract the ZIP and
  copy all files to ~/Documents/Cricket97/Game Files/VOX.

- dosbox-x -conf dosbox.conf

https://github.com/user-attachments/assets/88f11397-7895-4362-a25a-310e83ac8ca2

https://github.com/user-attachments/assets/fea63aff-023a-4c2f-842b-d3d641101d71
