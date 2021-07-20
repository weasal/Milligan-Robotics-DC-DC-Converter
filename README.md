# Converter
A DC-DC converter built around the TI LM2576
# Purpose
For the MATE robotics Explorer Category, we needed to deal with a 48V power supply.  As most of our electronics were not compatible with this voltage, we needed to convert it into something we could use.  The voltages needed were primarily 18V for our thrusters as well 5V and 12V for various electronics and servos.  Due to certain restrictions on how we could handle this conversion, size, efficiency, and simplicity were key concerns.  Because of this I elected to go with a switching power supply, specifically a buck converter, which allowed for high efficiency and widespread and available documentation.  While there was an option to build a more fundamental design, both ease of assembly as well as availability of documentation drove me to use a Texas Instruments IC.  While there the pracitical purpose was paramount, I also took the opportunity to educate myself about converter topography, board layout best practices, and PCB design tools.  
# Design Process
As I had never designed something like this, the first place I started was researching the theory and principles of power conversion.  After gaining a better grasp of the mechanics of the converter, I used Texas Instruments WEBENCH tool to pick the IC to power the converter as well as picking the passive components.  I then used EasyEDA to design the layout and generate Gerber files.
# Key Features
1. Low Cost
2. Simple assembly with minimal SMT Components
3. Relatively small dimensions
4. Easy connections
# Implantation and Retrospective.
Due to time and COVID restraints, we were unable to validate and test the design.  We elected to go with other methods due to difficulty obtaining certain components and to decrease the amount of time building, testing, and debugging our electrical system.  I was able to procure PCBs and was able to do basic continuity checks to ensure that the device had all connections routed correctly. Looking back at the design process, some compromises were made that I would like to rectify in a redesign.  Most notable of these was the inductor I had designed for was simply to big for us to fit more than a couple in our space.  While this was not a deal breaker from a general use perspective, this fact coupled with a rather low max current supported by the IC and larger than expected power demand for our ROV left this solution inadequate for powering the entire ROV.  The other major concern I have with the current design is the board layout I had created.  While everything should work as expected, there are some problems.  One is the lack of either pre-planned or standard size, meaning that any enclosure or support structure would have to be completely custom designed.  Related to this was the space wasted that likely could have been removed with better placement of various components.  The last major issue I would fix is the silkscreen.  While the components, VIN pin, and capacitor polarities are marked on the board, there are definitely some problem areas I would fix, most notably the lack of notation near the input and output terminals (While the documentation I created does include enough information to assemble and wire the device correctly, it is definitely not as user friendly as it could be).  While not an inherent flaw, I would likely not make the same compromises involving THT components, as there could have been significant space savings at the cost of ease-of-assembly if more SMT components had been used. Overall, I am proud of the work I have done on the project and look forward to continuing to iterate and improve on it.  
