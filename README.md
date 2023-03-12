# Design-and-Analysis-of-SPI-Master-Salve-using-18nm-in-Qflow

Serial Peripheral Interface, or SPI, is a very common communication protocol used for two-way communication between two devices. A standard SPI bus consists of 4 signals, Master Out Slave In (MOSI), Master In Slave Out (MISO), the clock (SCK), and Slave Select (SS). Unlike an asynchronous serial interface, SPI is not symmetric. An SPI bus has one master and one or more slaves. The master can talk to any slave on the bus, but each slave can only talk to the master. Each slave on the bus must have it's own unique slave select signal. The master uses the slave select signals to select which slave it will be talking to. Since SPI also includes a clock signal, both devices don't need to agree on a data rate before hand. The only requirement is that the clock is lower than the maximum frequency for all devices involved.

When the master of the SPI bus wants to initiate a transfer, it must first pull the SS signal low for the slave it wants to communicate with. Once the SS signal is low, that slave will be listening on the bus. The master is then free to start sending data.

There are 4 different SPI bus standards that all have to do with the SCK signal. The 4 modes are broken down into two parameters, CPOL and CPHA. CPOL stands for Clock POLarity and designates the default value (high/low) of the SCK signal when the bus is idle. CPHA stands for Clock PHAse and determines which edge of the clock data is sampled (rising/falling). The data sheet for any device will specify these parameters so you can adjust accordingly. The most common settings are CPOL=0 (idle low) and CPHA=0 (sample rising edge).

<centre><img width="550" alt="image" src="https://user-images.githubusercontent.com/99958597/224381556-528accd3-f562-4e56-b17a-844745c3962c.png"></centre>

- Reference https://alchitry.com/serial-peripheral-interface-spi-verilog

# Tool Used: Qflow
- Qflow (which includes the following tools)
- Yosys = For RTL Synthesis 
- Graywolf = For Placement
- Qrouter = For Detailed Routing
- Magic = VLSI Layout Tool
- Netgen = For LVS 
- OpenSTA = For Static Timing Analysis

