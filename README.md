# sky130-CMOS-Design-SPICE-Workshop
CMOS Circuit Design and SPICE Simulation using SKY130 Technology Workshop
<br>
![banner-1024x683 png](https://github.com/user-attachments/assets/eb9603eb-d60f-4130-b18b-907fd08edc8f)
<br>
**Brief description of the course**
<br>
VLSI System Design organized a ten day workshop on CMOS circuit design and SPICE simulation using SKY130 technology.The workshop offered an in-depth knowledge of the MOSFET fundamentals, CMOS inverter behaviour, switching thresholds, noise margins, dynamic simulations and how the power supply and device variations such as etching and oxide thickness affect the circuit, all reinforced through hands-on CMOS/SPICE exercises, including circuit simulation, waveform analysis and real device exploration.
<br>
This workshop was structured into five sections:
<br>1) NMOS Fundamentals: Basics of drain current (Id), drain-to-source voltage (Vds) and their characteristic plot
<br>2) Velocity Saturation and Basics of CMOS Inverter voltage tranfer characteristics and plot between Id and Vgs and plot to determine Vt
<br>
3) Switching threshold and dynamic simulations: Analyzing PMOS/NMOS W/L ratios and threshold voltage (Vm) through practical simulations
<br>
4) Evaluating CMOS Noise margins and inverter robustness
<br>
5) Lastly, studying the impact of power supply and device variations (etching, oxide thickness) on circuit and evaluating their robustnes. We studied the advantages and disadvantages of using small power supply and also the impact of device variation on single inverter and and inverter chain were discussed.
<br>Each section included practical lab exercises using SPICE- which enables us to apply theory to simulate circuits, study the waveforms and observe real device behaviour practically.
<br>
**INDEX:**
    <ul>
      <li>Basics of NMOS Drain Current (Id) vs Drain-to-source Voltage (Vds)
        <ul>
          <li>Part 1: Introduction to Circuit Design and SPICE Simulation (Id)</li>
          -What was learnt
          <li>Part 2: NMOS Resistive region and Saturation region of operation (Id)</li>
          -What was learnt
          <li>Part 3: Introduction to SPICE</li>
          -What was learnt
          <br>-Lab Activity
        </ul>
      </li>
      <li>Velocity Saturation and basics of CMOS inverter VTC
        <ul>
          <li>Part 1: SPICE Simulation for lower nodes and velocity saturation effect</li>
          -What was learnt
          <br>-Lab Activity
          <li>Part 2: CMOS voltage transfer characteristics (VTC)</li>
          -What was learnt
        </ul>
      </li>
      <li>CMOS Switching threshold and dynamic simulations
        <ul>
          <li>Part 1: Voltage transfer characteristics and SPICE simulations</li>
          -What was learnt
          <br>-Lab Activity
          <li>Part 2: Static behavior evaluation- CMOS inverter robustness- Switching threshold</li>
          -What was learnt
        </ul>
      </li>
      <li>CMOS Noise Margin robustness evaluation
        <ul>
          <li>Part 1: Static behavior evaluation- CMOS inverter robustness- Noise margin </li>
          -What was learnt
          <br>-Lab Activity
        </ul>
      </li>
      <li>CMOS power Supply and device variation robustness evaluation
        <ul>
          <li>Part 1: Static behavior evaluation- CMOS inverter robustness- Power supply variation </li>
          -What was learnt
          <br>-Lab Activity
          <li>Part 2: Static behavior evaluation- CMOS inverter robustness- Device variation </li>
          -What was learnt
          <br>-Lab Activity
        </ul>
      </li>
    </ul>
  </li>
</ul>
<ul style="list-style-type: circle;">
  <li>Conclusion</li>
  <li>References</li>
</ul>
<h2>Basics of NMOS Drain Current (Id) vs Drain-to-source Voltage (Vds)</h2>
In the first session of the workshop, we began by understanding the significance of SPICE as a powerful tool for circuit design and analysis, demonstrating how it can be used to tune the cell delays by varying the W/L ratio of the transistors. The fundamentals of NMOS transistors were then introduced, with a focus on threshold voltage and the different regions of operation—cut-off, resistive, and saturation. This was followed by a detailed study of the relationship between drain current (Id) and drain-to-source voltage (Vds). The session concluded with the practical setup of SPICE, where we simulated Id–Vds characteristics at varying gate-to-source voltages (Vgs), reinforcing both theoretical concepts and hands-on application.
<ul>
 <h3>Part 1: Introduction to Circuit Design and SPICE Simulation</h3>
    <h4>What was learnt</h4>
    In this we learnt how SPICE can be used to study the device behaviour by simulating the circuits and analyzing the waveforms. W/L ratio is an important parameter in deciding the device performance. 
    <br>We study the structure of NMOS- it consists of a p-type substrate, has 4 terminals (G,S,D,B), an isolation region created from SiO2 is present to isolate different devices, 2 n+ diffusion regions known as source and drain near the isolation region, a gate oxide layer deposited on the substrate followed by a poly-Si or metal gate layer on top of it. 
   <br>G stands for gate
    <br>S stands for source
    <br>D stands for drain
    <br>B stands for body
    <br>Body terminal can be used to tune the threshold voltage.
    <br>
    <b>Threshold Voltage (Vt)</b>- This is the minimum gate-to-source voltage (Vgs) required to form a conducting channel at the semiconductor surface or we can say that this is the voltage where "strong inversion" happens.
    <br>
    <b>Strong Inversion</b>- When Vgs is sufficiently large, the surface inverts to n type, creating a channel of mobile electrons that allows current to flow from drain to source.
    <br>2 cases were discussed:
    <br>1. Vsb=0; here no body bias is applied. In this case, the threshold voltage remains at its nominal value and strong inversion occurs as soos as Vgs exceeds this value
    <br>2. Vsb?0; here a +ve source-to-body bias is applied. This increases the depletion charge in the channel region and thereby raises the threshold voltage (body effect). As a result, a larger Vgs is required to reach strong inversion.
    <br>"In the presence of Vsb, additional potential is needed for strong inversion."
    <br>Threshold Voltage Equation: V<sub>T</sub> = V<sub>T0</sub> + γ ( √(|-2φ<sub>F</sub> + V<sub>SB</sub>|) − √(|-2φ<sub>F</sub>|) )
    <br>where
    <br>V<sub>T0</sub> is the threshold voltage when Vsb=0 and is a function of manufacturing process
    <br>γ  is the body effect coefficient and it expresses the impact of changes in body bias Vsb ( γ  has the units of V^0.5)
    <br>φ<sub>F</sub> is the fermi potential
    <br>
    <br><b>Body effect coefficient expression</b>
   <br>γ = ( √(2 q ε<sub>si</sub> N<sub>A</sub>) ) / C<sub>ox</sub>
    <br>where
    <br> ε<sub>si</sub> is the relative permitivity of silicon (=11.7)
    <br>N<sub>A</sub>is the doping concentration
    <br>q is the charge of an electron
    <br>Cox is the oxide capacitance
  <li>Drain-to-Source Voltage (Vds)</li>
  <li>Characteristic plots</li>
</ul>

