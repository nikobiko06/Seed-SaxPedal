<!-- Find way to make Table of Contents-->

# Seed-SaxPedal

<!-- Find way to do progress reports in GitHub -->

## Important info 
Pin 21: VCC
Pin 20: Analog Gnd
Pin 

Audio inputs
Pin 16: Audio in 1 (L)
Pin 17: Audio in 2 (R)
Range: +/- 1.8v

Audio Output Pin 
Pin 18: Audio out 1
PIn 19: Audio out 2

According to the https://docs.daisy.audio/tutorials/_a3_Getting-Started-Audio/ The daisy uses line level, so we will need to build an amplifier.

The MCU: STM32H750IBK https://www.st.com/resource/en/datasheet/stm32h750ib.pdf
ALLIANCE MEMORY //Is info for these on the DATASHEET?
PCM3060: audio codec

### from DataSheet
The Analog inputs to the Daisy Seed are AC coupled, this nice because I don't need an external decoupling cap. 
This is interesting considering the analog pins are also the digital pins.

No info on current in the data sheet: I need to know what the const. I/O current for the pins is in case i need amplification at the input and depending on what I'm driving at the output (A buffer should be good for now and might be necessary).
https://community.daisy.audio/t/maximum-current-for-digital-pins/5099/2




Progress reports:
  - Check in this document for comments while I figure out how to make documentation look pretty
  - Also check for Pseudo Code because I need to learn how to actually create a new project with the Seed.
## Issues/Progress (Create a whole different text file for this stuff because it would take up way too much of the read me)
7/5: Attempting to create something to test if the Daisy seed will receive a signal from direct output of an electret microphone

### Step 1: Learn how to create a Daisy seed project

Following the video https://www.youtube.com/watch?v=uJ_pw5RYCm4 (I need to learn how to embed a link and give it a nice fancy name). 

Everything was going smoothly - except when trying to check if I have python on my Mac I ran "python3 -v" and it listed like a lot so I tried "python3 --version and it gave me what I needed :) - (I even messed around in python3 in the terminal by running "python3") until I tried to run ./helper.py...

I tried to use the helper.py command to create the project following the instructions of the video exactly, but big evil terminal gave me "zsh: permission denied: ./helper.py" 
I typed this error code into google and google AI recommended these 2 solutions:

Solution 1: Run with Python Interpreter
In terminal: "python3 helper.py"

Solution 2: Make the script executable

I opened helper.py in vscode and changed the shebang #!/usr/bin/env python by adding a 3 at the end of python, saved, then ran the command "chmod +x ./helper.py" in the terminal (oh boy do I need to learn these commands 🤡)

I did not do solution 1 because I wasn't sure it would follow with the videos steps. So after doing what I described for solution 2, I re-ran the command to create a new project "./helper.py create ./MyProjects/AudioInputTest --board seed" ... and this time drum roll please ... IT WORKED!

## Step 2: Find voltage and current ratings of Daisy Seed

I downloaded the documents from the Daisy seed website (https://daisy.audio/products/daisy-seed) of the Schematic, Pinout, and Data Sheet
and placed them into the DaisyExamples folder within a new folder called "seedDocs".

What are the components on the seed? (I plan to download the data sheets on these)

I am downloading KiCad so I can see the files for the Daisy Seed. Ok I'm having trouble opening them, I'm calling it for the night.
~9p - 11:37p

## Questions:
What is helper py and why is it needed for creating a Daisy Seed project?
My best guess: It's needed because when creating a new project, you need to copy from "/Users/nikopalanzi/Desktop/DaisyExamples/utils/Template" into the new project. 

Why can I go through "python3 helper.py" but I am able to run ./helper.py in the raw terminal, within the DaisyExamples folder? What is the significance of "./"?
What is zsh?
What is Vim? What is the different from Neovim? How hard is it to get into, because I would like to try it instead of VsCode?
What is the difference between python and python3 and why is there a completely separate code for it?
What is the difference between -v and --version?
My best answer: -v listed quite a lot of things, --version only listed the version "Python 3.9.6"
What is a "shebang"?
What is the significance of the helper.py being within "DaisyExamples"?
BG: It just hit me that the daisy people wrote the script, so there's a chance they just made it and it's some automated thing that I don't know about.
<!-- Pseudo Code: 
  Audio in

  Signal Processing

  Audio Out
  -->
