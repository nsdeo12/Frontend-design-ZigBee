Frontend-design-ZigBee
======================

low voltage differential Low Noise Amplifier Design for ZigBee standard

A Technique for Impedance Matching in
Design of Low Noise Amplifier for ZigBee
Receiver Frontend
Nilakantha Singh Deo#1, Srinibasa Padhy#2
#
KIIT University
1
nsinghdeo005@gmail.com
srinibas.iitkgp@gmail.com
2
Abstract: As the Internet of Things wave is around the
corner extending the internet to the real world
embracing everyday objects, the communication
protocols need to be revisited. Personal area networks
(PAN) will revolutionize the way we live. Lightweight
protocols like Bluetooth and ZigBee will be heavily
sought for and the hardware to support them, such as
amplifiers that will work hand in hand with these
protocols, must be redesigned. In this paper, we propose
a novel technique for impedance matching in the design
of Low Noise Amplifier (LNA) using lumped passive
components which reduces the overall chip area. In
addition, we discuss the insights gained by reducing the
mathematical overhead of the LNA design process in
approximation of parasitic capacitances. The frequency
band is 2-2.4 GHz. The noise figure is found to be less
than 3dB.
Keywords: Impedance matching, LNA, low
amplifier, ZigBee frontend, RFIC transceivers
I.
Ftot  FLNA 
Frest  1
GLNA
Where, FLNA is the noise factor of the LNA, which
dominates the overall noise. Therefore decreasing the NF
(noise figure) value of first stage of the receiver i.e. LNA
has significant effect of noise reduction on the overall
system.
In noise figure calculation, the effect of parasitic
capacitances is included which lose their significance at
high frequencies. This may be avoided by approximating the
parasitics, except Cgs which is made to tune with the
degenerate inductor.
noise
INTRODUCTION
Impedance matching in LNA design is important to preserve
the shape of a signal since it enables maximum power
transfer between consecutive blocks in the receiver frontend.
Impedance matching in LNA is achieved by inserting filter
circuits and tuning them at a particular frequency. The
additional filter circuits lead to a larger chip area and
computation overhead by conjugate matching over a
frequency range of interest [8]. In order to reduce the
amount of computation involved and the number of
components, lumped components can be added at
subsequent stages and tuning them at center frequency till
source and load impedances are matched.
The noise figure value of LNA prevails over the receiver
noise figure. According to Friss’s equation, for a cascaded
stage, the total noise factor is given by
Ftot  F1 
It can be shown that
Fn  1
F2  1 F3  1
F4  1


 ... 
G1
G1.G2 G1.G 2.G3
G1.G 2 ...G n
Where, Fi and Gi are the noise factors and power gain of
individual blocks.
Fig.1 LNA impedance matching
Section II discusses various topologies of the LNA along
with an approximation model that considers only Cgs
neglecting other parasitic capacitances. It also discusses
calculation of noise figure in detail. Section III proposes a
novel technique to match impedances at input and output
side with an aim to minimize reflection losses so that shape
of input signal is preserved. The port matching technique is
briefly shown in the figure above (all the parameters have
their usual meaning). Subsequent sections discuss the
simulation results and the response of the circuits
respectively. The work is partially motivated by the need to
describe in detail the LNA design process illustrating the
mathematical analysis.
II. LNA TOPOLOGY AND DESIGN APPROACH
LNA can be designed with resistive termination(a),1/gm
termination(b), shunt series feedback(c) and inductor
degeneration(d) [4].The first three topologies have resistor
values dominated in the noise factor calculation, which is
additive to the noise figure. But in the inductive degenerate
structure both capacitors and inductors are found .This is
preferred over the other three as the inductor can be made to
resonate with the capacitor at the required frequency and
hence both L and C effect can be got rid of. Different LNA
topologies are shown underneath.
g m Ls
1

Cgs
sCgs
Zin  sL s  s L g 
Im  0
0 2 
1
(L s  L g ) C gs
Re (Zin )  R s
g m Ls
 Rs
Cgs
( 2)
For this kind of structure the effective transconductance can
be calculated by the following method:
Gmeff 
Fig.2 LNA topologies
The first schematic (figure.8) designed with inductor
degenerate structure is prone to noise as proper biasing is
not provided .In the later (figure.11) a proper biasing current
is provided with the help of a current mirror circuit. By
making W/L ratio 1/xth, a biasing current can be obtained in
the same ratio. Again an ac blocking capacitor is provided
just before the inductor to avoid a zero voltage at the gate of
the RF mos. Consider the small signal model of an inductor
degenerate structure below. Its input impedance can be
calculated as follows [4].
I out
Vs
I out  g m .Vgs
Z cgs
Vgs  (
Rs  Z in
Gmeff 
) Vs
g Z
I out
 m cgs
Vs
Rs  Z in
1
sCgs
Z cgs 
Z in  Rs 
g m Ls
1
 sLs  sLg 
Cgs
sCgs
gm
Gmeff 
Fig.3 Small signal model of degenerate LNA structure
Vin  I in sLg  I in (
Vgs  I in .
Gmeff 
1
)  (Iin  g m Vgs ) sL s
sCgs
1
Cgs
Vin  I in sLg  I in (
gm
1  s 2Cgs (L s  L g )  s(R s C gs  g m L s )
N device  G.N source
G.N source
NF 
1
Vin  I in [ s ( Lg  Ls )  (sg m L s  1).
sCgs
g m Ls
1

]
Cgs
sCgs
g m Ls
1
 sLs  sLg 
Cgs
sCgs
Noise figure calculations for a simple nmos device is given
by
1
1
)  (Iin  g m I in .
) sL s
sCgs
sCgs
Vin  I in [sL s  sL g 
Rs 
1
Cgs
(1)
 1
N device
G.N source
(3)
As the G (power gain of the device) is calculated by
Now the term in the square bracket is equal to the input G
impendence and for matching it should be equal to source 
resistance [5], Rs. 
Redrawing the small signal model for the above circuit we 1
have: jCgs
       
        1
       Rs 
        jCgs
i0 .i0*
 Gmeff
Vs .Vs*
g m Z in
Rs  Z in
2

gm2
1  Rs jCgs
2
gm2
g 2
 1
 2 m
 ( T . )2
2
1   (R s C gs )
 (R s C gs ) 2
 Rs
2
; where
Fig.4 small signal model for matching with Rs

2
gm .

2
T g m

 Cgs
(4)
So final value for G = (
T 1 2
. )
 Rs
method,
.Now for this device
Qin 
calculating noise factor by equation-3 we may get
N device  4kT  g m
 Qin 
N source  4kTRs
NF  1 
NF  1 
4kT  g m
gm2
4kTRs
1   2 (R s C gs ) 2
Rs g m
  Rs g m (
NF
 2
)
T
(5)
Now noise figure of a degenerated LNA can be
calculated in the same manner. Primarily the effective gm is
calculated and from that NF is calculated by the same
equation 3 [6].
G  Gmeff
1
Cgs (R s  g m L s / C gs )
1
2 Rs Cgs
(8)
For noise figure to be minimum at a particular frequency we
have to make
Rs g m


; As gm (Ls/Cgs) should be equal to Rs for maximum power
transfer.
 (1   2 R s 2 .C gs 2 )
NF  1 
1
C R eq
( 0 )
 1

 2 (R s C gs  g m L s ) 2
Rs g m
Here gm Ls/Cgs should be zero making the NF value more
acceptable, or we can take another result already included as
below.
NF
( 0 )
2
 NF  1 
2
 1

Rs g m

Rs g m
 2 (R s C gs  g m L s ) 2
(4 g m L s ) 2 .
 gm As g m Ls  Rs C gs and  2 
    1  s (R s C gs  g m L s )  s 2 Cgs (L s  L g ) 
 gm2  1
     (R s C gs  g m L s )  [1   2 C gs (L s  L g )]2 
2
2
Imaginary term   2 (R s C gs  g m L s ) 2
Real term  [1   C gs (L s  L g )]
2
2
 NF  1 
(6)
Noise figure can be calculated by taking the real term to
zero so that the Ls and Cgs will cancel each other’s effect at
a frequency ω.
NF  1 
 1
N device
GN source
4kT  g m
gm2
4kTRs 2
 (R s C gs  g m L s ) 2
NF  1 
 2
Rs g m
(R s C gs  g m L s ) 2
(7)
Calculating for quality factor we can have
Q

4 g m Ls 2
1
.
Rs Cgs (L g  L s )
stored power
lost power
I .I * / C
1

*
I .I R
 RC
1
Cgs (L g  L s )
1
... by (6)
Cgs (L s  L g )
; L s  Rs Cgs / g m
4 Ls
Lg  Ls
(9)
With the above results (equ8, equ9) the values of the
capacitance Cgs, inductors Lg [7]and Ls can be easily
calculated as the NF and Q values have been already taken
care of .Calculation of width for the nmos can be easily
3
Cgs
done once Cgs value is found as W  2
Cox L
Usually low noise amplifier is the next stage to antenna and
proceeded by the mixer unit. So it should be matched
properly. Equation (7) shows the noise figure value and it
can be arranged properly as an equation of circles. So
changing values of ω and Rs and Cgs we can have concentric
circles. In a way it may be noted that with smith chart
proper values of L and C can be chosen that would match
impedances of the LNA unit with that of the antenna and
mixer facilitating maximum power transfer.
III. IMPEDANCE MATCHING OF THE LNA
At input side it is required to facilitate maximum power
transfer from the antenna to the LNA block. Similarly the
output side requires the input to be matched in order to
transfer maximum power from the LNA block to the mixer
unit. Now considering the figure below,
For the inductive degenerative structure we can calculate the
same by taking the equivalent resistance by the following
Fig.5 adding lumped elements for matching
Two capacitors C1 and C2 are added at nodes A and B
respectively. Looking to the right of point X, we may
redraw the whole circuit as below which can be converted
from a parallel RC to series RC tuned circuit using the
following formulae (10).
a family of circles [9], using Smith Chart the addition of
inductors and capacitors at source or load side can be easily
found out. In this paper the NF is not an equation of family
of circles, yet with Smith chart the s11 can be drawn but
matching might not provide accurate results. Figure 9 shows
the s11 curve on Zsmith. The s11 curve approaches
approximately to (1+j0) curve. Hence it may be presumed to
be a good match at the source side.
IV. SIMULATIONS AND RESULTS
Fig.6 Parallel RC to series RC conversion
The intension behind this is that, the effect of inductor can
be cancelled by adding a capacitor and make it resonate at a
particular frequency ω0.
1  Q2 

Q2 

g m Ls / Cgs

R' 

2
1 Q

0 (g m L s / C gs ) 
Q

C1  Cgs


C2 '  (C1  Cgs )
(10)
Above equation are used for parallel RC to series RC
conversion.
At the resonating frequency ω0 the impedance becomes
infinite and Ls and =C1+Cgs has least significance. The
circuit impedance is due to the resistive element gmLs/Cgs.
The circuit components with significant input impedance
contribution is shown in figure below at left which can be
converted to a parallel RLC circuit as shown at the right
side
of
the
figure
below.
Two ports at input and output side should be set with 50
ohm resistances. While simulating with virtuoso, ports can
be inserted before matching and appropriate simulation
profile [10] must be set in order to get good result. The
frequency in the simulation is given as 2-4GHz to find a
proper minimum noise figure. All the schematics and
simulations are performed using cadence virtuoso ADEGXL
and spectre tools .gpdk180 with nmosrf library is used. The
results would be more accurate with tsmc18rf library. For
ZigBee receiver frontend around 20dB noise figure margin
is acceptable for LNA and mixer unit and a less than 5dB
NF is acceptable for LNA only. The simulation value gives
a noise figure of 2.5dB at 3GHz and around 10dB at
2.4GHz. The NFmin value thus is at 3GHz. The calculated
NF is 0.59198dB as compared to the simulated value of
2.5dB.Similarly the RF nmos has a width of 128um/180nm
is calculated as compared to 130um/180nm simulated value.
Without biasing the s11 values are found to be -25dB and
s22 as -100dB.whereas with a proper biasing the reflection
coefficients are somewhat compromised, nevertheless are
good results.
TABLE 1: COMPARISON OF VARIOUS LNA DESIGNS
specification
NF
(dB)
S11
(dB)
Frequency
( GHz)
Gain
( dB)
supply
voltage
( volt)
2.5 -25 3 15 1.8
This paper 10 -98 2.4 7 1.8
[5] 7.2 -37.1 2.4 22.3 0.5
[2] 7.5 * 2.445 * 1.8
[7] 4.6 * 2.4 * 0.6
[4] 3.5 * 1.46 22 1.5
(*values not provided)
Fig. 7 series RL to parallel RL conversion
The equation governing conversion of a series RL to parallel
RL ciruit can be written as follows(11).

R ''  R ' / (1  Q12 ) 

Ls (1  Q12 ) 
L' 

Q12


0 Ls
Q1 

R'

This paper 
VI. SCHEMATICS AND RESPONSES
(11)
Similarly the output side can be matched with proper
component addition and making them resonate at ω0 .In
cases where noise figure NF value is expressed in terms of
reflection coefficients at source side (ГS) and reflection
coefficients at load side ( ГL) the matching becomes easier.
If the NF becomes a function of ГS and ГL and found to be
Figure.8Schematic of the proposed LNA showing noise currents In1
and In2 of the transistors
Fig.9 s11-parameter responses on Zsmith
Fig.12 NF (min noise figure 2.5 db at 3GHz)
Fig.10 (final schematic with input and output matching network)
Fig.13 s11 (-25 dB at 2.4 GHz)
Fig.11 The final synthesized circuit with proper biasing
Fig.14 s11 (-44dB at 2.4GHz after proper biasing)
V. FUTURE WORK
Here linearity issues have not been dealt with. Common
source, single ended LNAs with proper biasing are linear
with IIP3 values better than -5dBm. It should be noted that
in mixer unit design IIP3 analysis along with NF is
important to improve performance of the transceivers.
During mixer design IIP3 analysis must be performed for
better signal integration.
VI. CONCLUSION
ZigBee devices are designed to have low data rate but
longer battery life with secure networking. This paper shows
a low noise figure (2.5dB) and low reflection coefficient
(s11=-25dB) and hence can act as a reliable receiver. The
recent case of MH370/MAS370 shows the black box goes
dead after 30 days of accident, increasing a risk of locating
.As the data rate in ZigBee device is designed to be low it
can remain active for a longer period of time (for
months)and can be used in black boxes of airplanes.
ACKNOWLEDGEMENT
The authors would like to thank Mr. Anand Rath, Associate
Scientist, ABB Corporate Research Center, India and
Mr.Sivlal, Research Scholar, VLSI Design Lab, KIIT
School of Electronics, for their valuable suggestion.
REFERENCES
[1] A. C. L. John Notor, “CMOS RFIC architecture for IEEE
     802.15.4 networks,” cadence design systems Inc., 6210 Old
      Dobbin Lane,suite 100 Columbia,Maryland 21045 USA,
     2003.
[2] A. V. V. P. R. Rafaella Fiorelli, “2.4 GHz single-ended input
     low power low voltage active front end for zigbee application
    in 90 nm CMOS,” in European conference on circuit theory
     and design(ECCTD), 2011.
[3] A. A. abidi, “low-power RFIC in wireless Transceivers,” in
IEEE symphosium on low power electronics, 1994.
[4] T. L. Derek K shaeffer, The design and implementation of low
power CMOS radio receivers, New York : Kluwer academic
publisher, 2002.
[5] W.-K. C. e. al, “Design of ultra-low voltage integrated CMOS
based LNA and mixer for ZigBee application,” International
journal of Electronics and communication Elsevier(AEU),
2013.
[6] P. A. M. Niknejad, lecture notes of MOSFET LNA design,
University of California, Berkeley, 2005.
[7] T. ,. J. Taris and Y. Deval, “A 60μW LNA for 2.4 GHz
wireless sensors network applications,” in Radio Frequency
Integrated Circuits Symposium (RFIC), 2011 IEEE ,
Baltimore, MD , 2011.
[8] S. S. C. Hyung-Jin Lee and Dong Sam Ha, “A Systematic
Approach to CMOS Low Noise,” in Circuits and Systems,
2005. ISCAS 2005. IEEE International Symposium on , 2005.
[9] G. Gonzalez, Microwave Transistor Amplifiers Analysis and
Design, New Jersey: Prentice Hall Inc. Englewood cliff ,
1984.
[10] T.-C. Yan, “Spectre RF- LNA linearity analysis,” september
2004. [Online]. Available: http://ebookbrowsee.net/lna-
design-using-spectrerf-pdf-d306994983. [Accessed February
2014].
[11] F. S.Arshad, “Wideband and multiband CMOS LNAs:state of
the art and future prospects,” Elsevier microelectronics
journal, vol. article in press, pp. 1-13, 2013.
