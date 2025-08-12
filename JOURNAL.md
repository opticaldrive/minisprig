---
title: "Mini Sprig"
author: "na"
description: "Sprig, but mini and Game Boy style"
created_at: "2025-08-05"
---

# August 5: Start, eyeballing, display, mcu
I'll probably be using a Xiao Rp2040 and one of those1.8  inch adafruit TFTs(same as the original sprig, grounded is giving these out)
After some estimation, slack threads, physical measurement, and 3d models, I think that the xiao will fit under the TFT if the TFT sits on standard headers(Sprig uses 5MM tall headers, but I'll likely have to use standard height headers)
<img width="935" height="368" alt="Screenshot 2025-08-05 at 8 31 23 PM" src="https://github.com/user-attachments/assets/e4e50785-1b47-469b-99e8-04eea2b586dd" />

Sorry for less then ideal detailed log, I'm kind rushing rn sorry.

Total time: 1 hours.


# August 6: Buttons + looking for IO expander
Added the buttons!
Also looking for a GPIO expander, might go with MCP one like adafruit has
https://www.adafruit.com/product/5346

Not sure if I should have the buttons be on a GPIO expander, or something else...

<img width="452" height="285" alt="Screenshot 2025-08-06 at 6 15 19 PM" src="https://github.com/user-attachments/assets/6ac0195a-beab-49bc-a185-0496dc61ad3c" />
Total time: 0.75 hours

# August 8:
Okay where do I begin.
I did a lot of stuff today,
<img width="991" height="552" alt="Screenshot 2025-08-08 at 5 45 43 PM" src="https://github.com/user-attachments/assets/25939c06-46b4-48bd-9059-8a992c1bc486" />
Adding QWIIC, wired the buttons to the GPIO expander(or that might have been yesterday i forgot)
Running out of GPIO :sob:
Also added an expansion header, there's power, SPI, I2C on it. SPI will kinda be useless since CS pins would have to be on the MCP23017
Using a MAX98357A for amplifier(speaker TBD), and MCP23017 for GPIO expander.
technically we DO have enough pins to implement a sprig on this but:
There is NO more UART on the expansion header(top), and no more pins...
soooo idk if i'll do it this way.
Also I'm playing with the idea of using  a pico again instead<img width="856" height="618" alt="Screenshot 2025-08-08 at 5 48 40 PM" src="https://github.com/user-attachments/assets/98325394-a845-4642-8eac-149fdea89f93" />
 of a Xiao RP2040
It does look very borked.

Or, two or three versions.
1. Using pico, no ESP32 updates later :( (ESP32 xiao and USBC are the only reasons i don't 100% want to use a pico)
2. Xiao - Limited Expansion Header
3. Xiao - No Speakers
Cutting the speakers gives me 3 GPIO which is enough to get me off the ground ag<img width="246" height="288" alt="Screenshot 2025-08-08 at 5 50 24 PM" src="https://github.com/user-attachments/assets/bba25e3b-743f-412a-a155-f4fbe178fb7d" />
ain.
I spent a really long time talking with deepseek on optimal pin arrangements
We have enough GPIO for my ideal plans if we put TFT_CS and CARD_CS on the MCP23017, but deepseek kept yelling at me about not doing that lol. 
ok thank you bye
Total time: 4 hours

# August 11: Back to the pico
Back to the pico for this version!
I wired all the buttons back up, nuked the xiao and gpio expander.
Expansion header moved to left. idk if its ideal

<img width="826" height="861" alt="Screenshot 2025-08-11 at 9 13 25 PM" src="https://github.com/user-attachments/assets/8f9eb370-5491-4602-a1c2-846df4fdf392" />
wired the schematic to a pico instead
<img width="811" height="606" alt="Screenshot 2025-08-11 at 9 14 49 PM" src="https://github.com/user-attachments/assets/d170996e-9d5a-4b87-8933-325fe43192ed" />
I'm probably going insane with the amount of like guessing and eyeballing and hopes and prayers on this.

Total time: 4 hours
