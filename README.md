# flashforge-ad5m-5mpro-research
Hardware and software researches and upgrades for Flashforge adventurer M5/M5 PRO

## The purpose of this research
I want to improve my 5M printer by adding some functionality from the 5M Pro (air filtration, closed chamber, maybe a webcam). I also want to connect an ERCF MMU to it. I am 100% sure that this printer is controlled by a klipper (look at the [software](./software/) directory).

## PCB Differences between 5M and 5M Pro
<img src="./photo/_5m_full_view_marked.png" width="600" />
The main points and differences that I was able to discover are:

1. USB connector, not used in the basic version, and seemingly not used in the pro version (free USB?).
2. TVOC connector, used in the Pro version to connect something (possibly a camera, not confirmed), has RX/TX pins. Looks like serial camera (lie ptc06?)*.
3. Servo connector, the photo of the Pro version shows the servo wire going into the air circulation system, probably the servo is needed to control the air flow (internal circulation/external)*.
4. Fan connector to the air outlet.
5. Connector connecting the fan to the air inlet.
6. Part of the board, apparently responsible for turning the printer on and off by button (based on the name of the pwr-on button)*.
7. Unknown connector, not connected anywhere even on the Pro version.*.
8. 1 more free USB! Yay!

(*) Not soldered on the base version.
