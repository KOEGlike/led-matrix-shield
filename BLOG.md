# An LED forearmband

I couldn't come up with a better name 😭

## What is this and why???

This is a forearm mounted 8*36 led matrix, with a cool 3d printed diffuser.

This project was made for Hack Club's [Alleyway](https://alley.hackclub.com), which had a relatively short deadline, so the main goals were to make something:

- Visually interesting, because I would ware this at Hackaday's [Supercon](https://hackaday.com/tag/2025-hackaday-superconference/)
- Not that complex, so I can finish it in the short timeframe
- Cheap and use parts that I already had, because my max budget was 50$

The [main organizer](https://alexren.me/) mentioned that something that was forearm mounted would be cool, so I came up with this idea.

## How it works

The main components are the:

- Xiao ESP32-C6, this basically does everything, charges the battery, controls the led strips/matrix, connects to your phone
- 2m of 144 LED/m WS2812b led strip, I cut this up into 8 smaller strips to make a matrix
- An 18650, this is the main power source
- Bms for the 18650, this was the most finicky part, I had to solder it onto the 18650
- 3D printed case, there are two part: the black inner shell, and the transparent outer shell, both printed in PETG

I used the [WLED](https://kno.wled.ge/) firmware, that has a nice mobile interface and REST api!

## Everything worked????

All of my hardware projects before this didn't work that easily, I always had to do a large amount of debugging to get them to work. But to my surprise, this was an outlier, the cad snap fit transparent cover, the circuitry all worked without needing to debug for hours. This may be because this was one of my simplest projects, but it still felt really good!!

## Turns out Neopixels are really resilient

They run off 3V3??? crazy

## It's really easy to remote control WLEd

When I was at supercon, I made the badge control the armband.

Here is how I did it:

The badges were designed to be very hackable, they use an esp32 and run micropython. You may notice that both the badge and the armband have an esp32 as their main SoC, so both have WiFi, and WLED uses Wifi.

So, to control the armband all I had to is to connect the badge the the armband's WiFi hotspot, and call it's REST API, and voila, you can control the armband with the supercon badge.
