# Create an Equalizer for All Audio in Mac OS X

Ever wish you had a system wide equalizer to adjust all audio output in Mac OS X and not just in iTunes? Maybe you want to adjust the way all audio output sounds or maybe you just want to boost the output volume of the built-in Mac speakers. We’ll show you how to do both by creating your own universal EQ using two free tools, follow along:

**Requirements**

* [[http://code.google.com/p/soundflower/downloads/list|Soundflower]] – free download from Google Code
* [[https://developer.apple.com/downloads/index.action#|AU Lab]] – free download from Apple Developers (requires free Apple Dev ID)

Download and install both Soundflower and AU Lab, you will then need to restart your Mac to have full access to the audio components. Once rebooted, follow along with the instructions below:

## Set Up a Universal Audio Equalizer for Mac OS X

1. Set System Volume to the maximum level, do this either through the menu bar or by hitting the Volume Up key repeatedly
2. Open System Preferences from the  Apple menu and select the “Sound” panel, followed by the “Output” tab. Select “Soundflower (2ch) from the Output list
3. Now launch AU Lab, found in /Applications/Utilities/
4. From the “Audio Input Device” pulldown menu, select “Soundflower (2ch)”, and then from “Audio Output Device” menu select “Stereo In/Stereo Out”
5. Click the “Create Document” button at the bottom of the screen
6. At the next screen, look for “Output 1″ column and click the “Effects” dropdown, selecting “AUGraphicEQ”
7. This is your new system-wide equalizer, set it how you see fit. Changes here will impact all audio output on the Mac
8. When satisfied with the EQ settings, hit Command+S to save the EQ settings file and put it somewhere easy to find like the Documents folder
9. Now open AU Lab preferences from the AU Lab menu, click on the “Document” tab and click the radiobox next to “Open a specific document”, selecting the .trak EQ file you saved in the previous step

Optional final step: If you want the EQ settings to load on every Mac OS X boot, right-click on the AU Lab icon, go to Options, and select “Open at Login”

It’s important to note that AU Lab must be running in order for the equalizer to have an effect, keeping it running will consume a small amount of CPU resources but it’s much less process hungry than some of the third party alternatives available on the market.
