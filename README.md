# Ex:Phiedit  |  Fanmade chart editor for Phigros! 

### For mobile devices: https://github.com/sudo-000/XPE-Mobile

#### Advertisement video: https://www.bilibili.com/video/BV1aX4y1s71R

### Ex:Phiedit development hub: https://discord.gg/fgqdh8EqUq 
- **Get beta versions of Ex:Phiedit**
- **Chat with devdevelopers directly**
- **Get the latest news**
- **Report bugs and suggest features**

# 
# 
# News: 

## [2024/06/11]
### Ex:Phiedit 5.0 will come with a new component that would change the world: XPE Assembler! 
Below is the current planned features for this assembler: 
```
XPE Assembler Guide

The new Ex:Phiedit 5.0 will introduce a new concept that would significantly help the production of extremely large impossible charts: Segments! 

Even though I implemented many performance boosts that make the charting program significantly faster. 
A number of it's algorithms still remain very suboptimal and cannot satisfy the need for creating crazily large nuclear bombs that has many millions of notes. 
So I bring the Pattern concept from Fl Studio to Ex:Phiedit which would make the creation of extremely large charts many times easier. 
Each segment contains only a few hundred thousand notes, which Ex:Phiedit would certainly be able to handle that much. 
The major difference of patterns and the old chart merging thing is that by using patterns, you can significantly reduce the amount of storage space required for a long section of repetitive patterns. 

An example of that would be: 
What you want: 
AAABBBAAABBBAAABBBAAABBBAAABBBAAABBB

Using old chart merging method: 

Part1.json: 
AAABBBAAABBB
Part2.json: 
            AAABBBAAABBB
Part3.json: 
                        AAABBBAAABBB
Merging result: 
AAABBBAAABBBAAABBBAAABBBAAABBBAAABBB

Using new pattern method: 
Segment1.json: 
AAABBB

Arrangement.asm: 
LDS Segment1,EAX
CMP EAX,5,6
MOV EAX,ESP
RETN

Assembling result: 
AAABBBAAABBBAAABBBAAABBBAAABBBAAABBB

Syntax for Arrangement.asm: 
LDS [filename],[workspace]
The filename is the name of the chart file, the assembler will find it in the Resources folder automatically. 
There are four workspaces for you to use, they are: EAX, EBX, ECX, EDX, and ESP. 
In which, ESP is the final result that will be written to the harddisk. 
Content in all other workspaces will be discarded when assembling is completed. 
Example: LDS Pattern1,EAX
Meaning: Load Pattern1.json into workspace EAX. 

MOV [workspaceA],[workspaceB]
Copy data from workspaceA to workspaceB. 
The data in workspaceB will be overwritten. 
Data in workspaceA is unchanged. 
Example: MOV EAX,EBX
Meaning: Copy data from workspace EAX to workspace EBX. 

PUSH [workspaceA],[workspaceB]
Merge data in workspaceA with workspaceB. 
The merging result will be written to WorkspaceB, data in workspaceA is unchanged. 
Example: PUSH EBX,ESP
Meaning: Merge data in workspace EBX with ESP. 

POP [workspace]
Clear all data in the specified workspace.
Example: POP EBX
Meaning: Clear all data in workspace EBX

CMP [workspace],[repetition],[offset]
Clone data in the specified workspace. 
Move by the specified offset in the number of bars (float is supported). 
Then merge with itself for specified number of repetitions. 
Example: CMP EAX,10,0.25
Meaning: Clone data in workspace EAX, move 0.25 bars forward and merge with itself, repeat 9 more times. 

TYPE [mode]
Set the conversion mode, must be located at the first line of Playlist.asm file. 
Executing this instruction at anywhere else will result in an syntax error. 
Acceptable conversation modes: RPE, PEC. 
If a set instruction is not found on the first line of Playlist.asm file, the default value RPE will be used. 
In RPE mode, the assembler will read json files from the Resources folder and output a ESP.json file to Resources\ESP. 
However, no one would ever wanna store an impossible chart as json, it's just a complete waste of storage space! 
So alternatively, you can add TYPE PEC in your Arrangement.asm so it generates a pec file instead of json. 
Note that in PEC mode you must export all your charts to old pec format in the editor via Settings -> Export old format. 
A .zip file with the same filename as your chart shall appear in the Resources folder. 
This assembler program does not have the ability to convert rpe charts to pec. 
Example: TYPE RPE
Meaning: Set conversion mode to RPE. 

FST [workspace],[offset]
Move data in the specified workspace forward by specified number of bars. 
Example: FST EDX, 10
Meaning: Move data in workspace EDX forward by 10 bars. 

RETN
This will write all data in ESP to the hard disk. 
All existing data in ESP.json will be overwritten. 
You should always add this line at the end of Arrangement.asm file. 
Otherwise the merged chart will not be saved. 
You are allowed to have multiple RETN instructions in your Arrangement.asm file. 
This is useful when you're making a super large chart and you don't want the assembler program to suddenly crash and you just loose everything. 

Have fun!
```

## [2024/06/11]
### The source code of the installer will be moved to releases from now on because of the 50 mb file size limit in the repo. While in releases you can go up to 2 GB!

## [2023/05/24]
### The new FPS config is now comming!!! (Bundled with XPE 4.0 Plus)
- ![image](https://github.com/sudo-000/Ex-Phiedit/assets/107282563/4bb55063-a87a-4162-8297-14239248bf28)

## [2023/05/23]
### Ex:Phiedit v4.0 is finally completed!

- **Huge UI improvement!!!**
  - When you look at it, you wanna lick it! 
  - ![image](https://github.com/sudo-000/Ex-Phiedit/assets/107282563/2066b72a-ee58-448a-9f3a-9ad656983bae)

- **Even more performance boost!**
  - ![image](https://github.com/sudo-000/Ex-Phiedit/assets/107282563/330695b3-405d-405c-a57c-156df410a6e3)
  - ![image](https://github.com/sudo-000/Ex-Phiedit/assets/107282563/76df8090-eadb-47de-aadf-ea1f9b8d21d6)

- **More than a hundred thousand notes can be handled now!**
  - ![image](https://github.com/sudo-000/Ex-Phiedit/assets/107282563/62467f3a-6fb1-487b-b89b-fecaa281caf5)

- **Customizable FPS!**
  - ![image](https://github.com/sudo-000/Ex-Phiedit/assets/107282563/6d27737f-8e39-4da0-97b3-183fd5354785)
