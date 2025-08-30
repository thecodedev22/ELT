# The ELT
**Author:** Isaac M
**Description:** So last week, I started watching Superman and Lois. I thought for my first project, I would recreate the ELT
**Created On:** 28/8/25

---

## August 28: Researched and Schematiced

### Initial Research Phase (Morning Session - 45 minutes)

Started the day by truly exploring what an Emergency Locator Transmitter actually needs to do. Having seen a couple of episodes of Superman & Lois, I noted that the ELT is a miniature distress beacon that characters can activate in moments of danger. The transmitter needs to be:

- **Highly visible** when activated (vivid flashing lights)
- **Audibly distinct** (distinct alarm/SOS signals)
- **Compact and portable** for emergency transport
- **Simple to initiate** in crisis situations
- **Error-free operation** when most needed

I studied real-world ELT devices and emergency beacons to cut through to the bottom functionality. Strobe lights, audio alarms, and radio transmission are all employed by most commercial devices. For the initial iteration, I'm limiting myself to the visual and auditory.

### Component Selection Process (30 minutes)

I reviewed each requirement and chose each component with attention:

**Microcontroller Selection:**
- Initially considered using Arduino Nano, but the **XIAO RP2040** came out on top due to its compact size, dual-core processor, and onboard USB capabilities
- RP2040's PIO (Programmable I/O) blocks will be perfect for generating precise timing patterns for SOS messages
- 21 GPIO pins will provide more than enough space for additional expansion features

**Output Components:**
- **Light bar:** Employed a high-brightness LED strip rather than individual LEDs in order to maximize visibility and showmanship
- **Buzzer:** Piezoelectric buzzer selected for loud, crisp sound without additional amplification
- Both parts selected to operate within the 3.3V logic levels of the RP2040

**Supporting Components:**
- **220Ω resistors:** One to current limit the light bar, one as pull-up for the button
- **Push button:** Simple momentary switch for single-button operation (keeping things simple for emergency use)

### Schematic Design Session (30 minutes)

The schematic design process was methodical. I started with power distribution - clean 3.3V supply to all units. XIAO RP2040 has 3.3V and 5V output, which gives flexibility according to different component specifications.

**Circuit Architecture Decisions:**
- **Single button control:** Thought about a simple press-pattern scheme (single press = SOS mode, double press = strobe mode, long press = continuous mode)
- **Direct GPIO control:** Directly connected buzzer and light bar to GPIO pins with good current limiting
- **Pull-up configuration:** Used external pull-up resistor for reliable button detection
- **Ground plane:** Offered strong ground connections throughout the circuit

The schematic is a tidy, straightforward design that should be extremely reliable. I'm quite literally **70 percent sure this is going to work**, but the only thing that gives me doubt is that I haven't tested the current draw of the light bar yet.

**Components List Finalized:**
- 1x light-bar
- 1x XIAO-RP2040
- 1x 220Ω resistor (current limiting)
- 1x small button
- 1x 220Ω pull-up resistor
- Jumper wires/connections
- Ground connections
- 1x buzzer

### 3D Case Design Session (Evening - 30 minutes)

Grand afternoon challenge: mechanical design. I completed the mechanical design segment in the evening. The case should look like Superman & Lois but be cost-effective to produce and put together.

**Design Considerations:**
- **Small size:** Large enough to fit into a pocket or emergency package
- **Accessibility for components:** Easy access to USB port for charging and programming
- **Button integration:** Recessed button to prevent accidental activation
- **Light transmission:** Transparent or clear part for light bar viewability
- **Audio output:** Holes optimally placed for buzzer sound output
- **Assembly method:** 3D printing-compatible design using minimal support material

The case design reaches a balance between realism and practicality. The proportions and design should render it instantly recognizable to the show's fans without being compromised as a working emergency device.

**Manufacturing Notes:**
- Optimized for standard FDM 3D printing
- Wall thickness optimized for strength-to-print time
- Mounting points included for internal hardware
- Snap-fit assembly to not need screws

### Technical Challenges Identified

Found a number of challenges that will need attention upon implementation:

1. **Power Management:** Needs to measure actual current usage and determine battery needs
2. **Signal Patterns:** Ensuring proper SOS timing (3 short, 3 long, 3 short with sufficient spacing)
3. **Component Integration:** Ensuring all components are correctly inserted into the planned case
4. **Durability:** Testing actual emergency usage scenarios for the case design

### Planning Next Steps

The fundamentals are established, but some implementation details need to be smoothed out:

- **Breadboard prototyping:** Breadboard prototype the circuit before committing to PCB
- **Writing firmware:** Test and create the control software
- **Refining cases:** Print trial versions and perfect the design
- **Sourcing components:** Source all components and verify specifications
- **Integration testing:** Ensure mechanical and electrical systems work together

### Reflection on Progress

**Total time taken: 1h 45 min**

That was a productive first day on the project. The research phase actually brought the requirements into focus, and having the electrical and mechanical designs laid out on paper gives us a good direction. The schematic is sound as a first cut, though I have realistic expectations as to the types of issues that will show up on implementation.

Most satisfying was actually having the 3D case design come into being - it genuinely looks like something that could be a prop on the show! The technical hurdle at this point is making certain all the electronics work as planned and will fit within the case.




