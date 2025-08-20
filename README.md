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
          <li>Part 1: Introduction to Circuit Design and SPICE Simulation </li>
          -What was learnt
          <li>Part 2: NMOS Resistive region and Saturation region of operation </li>
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
    <br><b>Threshold Voltage Equation</b>b>
    <br>V<sub>T</sub> = V<sub>T0</sub> + γ ( √(|-2φ<sub>F</sub> + V<sub>SB</sub>|) − √(|-2φ<sub>F</sub>|) )
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
    <br>
    <br><b>Fermi potential equation</b>
    <br>φ<sub>F</sub> = -φ<sub>T</sub> ln( N<sub>A</sub> / n<sub>i</sub> )
    <br>where n<sub>i</sub> is the intrinsic doping parameter for the substrate.
    <br>
     <h3>Part 2: NMOS Resistive region and Saturation region of operation</h3>
     <h4>What was learnt</h4>
     The resistive region, also known as linear region of operation, occurs when the transistor operates with Vgs=Vt, and further changes can be observed when Vgs>Vt. In this region, the induced charge Qi is proportional to (Vgs-Vt). For analysis, we took 
    <br>Vgs=1V, Vds=0.05V, Vt=0.45V
    <br>When Vds=0, the voltage across the n channel remains constant but not the case when Vds is applied due to potential gradient across the channel as source is at 0V but drain at 0.05V.
    <br>Let the effective channel length be L and 'x' axis be along the channel length and 'y' axis be perpendicular to the channel length. Let V(x) be the voltage at any point 'x' along the channel. Now, Vgs-V(x) is the gate-to-channel voltage at that point.
<br>Therefore, in the channel, induced charge at any point 'x' Q<sub>i</sub>(x) ∝ − ( V<sub>GS</sub> − V(x) − V<sub>T</sub> )
<br>Formula for charge induced at any point ‘x’
<br>Q<sub>i</sub>(x) = − C<sub>ox</sub> ( V<sub>GS</sub> − V(x) − V<sub>T</sub> )
<br>Gate oxide capacitance formula C<sub>ox</sub> = &epsilon;<sub>ox</sub> / t<sub>ox</sub>
<br>where
    <br>εox is the oxide permittivity = 3.97εo = 3.510e-11 F/m
    <br>tox is the oxide thickness

<br> From device point of view, we have 2 types of current
<br>Drift Current: Current due to potential difference
<br>Diffusion Current: Current due to difference in carrier concentration
<br>Here we are only talking about the drift current (Id) that is from source to drain.
<br> Id=velocity of charge carriers* available charge over channel width

<br>
<b>Drift current (Id) formula</b>
<br>I<sub>D</sub> = μ<sub>n</sub> C<sub>ox</sub> (W/L) [ (V<sub>GS</sub> − V<sub>T</sub>) V<sub>DS</sub> − (V<sub>DS</sub><sup>2</sup> / 2) ]
<br>The term µn.Cox is denoted by kn' and kn' is known as process transconductance
<br>kn'.(W/L) is denoted by kn and kn is also known as gain factor
<br>Condition on Vds for the MOSFET to be in linear/resistive region or saturation/pinch-off region
<br>When Vds <= (Vgs-Vt), the MOSFET is in linear region of operation
<br>For this region, Id=kn.(Vgs-Vt).Vds as (Vds^2)/2 is a very small amount in this case
<br>Vdds can be sweeped from 0V to (Vgs-Vt)V to make the device work in linear region of operation
<br> Dependance of Id on Vds in pinch-off region: The chanel voltag
e is denoted with Vgs-Vds.
<br>
<b>Pinch-off condition</b> is when Vgs-Vds=Vt
<br>When the Pinch-off phenomenon is started, the channel begins to disappear. Basically, the channel starts to disappear only from the Drain side acquiring a triangular shape.
When Vgs-Vds<Vt, there is no channel present near the Drain terminal.Id becomes (kn/2).(Vgs-Vt)^2
<br>Looks like a perfect current source but in reality it is not true because the effective conductive channel length can be still changed by applying Vds.
<br>As Vds increases, more area of channel near the drain terminal will disappear resulting in decrease in effective channel length.
<br><b>New modified drain current equation</b>
    <br>I<sub>D</sub> = (K<sub>n'</sub>)/2) (W/L) [ ((V<sub>GS</sub> − V<sub>T</sub>))<sup>2</sup>[1+λV<sub>DS</sub>]
<br>Here, λ is the channel length modulation
    <br>
<h3>Part 3: Introduction to SPICE</h3>
<h4>What was learnt</h4>
<br>SPICE is a software/engine which already have predefined models which can be used to calculate waveforms and delays by inserting the input values. 
<br>SPICE model parameters also known as technological constant nodes, which come from foundaries and is listed in the model file which we provide to the engine. Example: Vt0, kn', λ, γ
<br>These are the 1st level inputs
<br>Levels of SPICE simulation- 1st level input is SPICE model parameters+Spice netlist, these are given to the SPICE Software to get required SPICE waveform.
<br>https://user-images.githubusercontent.com/89193562/132711027-1aa941dc-56bc-4be9-af32-5a96b76d9c09.jpg
<br>A node is a point that connects two terminals. When two terminals of the same device are short-circuited, the node exists between them. In most cases, however, a node connects multiple devices. Nodes can be identified in a SPICE netlist, where every wire linking different components corresponds to a unique node.
<h4>Lab Activity</h4>
    <br> The following code is used for day1 lab activity
<br>*Model Description
.param temp=27

*Including sky130 library files
.lib "sky130_fd_pr/models/sky130.lib.spice" tt

*Netlist Description

XM1 Vdd n1 0 0 sky130_fd_pr__nfet_01v8 w=0.65 l=0.25
R1 n1 in 55
Vdd vdd 0 1.8V
Vin in 0 1.8V

*simulation commands

.op
.dc Vdd 0 1.8 0.1 Vin 0 1.8 0.2

.control

run
display
setplot dc1
.endc

.end
<br>In the lab activity, tt(typical corner) corner is used.
<br>![VirtualBox_vsdworkshop_15_08_2025_18_05_15](https://github.com/user-attachments/assets/96ef8322-12f2-4932-9007-4bfa6d5f7d56)
<br>![VirtualBox_vsdworkshop_15_08_2025_18_05_35](https://github.com/user-attachments/assets/82230928-d2dc-4d60-ae12-20b42381db43)
<br>![Uploading VirtualBox_vsdworkshop_15_08_2025_18_05_46.jpg…]()






    
  <li>Drain-to-Source Voltage (Vds)</li>
  <li>Characteristic plots</li>
</ul>

