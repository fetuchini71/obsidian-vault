# Extracción: Atkins - Physical Chemistry 11ed
**Páginas:** 335-360
**Fuente:** Quimica\Atkins_Physical_Chemistry_11ed.pdf
---


## Página 335

FOCUS 8
Atomic structure and spectra
This Focus discusses the use of quantum mechanics to de­
scribe and investigate the ‘electronic structure’ of atoms, the 
arrangement of electrons around their nuclei. The concepts 
are of central importance for understanding the properties of 
atoms and molecules, and hence have extensive chemical ap­
plications.
8A  Hydrogenic atoms
This Topic uses the principles of quantum mechanics intro­
duced in Focus 7 to describe the electronic structure of a ‘hy­
drogenic atom’, a one-electron atom or ion of general atomic 
number Z. Hydrogenic atoms are important because their 
Schrödinger equations can be solved exactly and they provide 
a set of concepts that are used to describe the structures of 
many-electron atoms and molecules. Solving the Schrödinger 
equation for an electron in an atom involves the separation of 
the wavefunction into angular and radial parts and the result­
ing wavefunctions are the hugely important ‘atomic orbitals’ 
of hydrogenic atoms.
8A.1  The structure of hydrogenic atoms; 8A.2  Atomic orbitals and 
their energies
8B  Many-electron atoms
A ‘many-electron atom’ is an atom or ion with more than one 
electron. Examples include all neutral atoms other than H; so 
even He, with only two electrons, is a many-electron atom. 
This Topic uses hydrogenic atomic orbitals to describe the 
structures of many-electron atoms. Then, in conjunction with 
the concept of ‘spin’ and the ‘Pauli exclusion principle’, it de­
scribes the origin of the periodicity of atomic properties and 
the structure of the periodic table.
8B.1  The orbital approximation; 8B.2  The Pauli exclusion principle; 
8B.3  The building-up principle; 8B.4  Self-consistent field orbitals
8C  Atomic spectra
The spectra of many-electron atoms are more compli­
cated than that of hydrogen. Similar principles apply, but 
Coulombic and magnetic interactions between the electrons 
give rise to a variety of energy differences, which are summa­
rized by constructing ‘term symbols’. These symbols act as la­
bels that display the total orbital and spin angular momentum 
of a many-electron atom and are used to express the selection 
rules that govern their spectroscopic transitions.
8C.1  The spectra of hydrogenic atoms; 8C.2  The spectra of many-
electron atoms
Web resource  What is an application 
of this material?
Impact 13 focuses on the use of atomic spectroscopy to exam­
ine stars. By analysing their spectra it is possible to determine 
the composition of their outer layers and the surrounding 
gases and to determine features of their physical state.


## Página 336

TOPIC 8A  Hydrogenic atoms
➤  Why do you need to know this material?
An understanding of the structure of hydrogenic atoms 
is central to the description of all other atoms, the peri­
odic table, and bonding. All accounts of the structures 
of molecules are based on the language and concepts 
introduced here.
➤  What is the key idea?
Atomic orbitals are one-electron wavefunctions for atoms 
and are labelled by three quantum numbers that specify 
the energy and angular momentum of the electron.
➤  What do you need to know already?
You need to be aware of the concept of a wavefunction 
(Topic 7B) and its interpretation. You also need to know 
how to set up a Schrödinger equation and how boundary 
conditions result in only certain solutions being accept­
able (Topic 7D).
The Swedish spectroscopist Johannes Rydberg noted (in 
1890) that the wavenumbers of all the lines are given by the 
expression
R
n
n
1
1
H
1
2
2
2


ν =
−




Spectral lines of a hydrogen atom  
(8A.1)
with n1 = 1 (the Lyman series), 2 (the Balmer series), and 3 (the 
Paschen series), and that in each case n2 = n1 + 1, n1 + 2, …. 
The constant RH is now called the Rydberg constant for the 
hydrogen atom and is found empirically to have the value 
109 677 cm−1.
8A.1  The structure of hydrogenic 
atoms
Consider a hydrogenic atom, an atom or ion of arbitrary 
atomic number Z but having a single electron. Hydrogen it­
self is an example (with Z = 1). The Coulomb potential energy 
of an electron in a hydrogenic atom of atomic number Z and 
therefore nuclear charge Ze is
ε
=−π
V r
Ze
r
( )
4
2
0

(8A.2)
where r is the distance of the electron from the nucleus and 
ε0 is the vacuum permittivity. The hamiltonian for the entire 
atom, which consists of an electron and a nucleus of mass mN, 
is therefore
H
E
E
V r
ˆ
ˆ
ˆ
ˆ( )
k,electron
k,nucleus
=
+
+
ℏ
ℏ
ε
= −
∇−
∇−π
m
m
Ze
r
2
2
4
2
e
e
2
2
N
N
2
2
0 
Hamiltonian for a 
hydrogenic atom
 
(8A.3)
The subscripts e and N on ∇ 2 indicate differentiation with re­
spect to the electron or nuclear coordinates.
(a)  The separation of variables
Physical intuition suggests that the full Schrödinger equation 
ought to separate into two equations, one for the motion of 
the atom as a whole through space and the other for the mo­
tion of the electron relative to the nucleus. The Schrödinger 
When an electric discharge is passed through gaseous hydrogen, 
the H2 molecules are dissociated and the energetically excited 
H atoms that are produced emit electromagnetic radiation at a 
number of discrete frequencies (and therefore discrete wave­
numbers), producing a spectrum of a series of ‘lines’ (Fig. 8A.1). 
2000
1000
800
600
500
400
200
150
120
100
Analysis
300
Wavelength,   /nm
λ
Visible
Balmer Lyman
Paschen
Brackett
Figure 8A.1  The spectrum of atomic hydrogen. Both the observed 
spectrum and its resolution into overlapping series are shown. 
Note that the Balmer series lies in the visible region.


## Página 337

8A  Hydrogenic atoms  305
equation for the internal motion of the electron relative to the 
nucleus is1
ℏ
µ
ψ
ε
ψ
ψ
µ
−
∇
−π
=
=
+
Ze
r
E
m
m
2
4
1
1
1
2
2
2
0
e
N

Schrödinger 
equation for a 
hydrogenic atom
 
(8A.4)
where differentiation is now with respect to the coordinates of 
the electron relative to the nucleus. The quantity μ is called the 
reduced mass. The reduced mass is very similar to the electron 
mass because mN, the mass of the nucleus, is much larger than 
the mass of an electron, so 1/µ ≈ 1/me and therefore µ ≈ me. 
In all except the most precise work, the reduced mass can be 
replaced by me.
Because the potential energy is centrosymmetric (independ­
ent of angle), the equation for the wavefunction is expected to 
be separable into radial and angular components, as in
r
R r Y
( , , )= ( ) ( , )
ψ
θ φ
θ φ 
(8A.5)
with R(r) the radial wavefunction and Y(θ,ϕ) the angular 
wavefunction. The equation does separate, and the two con­
tributions to the wavefunction are solutions of two equations:
Y
l l
Y
(
1)
2
Λ
=−
+

(8A.6a)
ℏ
R
r
r
R
r
V R
ER
2
d
d
2 d
d
2
2
2
eff
µ
−
+



+
=

(8A.6b)
where
ℏ
ε
µ
=−π
+
+
V
r
Ze
r
l l
r
( )
4
(
1)
2
eff
2
0
2
2

(8A.6c)
Equation 8A.6a is the same as the Schrödinger equation for 
a particle free to move at constant radius around a central 
point, and is considered in Topic 7F. The allowed solutions 
are the spherical harmonics (Table 7F.1), and are specified by 
the quantum numbers l and ml. Equation 8A.6b is called the 
radial wave equation. The radial wave equation describes the 
motion of a particle of mass μ in a one-dimensional region 0 ≤ 
r < ∞ where the potential energy is Veff(r).
(b)  The radial solutions
Some features of the shapes of the radial wavefunctions can 
be anticipated by examining the form of Veff(r). The first term 
in eqn 8A.6c is the Coulomb potential energy of the electron 
in the field of the nucleus. The second term stems from what 
in classical physics would be called the centrifugal force aris­
ing from the angular momentum of the electron around the 
nucleus. When l = 0, the electron has no angular momen­
tum, and the effective potential energy is purely Coulombic 
and the force exerted on the electron is attractive at all radii 
(Fig. 8A.2). When l ≠ 0, the centrifugal term gives a positive 
contribution to the effective potential energy, corresponding 
to a repulsive force at all radii. When the electron is close to 
the nucleus (r ≈ 0), the latter contribution to the potential en­
ergy, which is proportional to 1/r2, dominates the Coulombic 
contribution, which is proportional to 1/r, and the net result 
is an effective repulsion of the electron from the nucleus. The 
two effective potential energies, the one for l = 0 and the one for 
l ≠ 0, are therefore qualitatively very different close to the nu­
cleus. However, they are similar at large distances because the 
centrifugal contribution tends to zero more rapidly (as 1/r2) 
than the Coulombic contribution (as 1/r). Therefore, the solutions 
with l = 0 and l ≠ 0 are expected to be quite different near the 
nucleus but similar far away from it. 
Two features of the radial wavefunction are important:
• Close to the nucleus the radial wavefunction is 
proportional to r l, and the higher the orbital angu­
lar momentum, the less likely it is that the electron 
will be found there (Fig. 8A.3).
• Far from the nucleus all radial wavefunctions 
approach zero exponentially.
The detailed solution of the radial equation for the full range 
of radii shows how the form r l close to the nucleus blends 
1 See the first section of A deeper look 3 on the website for this text for full 
details of this separation procedure and then the second section for the cal­
culations that lead to eqn 8A.6.
l = 0
l ≠ 0
Radius, r
Effective potential energy, Veff
0
Figure 8A.2  The effective potential energy of an electron in 
the hydrogen atom. When the electron has zero orbital angular 
momentum, the effective potential energy is the Coulombic 
potential energy. When the electron has non-zero orbital 
angular momentum, the centrifugal effect gives rise to a positive 
contribution which is very large close to the nucleus. The l = 0 
and l ≠ 0 wavefunctions are therefore very different near the 
nucleus.
Physical interpretation


## Página 338

306 
8  Atomic structure and spectra
into the exponentially decaying form at great distances. It 
turns out that the two regions are bridged by a polynomial in 
r and that











=
×
×
R r
r
r
r
( )
(polynomial in ) (decaying exponential in )
l

(8A.7)
The radial wavefunction therefore has the form
=
−
R r
r L r
( )
( )e
l
r
with various constants and where L(r) is the bridging polyno­
mial. Close to the nucleus (r ≈ 0) the polynomial is a constant 
and e−r ≈ 1, so R(r) ∝ r l; far from the nucleus the dominant 
term in the polynomial is proportional to rn−l−1, where n is an 
integer, so regardless of the value of l, all the wavefunctions 
of a given value of n are proportional to rn−1e−r and decay 
exponentially to zero in the same way (exponential functions 
e−x always dominate simple powers, xn).
The detailed solution also shows that, for the wavefunction to 
be acceptable, the value of n that appears in the polynomial can 
take only positive integral values, and specifically n = 1, 2, …. 
This number also determines the allowed energies through the 
expression:
ℏ
E
e
Z
n
32π
n
4
2
0
2
2
2
2
µ
ε
=−
×

Bound-state energies  
(8A.8)
Dominant far 
from the nucleus
Bridges the two 
ends of the function
Dominant 
close to  the 
nucleus
Radius, r
Wavefunction, ψ
l = 0
1
2
3
Figure 8A.3  Close to the nucleus, orbitals with l = 1 are 
proportional to r, orbitals with l = 2 are proportional to r 2, 
and orbitals with l = 3 are proportional to r 3. Electrons are 
progressively excluded from the neighbourhood of the nucleus 
as l increases. An orbital with l = 0 has a finite, non-zero value at 
the nucleus.
So far, only the general form of the radial wavefunctions has 
been given. It is now time to show how they depend on various 
fundamental constants and the atomic number of the atom. 
They are most simply written in terms of the dimensionless 
quantity ρ (rho), where
ℏ
ρ
µ
ε
=
=
= π
Zr
na
a
m a
a
m e
2
4
e
0
0
0
2
e
2

(8A.9)
The Bohr radius, a0, has the value 52.9 pm; it is so called 
because the same quantity appeared in Bohr’s early model 
of the hydrogen atom as the radius of the electron orbit of 
lowest energy. In practice, because me << mN (so me/μ ≈ 1) 
there is so little difference between a and a0 that it is safe 
to use a0 in the definition of ρ for all atoms (even for 1H, a 
= 1.0005a0). In terms of these quantities and with the vari­
ous quantum numbers displayed, the radial wavefunctions 
for an electron with quantum numbers n and l are the (real) 
functions
R
r
N
L
( )
( )e
n l
n l
l
n l
,
,
,
/2
ρ
ρ
=
ρ
−

Radial wavefunctions  
(8A.10)
where Ln,l(ρ) is an associated Laguerre polynomial. These 
polynomials have quite simple forms, such as 1, ρ, and 2 − ρ 
(they can be picked out in Table 8A.1). The factor Nn,l ensures 
that the radial wavefunction is normalized to 1 in the sense 
that
R
r r
r
( )
d
1
n l,
2
2
0∫
=
∞

(8A.11)
Table 8A.1  Hydrogenic radial wavefunctions
n
l
Rn,l(r)
1
0
Z
a
2
e
3/2
/2




ρ
−
2
0
Z
a
1
8
(2
)e
1/2
3/2
/2
ρ




−
ρ
−
2
1
Z
a
1
24
e
1/2
3/2
/2
ρ




ρ
−
3
0
Z
a
1
243
(6 6
)e
 
1/2
3/2
2
/2
ρ
ρ




−
+
ρ
−
3
1
Z
a
1
486
(4
) e
1/2
3/2
/2
ρ ρ




−
ρ
−
3
2
Z
a
1
2430
e
1/2
3/2
2
/2
ρ




ρ
−
ρ = (2Z/na)r with a = 4πε0ħ2/μe2. For an infinitely heavy nucleus (or one that may be 
assumed to be), μ = me and a = a0, the Bohr radius.


## Página 339

8A  Hydrogenic atoms  307
Brief illustration 8A.1
To calculate the probability density at the nucleus for an elec­
tron with n = 1, l = 0, and ml = 0, evaluate ψ at r = 0:
R
Y
Z
a
(0, , )
(0)
( , ) 2
1
4π
1,0,0
1,0
0,0
0
3/2
1/2
ψ
θ φ
θ φ
=
= 







The probability density is therefore
Z
a
(0, , )
2
1,0,0
3
0
3
ψ
θ φ = π
which evaluates to 2.15 × 10−6 pm−3 when Z = 1.
Physical interpretation
n = 1, l = 0
Zr/a0
R(r)/(Z/a0)3/2
0 0
1
2
3
2
1.5
1
0.5
n = 2, l = 0
Zr/a0
R(r)/(Z/a0)3/2
0
0
10
15
5
0.4
0.2
0.8
0.6
–0.2
n = 3, l = 0
Zr/a0
R(r)/(Z/a0)3/2
0
0
7.5
15
22.5
0.4
0.3
0.2
0.1
–0.1
n = 2, l = 1
Zr/a0
R(r)/(Z/a0)3/2
0
0
10
15
5
0.15
0.1
0.05
n = 3, l = 1
Zr/a0
R(r)/(Z/a0)3/2
0
0
7.5
15
22.5
0.05
–0.05
0.1
n = 3, l = 2
Zr/a0
R(r)/(Z/a0)3/2
0
0
7.5
15
22.5
0.05
0.04
0.03
0.02
0.01
Figure 8A.4  The radial wavefunctions of the first few states of hydrogenic atoms of atomic number Z. Note that the orbitals with l = 0 
have a non-zero and finite value at the nucleus. The horizontal scales are different in each case: as the principal quantum number increases, 
so too does the size of the orbital.
(The r2 comes from the volume element in spherical coordi­
nates; see The chemist’s toolkit 21 in Topic 7F.) Specifically, the 
components of eqn 8A.10 can be interpreted as follows:
• The exponential factor ensures that the wavefunc­
tion approaches zero far from the nucleus.
• The factor ρl ensures that (provided l > 0) the wave­
function vanishes at the nucleus. The zero at r = 0 is 
not a radial node because the radial wavefunction 
does not pass through zero at that point (because r 
cannot be negative).
• The associated Laguerre polynomial is a function 
that in general oscillates from positive to negative 
values and accounts for the presence of radial 
nodes.
Expressions for some radial wavefunctions are given in Table 
8A.1 and illustrated in Fig. 8A.4. Finally, with the form of 
the radial wavefunction established, the total wavefunction, 
eqn 8A.5, in full dress becomes
ψ
θ φ
θ φ
=
r
R
r Y
( , , )
( )
( , )
n l m
n l
l m
, ,
,
,
l
l

(8A.12)


## Página 340

308 
8  Atomic structure and spectra
8A.2  Atomic orbitals and their 
energies
An atomic orbital is a one-electron wavefunction for an elec­
tron in an atom, and for hydrogenic atoms has the form speci­
fied in eqn 8A.12. Each hydrogenic atomic orbital is defined by 
three quantum numbers, designated n, l, and ml. An electron 
described by one of the wavefunctions in eqn 8A.12 is said to 
‘occupy’ that orbital. For example, an electron described by 
the wavefunction ψ1,0,0 is said to ‘occupy’ the orbital with n = 1, 
l = 0, and ml = 0.
(a)  The specification of orbitals
Each of the three quantum numbers specifies a different at­
tribute of the orbital:
• The principal quantum number, n, specifies the energy 
of the orbital (through eqn 8A.8); it takes the values n = 
1, 2, 3, ….
• The orbital angular momentum quantum number, l, 
specifies the magnitude of the angular momentum of the 
electron as {l(l + 1)}1/2ћ, with l = 0, 1, 2, …, n − 1.
• The magnetic quantum number, ml, specifies the z-com­
ponent of the angular momentum as mlћ, with ml = 0, ±1, 
±2, …, ±l.
Note how the value of the principal quantum number controls 
the maximum value of l, and how the value of l controls the 
range of values of ml.
(b)  The energy levels
The energy levels predicted by eqn 8A.8 are depicted in Fig. 
8A.5. The energies, and also the separation of neighbouring 
levels, are proportional to Z2, so the levels are four times as 
wide apart (and the ground state four times lower in energy) 
in He+ (Z = 2) than in H (Z = 1). All the energies given by eqn 
8A.8 are negative. They refer to the bound states of the atom, 
in which the energy of the atom is lower than that of the infi­
nitely separated, stationary electron and nucleus (which cor­
responds to the zero of energy). There are also solutions of the 
Schrödinger equation with positive energies. These solutions 
correspond to unbound states of the electron, the states to 
which an electron is raised when it is ejected from the atom 
by a high-energy collision or photon. The energies of the un­
bound electron are not quantized and form the continuum 
states of the atom.
Equation 8A.8, which can be written as


E
hcZ R
n
R
e
ch
      
8
n
2
N
2
N
4
0
2
3
µ
ε
=−
=

Bound-state energies  
(8A.13)
is consistent with the spectroscopic result summarized by eqn 
8A.1, with the Rydberg constant for the atom identified as



R
m
R
R
m e
h c
           
8
N
e
e
4
0
2
3
µ
ε
=
×
=
∞
∞

Rydberg constant  
(8A.14)
where µ is the reduced mass of the atom and R∞ is the Rydberg 
constant; the constant RN is the value that constant takes for a 
specified atom N (not nitrogen!), such as hydrogen, when N is 
replaced by H and µ takes the appropriate value. Insertion of 
the values of the fundamental constants into the expression 
for RH gives almost exact agreement with the experimental 
value for hydrogen. The only discrepancies arise from the ne­
glect of relativistic corrections (in simple terms, the increase 
of mass with speed), which the non-relativistic Schrödinger 
equation ignores.
Brief illustration 8A.2
The value of R∞ is given inside the front cover and is 
109 737 cm−1. The reduced mass of a hydrogen atom with mp = 
1.672 62 × 10−27 kg and me = 9.109 38 × 10−31 kg is
µ =
+
=
×
×
×
×
+
×
=
×
−
−
−
−
−
m m
m
m
(9.10938 10
kg) (1.67262 10
kg)
(9.10938 10
kg) (1.67262 10
kg)
9.10442 10
kg
e
p
e
p
31
27
31
27
31
It then follows that
=
×
×
×
=
−
−
−
−
R
9.10442 10
kg
9.10938 10
kg 109737cm
109677cm
H
31
31
1
1

and that the ground state of the electron (n = 1) lies at
E
hcR
(6.62608 10
Js) (2.997945 10 cm s )
(109677cm )
2.17870 10
J 
1
H
34
10
1
1
18

=−
=−
×
×
×
×
=−
×
−
−
−
−
or 2.178 70 aJ. This energy corresponds to −13.598 eV.
Energy, E
0
1
2
3
∞
n
Continuum
Classically
allowed
energies
H+ + e–
–hcRH
–hcRH/4
–hcRH/9
~
~
~
Figure 8A.5  The energy levels of a hydrogen atom. The values 
are relative to an infinitely separated, stationary electron and a 
proton.


## Página 341

8A  Hydrogenic atoms  309
(c)  Ionization energies
The ionization energy, I, of an element is the minimum en­
ergy required to remove an electron from the ground state, 
the state of lowest energy, of one of its atoms in the gas phase. 
Because the ground state of hydrogen is the state with n = 1, 
with energy E1 = −hc RH and the atom is ionized when the elec­
tron has been excited to the level corresponding to n = ∞ (see 
Fig. 8A.5), the energy that must be supplied is

I
hcRH
=

(8A.15)
The value of I is 2.179 aJ (1 aJ = 10−18 J), which corresponds to 
13.60 eV.
A note on good practice  Ionization energies are sometimes 
referred to as ionization potentials. That is incorrect, but not 
uncommon. If the term is used at all, it should denote the elec­
trical potential difference through which an electron must be 
moved for the change in its potential energy to be equal to the 
ionization energy, and reported in volts: the ionization energy of 
hydrogen is 13.60 eV; its ionization potential is 13.60 V.
Example 8A.1  Measuring an ionization energy 
spectroscopically
The emission spectrum of atomic hydrogen shows lines at 
82 259, 97 492, 102 824, 105 292, 106 632, and 107 440 cm−1, 
which correspond to transitions to the same lower state from 
successive upper states with n = 2, 3, …. Determine the ioniza­
tion energy of the lower state.
Collect your thoughts  The spectroscopic determination of 
ionization energies depends on the identification of the ‘series 
limit’, the wavenumber at which the series terminates and 
becomes a continuum. If the upper state lies at an energy 
−hc RH/n2, then the wavenumber of the photon emitted when 
the atom makes a transition to the lower state, with energy 
Elower, is
R
n
E
hc
R
n
I
hc
H
2
lower
H
2
ν = −
−
= −
+



A plot of the wavenumbers against 1/n2 should give a straight 
line of slope −RH
  and intercept I/hc. Use software to calculate 
a least-squares fit of the data in order to obtain a result that 
reﬂects the precision of the data.
The solution  The wavenumbers are plotted against 1/n2 in 
Fig. 8A.6. From the (least-squares) intercept, it follows that 
I/hc = 109 679 cm−1, so the ionization energy is
I
hc (109679cm )
1
=
×
−
(6.62608 10
Js) (2.997 945 10 cms ) (109679cm )
34
10
1
1
=
×
×
×
×
−
−
−
2.1787 10
J
18
=
×
−
I = −Elower
or 2.1787 aJ, corresponding to 1312.1 kJ mol−1 (the negative of 
the value of E calculated in Brief illustration 8A.2).
Self-test 8A.1  The emission spectrum of atomic deuterium 
shows lines at 15 238, 20 571, 23 039, and 24 380 cm−1, which 
correspond to transitions from successive upper states with 
n = 3, 4, … to the same lower state. Determine (a) the ioniza­
tion energy of the lower state, (b) the ionization energy of the 
ground state, (c) the mass of the deuteron (by expressing the 
Rydberg constant in terms of the reduced mass of the electron 
and the deuteron, and solving for the mass of the deuteron).
Answer: (a) 328.1 kJ mol−1, (b) 1312.4 kJ mol−1,
(c) 2.8 × 10−27 kg, a result very sensitive to RD
(d)  Shells and subshells
All the orbitals of a given value of n are said to form a single 
shell of the atom. In a hydrogenic atom (and only in a hydro­
genic atom), all orbitals of given n, and therefore belonging to 
the same shell, have the same energy. It is common to refer to 
successive shells by letters:
n =  1    2  3     4 …
Specification of shells
      K  L  M  N …
Thus, all the orbitals of the shell with n = 2 form the L shell of 
the atom, and so on.
The orbitals with the same value of n but different values of l 
are said to form a subshell of a given shell. These subshells are 
also generally referred to by letters:
l =  0  1  2  3  4  5  6 …    Specification of subshells
    s   p  d  f  g  h  i …
All orbitals of the same subshell have the same energy in all 
kinds of atoms, not only hydrogenic atoms. After l = 3 the 
letters run alphabetically (j is not used because in some lan­
0
0.1
0.2
1/n2
80
90
100
110
ν/(103 cm–1)
~
Figure 8A.6  The plot of the data in Example 8A.1 used to 
determine the ionization energy of an atom (in this case, of H). 


## Página 342

310 
8  Atomic structure and spectra
guages i and j are not distinguished). Figure 8A.7 is a version 
of Fig. 8A.5 which shows the subshells explicitly. Because l can 
range from 0 to n − 1, giving n values in all, it follows that there 
are n subshells of a shell with principal quantum number n. 
The organization of orbitals in the shells is summarized in Fig. 
8A.8. The number of orbitals in a shell of principal quantum 
number n is n2, so in a hydrogenic atom each energy level is 
n2-fold degenerate.
Brief illustration 8A.3
When n = 1 there is only one subshell, that with l = 0, and that 
subshell contains only one orbital, with ml = 0 (the only value 
of ml permitted). When n = 2, there are four orbitals, one in 
the s subshell with l = 0 and ml = 0, and three in the l = 1 sub­
shell with ml = +1, 0, −1. When n = 3 there are nine orbitals 
(one with l = 0, three with l = 1, and five with l = 2).
(e)  s Orbitals
The orbital occupied in the ground state is the one with n = 1 
(and therefore with l = 0 and ml = 0, the only possible values 
of these quantum numbers when n = 1). From Table 8A.1 and 
with Y0,0 = 
π
(1/4 )1/2 (Table 7F.1) it follows that (for Z = 1):
a
1
(
)
e r a
0
3 1/2
/ 0
ψ = π
−

(8A.16)
This wavefunction is independent of angle and has the same 
value at all points of constant radius; that is, the 1s orbital 
(the s orbital with n = 1, and in general ns) is ‘spherically 
symmetrical’. The wavefunction decays exponentially from a 
maximum value of 1/
a
(
)
0
3 1/2
π
 at the nucleus (at r = 0). It follows 
that the probability density of the electron is greatest at the 
nucleus itself.
The general form of the ground-state wavefunction can be 
understood by considering the contributions of the poten­
tial and kinetic energies to the total energy of the atom. The 
closer the electron is to the nucleus on average, the lower 
(more negative) its average potential energy. This dependence 
suggests that the lowest potential energy should be obtained 
with a sharply peaked wavefunction that has a large ampli­
tude at the nucleus and is zero everywhere else (Fig. 8A.9). 
However, this shape implies a high kinetic energy, because 
such a wavefunction has a very high average curvature. The 
electron would have very low kinetic energy if its wavefunc­
tion had only a very low average curvature. However, such a 
wavefunction spreads to great distances from the nucleus and 
the average potential energy of the electron is correspondingly 
high. The actual ground-state wavefunction is a compromise 
between these two extremes: the wavefunction spreads away 
n
1
2
3
4
∞
1s
2s
2p
3s
3p
3d
4s
4p
4d
4f
[1]
[1]
[1]
[1]
[3]
[3]
[3]
[5]
[5]
[7]
s
p
d
f
Energy
Figure 8A.7  The energy levels of a hydrogenic atom showing the 
subshells and (in square brackets) the numbers of orbitals in each 
subshell. All orbitals of a given shell have the same energy.
s
p
d
Subshells
Shells
M shell, n = 3
L shell, n = 2
K shell, n = 1
Orbitals
Figure 8A.8  The organization of orbitals (white squares) into 
subshells (characterized by l) and shells (characterized by n).
Radius, r
Wavefunction, ψ
Low potential energy
but
high kinetic energy
Low kinetic energy
but
high potential energy
Lowest total energy
a
b
c
Figure 8A.9  The balance of kinetic and potential energies 
that accounts for the structure of the ground state of hydrogenic 
atoms. (a) The sharply curved but localized orbital has high 
mean kinetic energy, but low mean potential energy; (b) the 
mean kinetic energy is low, but the potential energy is not very 
favourable; (c) the compromise of moderate kinetic energy and 
moderately favourable potential energy.


## Página 343

8A  Hydrogenic atoms  311
from the nucleus (so the expectation value of the potential en­
ergy is not as low as in the first example, but nor is it very high) 
and has a reasonably low average curvature (so the expectation 
of the kinetic energy is not very low, but nor is it as high as in 
the first example).
One way of depicting the probability density of the electron 
is to represent |ψ|2 by the density of shading (Fig. 8A.10). A 
simpler procedure is to show only the boundary surface, the 
surface that mirrors the shape of the orbital and captures a 
high proportion (typically about 90 per cent) of the electron 
probability. For the 1s orbital, the boundary surface is a sphere 
centred on the nucleus (Fig. 8A.11).
Example 8A.2  Calculating the mean radius of an orbital
Calculate the mean radius of a hydrogenic 1s orbital.
Collect your thoughts  The mean radius is the expectation value
∫
∫
ψ
ψ τ
ψ
τ
〈〉=
=
r
r
r
*
d
d
2
You need to evaluate the integral by using the wavefunctions 
given in Table 8A.1 and dτ = r2dr sin θ dθ  dϕ (The chemist’s 
toolkit 21 in Topic 7F). The angular parts of the wavefunction 
(Table 7F.1) are normalized in the sense that
Y
sin  d d
1
l m
,
2
0
2
0
l
∫
∫
θ
θ φ =
φ
θ
=
π
=
π
The relevant integral over r is given in the Resource section.
The solution  With the wavefunction written in the form ψ = 
RY, the integration (with the integral over the angular vari­
ables, which is equal to 1, in blue) is
∫
∫
∫
∫
θ
θ φ
〈〉=
=
∞
π
π
∞
r
rR
Y
r
r
r R
r
d sin  d d
d
n l
l m
n l
,
2
,
2
2
3
,
2
0
0
2
0
0
l
For a 1s orbital
R
Z
a
2
e Zr a
1,0
0
3/2
/ 0
= 



−
Hence
∫
〈〉=
=
×
=
−
∞
r
Z
a
r
r
Z
a
Z a
a
Z
4
e
d
4
3!
(2 /
)
3
2
Zr a
3
0
3
3
2
/
0
3
0
3
0
4
0
0





Self-test 8A.2  Evaluate the mean radius of a 3s orbital by 
integration.
Answer: 27a0/2Z
All s orbitals are spherically symmetric, but differ in the 
number of radial nodes. For example, the 1s, 2s, and 3s orbit­
als have 0, 1, and 2 radial nodes, respectively. In general, an ns 
orbital has n − 1 radial nodes. As n increases, the radius of the 
spherical boundary surface that captures a given fraction of 
the probability also increases.
Brief illustration 8A.4
The radial nodes of a 2s orbital lie at the locations where the 
associated Laguerre polynomial factor (Table 8A.1) is equal to 
zero. In this case the factor is simply 2 − ρ so there is a node at 
ρ = 2. For a 2s orbital, ρ = Zr/a0, so the radial node occurs at r 
= 2a0/Z (see Fig. 8A.4).
(f)  Radial distribution functions
The wavefunction yields, through the value of |ψ|2, the prob­
ability of finding an electron in any region. As explained in 
Topic 7B, |ψ|2 is a probability density (dimensions: 1/volume) 
and can be interpreted as a (dimensionless) probability when 
multiplied by the (infinitesimal) volume of interest. Imagine 
a probe with a fixed volume dτ and sensitive to electrons that 
Integral E.3
(a) 1s
(b) 2s
x
x
y
y
z
z
Figure 8A.10  Representations of cross-sections through the (a) 
1s and (b) 2s hydrogenic atomic orbitals in terms of their electron 
probability densities (as represented by the density of shading).
x
y
z
Figure 8A.11  The boundary surface of a 1s orbital, within which 
there is a 90 per cent probability of finding the electron. All s 
orbitals have spherical boundary surfaces.


## Página 344

312 
8  Atomic structure and spectra
can move around near the nucleus of a hydrogenic atom. 
Because the probability density in the ground state of the 
atom is proportional to e
Zr a
2
/ 0
−
, the reading from the detector 
decreases exponentially as the probe is moved out along any 
radius but is constant if the probe is moved on a circle of con­
stant radius (Fig. 8A.12).
Now consider the total probability of finding the electron 
anywhere between the two walls of a spherical shell of thick­
ness dr at a radius r. The sensitive volume of the probe is now 
the volume of the shell (Fig. 8A.13), which is 4πr2dr (the prod­
uct of its surface area, 4πr2, and its thickness, dr). Note that the 
volume probed increases with distance from the nucleus and 
is zero at the nucleus itself, when r = 0. The probability that the 
Probability, ψ*ψdτ
Radius, r
r
Figure 8A.12  A constant-volume electron-sensitive detector (the 
small cube) gives its greatest reading at the nucleus, and a smaller 
reading elsewhere. The same reading is obtained anywhere on a 
circle of given radius at any orientation: the s orbital is spherically 
symmetrical.
Radial distribution function, P/(Z/a0)
Radius, Zr/a0
r
0
0
0.2
0.4
0.6
1
2
3
4
Figure 8A.13  The radial distribution function P(r) is the 
probability density that the electron will be found anywhere 
in a shell of radius r; the probability itself is P(r)dr, where dr is 
the thickness of the shell. For a 1s electron in hydrogen, P(r) is 
a maximum when r is equal to the Bohr radius a0. The value of 
P(r)dr is equivalent to the reading that a detector shaped like a 
spherical shell of thickness dr would give as its radius is varied. 
electron will be found between the inner and outer surfaces of 
this shell is the probability density at the radius r multiplied 
by the volume of the probe, or |ψ(r)|2 × 4πr2dr. This expression 
has the form P(r)dr, where
ψ
= π
P r
r
r
( )
4
| ( )|
2
2 
Radial distribution function
[s orbitals only]
 
(8A.17a)
The function P(r) is called the radial distribution function (in 
this case, for an s orbital). It is also possible to devise a more 
general expression which applies to orbitals that are not spher­
ically symmetrical.
How is that done? 8A.1  Deriving the general form of the 
radial distribution function
The probability of finding an electron in a volume element 
dτ when its wavefunction is ψ = RY is |RY|2dτ with dτ = 
r2dr sin θ dθ dϕ. The total probability of finding the electron 
at any angle in a shell of radius r and thickness dr is the inte­
gral of this probability over the entire surface, and is written 
P(r)dr; so
P r
r
R r
Y
r
r
( )d
( )
d sin  d d
l m
2
,
2
2
0
2
0
l
∫
∫
θ
θ φ
=
π
π
Because the spherical harmonics are normalized to 1 (the blue 
integration, as in Example 8A.2, gives 1), the final result is
P r
r R r
( )
( )
2
2
=

 
(8A.17b)
The radial distribution function is a probability density in 
the sense that, when it is multiplied by dr, it gives the probabil­
ity of finding the electron anywhere between the two walls of 
a spherical shell of thickness dr at the radius r. For a 1s orbital,
=
−
P r
Z
a
r
( )
4
e
Zr a
3
0
3
2
2
/ 0 
(8A.18)
This expression can be interpreted as follows:
• Because r2 = 0 at the nucleus, P(0) = 0. The volume 
of the shell is zero when r = 0 so the probability of 
finding the electron in the shell is zero.
• As r → ∞, P(r) → 0 on account of the exponential 
term. The wavefunction has fallen to zero at great 
distances from the nucleus and there is little prob­
ability of finding the electron even in a large shell.
• The increase in r2 and the decrease in the exponen­
tial factor means that P passes through a maximum 
at an intermediate radius (see Fig. 8A.13); it marks 
the most probable radius at which the electron will 
be found regardless of direction.
Radial distribution function
[general form]
Physical interpretation


## Página 345

8A  Hydrogenic atoms  313
Example 8A.3  Calculating the most probable radius
Calculate the most probable radius, rmp, at which an electron 
will be found when it occupies a 1s orbital of a hydrogenic 
atom of atomic number Z, and tabulate the values for the one-
electron species from H to Ne9+.
Collect your thoughts  You need to find the radius at which the 
radial distribution function of the hydrogenic 1s orbital has 
a maximum value by solving dP/dr = 0. If there are several 
maxima, you should choose the one corresponding to the 
greatest amplitude.
The solution  The radial distribution function is given in eqn 
8A.18. It follows that
=
−




=
−




−
−
P
r
Z
a
r
Zr
a
rZ
a
Zr
a
d
d
4
2
2
e
8
1
e
Zr a
Zr a
3
0
3
2
0
2
/
3
0
3
0
2
/
0
0
This function is zero other than at r = 0 where the term in 
parentheses is zero, which is at
r
a
Z
mp
0
=
Then, with a0 = 52.9 pm, the most probable radii are
H
He+
Li2+
Be3+
B4+
C5+
N6+
O7+
F8+
Ne9+
rmp/pm
52.9
26.5
17.6
13.2
10.6
8.82
7.56
6.61
5.88
5.29
Comment. Notice how the 1s orbital is drawn towards the 
nucleus as the nuclear charge increases. At uranium the most 
probable radius is only 0.58 pm, almost 100 times closer than 
for hydrogen. (On a scale where rmp = 10 cm for H, rmp = 1 mm 
for U.) However, extending this result to very heavy atoms 
neglects important relativistic effects that complicate the 
calculation.
Self-test 8A.3  Find the most probable distance of a 2s electron 
from the nucleus in a hydrogenic atom.
Answer: (3 + 51/2)a0/Z = 5.24a0/Z; this value reﬂects  
the expansion of the atom as its energy increases.
(g)  p Orbitals
All three 2p orbitals have l = 1, and therefore the same mag­
nitude of angular momentum; they are distinguished by dif­
ferent values of ml, the quantum number that specifies the 
component of angular momentum around a chosen axis 
(conventionally taken to be the z-axis). The orbital with ml = 0, 
for instance, has zero angular momentum around the z-axis. 
Its angular variation is given by the spherical harmonic Y1,0, 
which is proportional to cos θ (see Table 7F.1). Therefore, the 
probability density, which is proportional to cos2θ, has its 
maximum value on either side of the nucleus along the z-axis 
(at θ = 0 and 180°, where cos2θ = 1). Specifically, the wavefunc­
tion of a 2p orbital with ml = 0 is
ψ
θ φ
θ
=
=
π




−
R
r Y
Z
a
r
( )
( , )
1
4(2 )
cos  e Zr
a
2,1,0
2,1
1,0
1/2
0
5/2
/2 0
r
f r
cos
( )
θ
=

(8A.19a)
where f(r) is a function only of r. Because in spherical polar co­
ordinates z = r cos θ  (The chemist’s toolkit 21 in Topic 7F), this 
wavefunction may also be written
zf r( )
2,1,0
ψ
=

(8A.19b)
All p orbitals with ml = 0 and any value of n have wavefunc­
tions of this form, but f(r) depends on the value of n. This way 
of writing the orbital is the origin of the name ‘pz orbital’: its 
boundary surface is shown in Fig. 8A.14. The wavefunction 
is zero everywhere in the xy-plane, where z = 0, so the xy-plane 
is a nodal plane of the orbital: the wavefunction changes sign 
on going from one side of the plane to the other.
The wavefunctions of 2p orbitals with ml = ±1 have the fol­
lowing form:
∓
ψ
θ φ
θ
=
=
π




φ
±
±
±
−
R
r Y
Z
a
r
( )
( , )
1
8
sin e
e Zr
a
2,1, 1
2,1
1, 1
1/2
0
5/2
i
/2 0
	
  
θ
=
φ
±
r
f r
1
2
sin e
( )
1/2
i
∓
 
(8A.20)
In Topic 7D it is explained that a particle described by a com­
plex wavefunction has net motion. In the present case, the 
+
+
+
–
–
–
x
y
z
px
py
pz
θ
ϕ
θ = 90°
ϕ = 90°
ϕ = 0
Figure 8A.14  The boundary surfaces of 2p orbitals. A nodal plane 
passes through the nucleus and separates the two lobes of each 
orbital. The dark and light lobes denote regions of opposite sign 
of the wavefunction. The angles of the spherical polar coordinate 
system are also shown. All p orbitals have boundary surfaces like 
those shown here. 


## Página 346

314 
8  Atomic structure and spectra
functions correspond to non-zero angular momentum about 
the z-axis: 
φ
+e i  corresponds to clockwise rotation when viewed 
from below, and 
φ
−e i  corresponds to anticlockwise rotation 
(from the same viewpoint). They have zero amplitude where 
θ = 0 and 180° (along the z-axis) and maximum amplitude at 
90°, which is in the xy-plane. To draw the functions it is usual 
to represent them by forming the linear combinations
ψ
ψ
ψ
θ
φ
=
−
=
=
+
−
r
f r
x f r
1
2
(
)
sin cos
( )
( )
2p
1/2
2,1, 1
2,1, 1
x
ψ
ψ
ψ
θ
φ
=
+
=
=
+
−
r
f r
y f r
i
2
(
)
sin sin
( )
( )
2p
1/2
2,1, 1
2,1, 1
x

(8A.21)
These linear combinations correspond to zero orbital angular 
momentum around the z-axis, as they are superpositions of 
states with equal and opposite values of ml. The px orbital has 
the same shape as a pz orbital, but it is directed along the x-axis 
(see Fig. 8A.14); the py orbital is similarly directed along the 
y-axis. The wavefunction of any p orbital of a given shell can 
be written as a product of x, y, or z and the same function f 
(which depends on the value of n).
(h)  d Orbitals
When n = 3, l can be 0, 1, or 2. As a result, this shell consists 
of one 3s orbital, three 3p orbitals, and five 3d orbitals. Each 
value of the quantum number ml = 0, ±1, ±2 corresponds to 
a different value of the component of angular momentum 
about the z-axis. As for the p orbitals, d orbitals with opposite 
values of ml (and hence opposite senses of motion around the 
z-axis) may be combined in pairs to give real wavefunctions, 
and the boundary surfaces of the resulting shapes are shown 
eiϕ + e−iϕ = 2 cos ϕ
eiϕ − e−iϕ = 2i sin ϕ
x
y
z
+
–
+
–
+
dz2
dx2–y2
dxy
dyz
dzx
+
+
+
+
+
+
+
+
+
+
–
–
–
–
–
–
–
–
–
Figure 8A.15  The boundary surfaces of 3d orbitals. The purple 
and yellow areas denote regions of opposite sign of the 
wavefunction. All d orbitals have boundary surfaces like those 
shown here.
in Fig. 8A.15. The real linear combinations have the following 
forms, with the function f(r) depending on the value of n:
ψ
ψ
ψ
=
=
=
xyf r
yzf r
zxf r
( )    
( )    
( )  
d
d
d
xy
yz
zx
ψ
ψ
=
−
=
−
−
x
y
f r
z
r
f r
(
) ( )    
3
2 (3
) ( )
d
2
2
d
1/2
2
2
1
2
x
y
z
2
2
2

(8A.22)
These linear combinations give rise to the notation dxy, dyz, etc. 
for the d-orbitals. With the exception of the dz2 orbital, each 
combination has two angular nodes which divide the orbital 
into four lobes. For the dz2 orbital, the two angular nodes com­
bine to give a conical surface that separates the main lobes 
from a smaller toroidal component encircling the nucleus.
Checklist of concepts
☐	 1.	 The Schrödinger equation for a hydrogenic atom sepa­
rates into angular and radial equations.
☐	 2.	 Close to the nucleus the radial wavefunction is propor­
tional to r l; far from the nucleus all hydrogenic wave­
functions approach zero exponentially.
☐	 3.	 An atomic orbital is a one-electron wavefunction for 
an electron in an atom.
☐	 4.	 An atomic orbital is specified by the values of the quan­
tum numbers n, l, and ml.
☐	 5.	 The energies of the bound states of hydrogenic atoms 
are proportional to −Z2/n2.
☐	 6.	 The ionization energy of an element is the minimum 
energy required to remove an electron from the ground 
state of one of its atoms.
☐	 7.	 Orbitals of a given value of n form a shell of an atom, 
and within that shell orbitals of the same value of l form 
subshells.


## Página 347

8A  Hydrogenic atoms  315
Checklist of equations
Property
Equation
Comment
Equation number
Wavenumbers of the spectral lines of 
a hydrogen atom
R
n
n
(1/
1/
)   
H
1
2
2
2
ν =
−


RH
  is the Rydberg constant 
for hydrogen (expressed as 
a wavenumber)
8A.1
Bohr radius
a
m e
4
/
0
0
2
e
2
ε
= π
ℏ
a0 = 52.9 pm
8A.9
Wavefunctions of hydrogenic atoms
r
R
r Y
( , , )
( )
( , )
n l m
n l
l m
, ,
,
,
l
l
ψ
θ φ
θ φ
=
Yl m
,
l are spherical harmonics
8A.12
Energies of hydrogenic atoms
E
hcZ R
n
/
, 
n
2
N
2

=−
 
R
e
ch
/8
N
4
0
2
3

µ
ε
=
R
R
N


≈
∞, the Rydberg constant; 
μ = memN/(me + mN)
8A.13
Radial distribution function
=
P r
r R r
( )
( )
2
2
ψ
= π
P r
r
( ) 4
2
2 for s orbitals
8A.17b
☐	 8.	 Orbitals of the same shell all have the same energy in 
hydrogenic atoms; orbitals of the same subshell of a 
shell are degenerate in all types of atoms.
☐	 9.	 s Orbitals are spherically symmetrical and have non-
zero probability density at the nucleus.
☐	10.	 A radial distribution function is the probability den­
sity for the distribution of the electron as a function of 
distance from the nucleus.
☐	11.	 There are three p orbitals in a given subshell; each one 
has one angular node.
☐	12.	 There are five d orbitals in a given subshell; each one 
has two angular nodes.


## Página 348

The individual orbitals can be assumed to resemble the hydro­
genic orbitals based on nuclei with charges modified by the 
presence of all the other electrons in the atom. This assump­
tion can be justified if, to a first approximation, electron–
electron interactions are ignored.
How is that done? 8B.1  Justifying the orbital 
approximation
Consider a system in which the hamiltonian for the energy 
is the sum of two contributions, one for electron 1 and the 
other for electron 2: H
H
H
ˆ
ˆ
ˆ
1
2
=
+
. In an actual two-electron 
atom (such as a helium atom), there is an additional term 
(proportional to 1/r12, where r12 is the distance between the 
two electrons) corresponding to their interaction:
H
m
e
r
m
e
r
e
r
ˆ
2
2
4
2
2
4
4
2
e
1
2
2
0 1
2
e
2
2
2
0 2
2
0 12
ℏ





ℏ





ε
ε
ε
= −
∇−π
−
∇−π
+
π
In the orbital approximation the final term is ignored. Then 
the task is to show that if ψ(r1) is an eigenfunction of Hˆ
1with 
energy E1, and ψ(r2) is an eigenfunction of Hˆ
2 with energy E2, 
then the product Ψ(r1,r2) = ψ(r1)ψ(r2) is an eigenfunction of 
the combined hamiltonian Hˆ. To do so write
HˆΨ (r1,r2) = H
H
( ˆ
ˆ )
1
2
+
ψ (r1)ψ (r2)










ψ
ψ
ψ
ψ
=
+
r
r
r
r
H
H
ˆ
( ) ( )
ˆ
( ) ( )
1
1
2
2
1
2
r
r
r
r
H
H
( ) ˆ
( )
( ) ˆ
( )
2
1
1
2
1
2








ψ
ψ
ψ
ψ
=
+
= ψ(r2) E1ψ(r1) + ψ(r1) E2ψ(r2) = (E1 + E2)ψ(r1)ψ(r2)
= EΨ(r1,r2)
where E = E1 + E2, which is the desired result. Note how each 
hamiltonian operates on only its ‘own’ wavefunction. If the 
electrons interact (as they do in fact), then the term in 1/r12
 
must be included, and the proof fails. Therefore, this descrip­
tion is only approximate, but it is a useful model for discuss­
ing the chemical properties of atoms and is the starting point 
for more sophisticated descriptions of atomic structure.
ˆH2
ˆH1
ψ(r2)Ĥ1ψ(r1)
ψ(r1)Ĥ2ψ(r2)
E2ψ(r2)
E1ψ(r1)
➤  Why do you need to know this material?
Many-electron atoms are the building blocks of all com­
pounds, and to understand their properties, including 
their ability to participate in chemical bonding, it is essen­
tial to understand their electronic structure. Moreover, a 
knowledge of that structure explains the structure of the 
periodic table and all that it summarizes.
➤  What is the key idea?
Electrons occupy the orbitals that result in the lowest 
energy of the atom, subject to the requirements of the 
Pauli exclusion principle.
➤  What do you need to know already?
This Topic builds on the account of the structure of hydro­
genic atoms (Topic 8A), especially their shell structure.
A many-electron atom (or polyelectron atom) is an atom with 
more than one electron. The Schrödinger equation for a many-
electron atom is complicated because all the electrons interact 
with one another. One very important consequence of these 
interactions is that orbitals of the same value of n but differ­
ent values of l are no longer degenerate. Moreover, even for a 
helium atom, with just two electrons, it is not possible to find 
analytical expressions for the orbitals and energies, so it is 
necessary to use various approximations.
8B.1  The orbital approximation
The wavefunction of a many-electron atom is a very compli­
cated function of the coordinates of all the electrons, written 
as Ψ(r1,r2, …), where ri is the vector from the nucleus to elec­
tron i (uppercase psi, Ψ, is commonly used to denote a many-
electron wavefunction). The orbital approximation states that 
a reasonable first approximation to this exact wavefunction is 
obtained by thinking of each electron as occupying its ‘own’ 
orbital, and writing
Ψ(r1,r2, …) = ψ(r1)ψ(r2) …
Orbital approximation  
(8B.1)
TOPIC 8B  Many-electron atoms


## Página 349

8B  Many-electron atoms  317
The orbital approximation can be used to express the elec­
tronic structure of an atom by reporting its configuration, a 
statement of its occupied orbitals (usually, but not necessarily, 
in its ground state). Thus, as the ground state of a hydrogenic 
atom consists of the single electron in a 1s orbital, its configu­
ration is reported as 1s1 (read ‘one-ess-one’).
A He atom has two electrons. The first electron occupies a 1s 
hydrogenic orbital, but because Z = 2 that orbital is more compact 
than in H itself. The second electron joins the first in the 1s or­
bital, so the electron configuration of the ground state of He is 1s2.
Brief illustration 8B.1
According to the orbital approximation, each electron in He 
occupies a hydrogenic 1s orbital of the kind given in Topic 
8A. Anticipating (see below) that the electrons experience an 
effective nuclear charge Zeffe rather than the actual charge 
on the nucleus with Z = 2 (specifically, as seen later, a charge 
1.69e rather than 2e), then the two-electron wavefunction of 
the atom is
Ψ
= π
× π
−
−
r r
Z
a
Z
a
( , )
(
)
e
(
)
e
Z
r a
Z
r a
1
2
eff
3/2
0
3 1/2
/
eff
3/2
0
3 1/2
/
eff 1
0
eff 2
0










= π
−
+
Z
a e Z
r
r
a
eff
3
0
3
(
)/
eff
1
2
0
There is nothing particularly mysterious about a two-electron 
wavefunction: in this case it is a simple exponential function 
of the distances of the two electrons from the nucleus.
8B.2  The Pauli exclusion principle
It is tempting to suppose that the electronic configurations 
of the atoms of successive elements with atomic numbers Z = 
3, 4, …, and therefore with Z electrons, are simply 1sZ. That, 
however, is not the case. The reason lies in two aspects of na­
ture: that electrons possess ‘spin’ and that they must obey the 
very fundamental ‘Pauli principle’.
(a)  Spin
The quantum mechanical property of electron spin, the pos­
session of an intrinsic angular momentum, was identified by 
an experiment performed by Otto Stern and Walther Gerlach 
in 1921, who shot a beam of silver atoms through an inhomo­
geneous magnetic field (Fig. 8B.1). The idea behind the experi­
ment was that each atom possesses a certain electronic angular 
momentum and (because moving charges generate a magnetic 
field) as a result behaves like a small bar magnet aligned with 
ψ1s(r1)
ψ1s(r2)
the direction of the angular momentum vector. As the atoms 
pass through the inhomogeneous magnetic field they are de­
flected, with the deflection depending on the relative orienta­
tion of the applied magnetic field and the atomic magnet.
The classical expectation is that the electronic angular mo­
mentum, and hence the resulting magnet, can be oriented in 
any direction. Each atom would be deflected into a direction 
that depends on the orientation and the beam should spread 
out into a broad band as it emerges from the magnetic field. In 
contrast, the expectation from quantum mechanics is that the 
angular momentum, and hence the atomic magnet, has only 
discrete orientations (Topic 7F). Each of these orientations re­
sults in the atoms being deflected in a specific direction, so the 
beam should split into a number of sharp bands, each corre­
sponding to a different orientation of the angular momentum 
of the electrons in the atom.
In their first experiment, Stern and Gerlach appeared to 
confirm the classical prediction. However, the experiment is 
difficult because collisions between the atoms in the beam blur 
the bands. When they repeated the experiment with a beam of 
very low intensity (so that collisions were less frequent), they 
observed discrete bands, and so confirmed the quantum pre­
diction. However, Stern and Gerlach observed two bands of Ag 
atoms in their experiment. This observation seems to conflict 
with one of the predictions of quantum mechanics, because an 
angular momentum l gives rise to 2l + 1 orientations, which 
is equal to 2 only if l = 1
2, contrary to the requirement that l 
is an integer. The conflict was resolved by the suggestion that 
the angular momentum they were observing was not due to 
orbital angular momentum (the motion of an electron around 
the atomic nucleus) but arose instead from the rotation of the 
electron about its own axis, its ‘spin’.
The spin of an electron does not have to satisfy the same 
boundary conditions as those for a particle circulating through 
space around a central point, so the quantum number for spin 
angular momentum is subject to different restrictions. The spin 
(a)
(b)
(c)
Figure 8B.1  (a) The experimental arrangement for the Stern–
Gerlach experiment: the magnet provides an inhomogeneous 
field. (b) The classically expected result. (c) The observed outcome 
using silver atoms.


## Página 350

318 
8  Atomic structure and spectra
quantum number s is used in place of the orbital angular mo­
mentum quantum number l (Topic 7F; like l, s is a non‑negative 
number) and ms, the spin magnetic quantum number, is used 
in place of ml for the projection on the z‑axis. The magnitude of 
the spin angular momentum is s s
{ ( + 1)}1/2ħ and the component 
msħ is restricted to the 2s + 1 values ms = s, s − 1, …, −s. To ac­
count for Stern and Gerlach’s observation, s = 1
2 and ms = ± 1
2.
A note on good practice  You will sometimes see the quantum 
number s used in place of ms, and written s = ± 1
2 . That is wrong: 
like l, s is never negative and denotes the magnitude of the spin 
angular momentum. For the z-component, use ms.
The detailed analysis of the spin of a particle is sophisticated 
and shows that the property should not be taken to be an actual 
spinning motion. It is better to regard ‘spin’ as an intrinsic prop­
erty like mass and charge: every electron has exactly the same 
value and the magnitude of the spin angular momentum of an 
electron cannot be changed. However, the picture of an actual 
spinning motion can be very useful when used with care. In the 
vector model of angular momentum (Topic 7F), the spin may 
lie in two different orientations (Fig. 8B.2). One orientation cor­
responds to ms = + 1
2 (this state is often denoted α or ↑); the other 
orientation corresponds to ms = − 1
2 (this state is denoted β or ↓).
Other elementary particles have characteristic spin. For exam­
ple, protons and neutrons are spin- 1
2 particles (i.e. s = 1
2). Because 
the masses of a proton and a neutron are so much greater than 
the mass of an electron, yet they all have the same spin an­
gular momentum, the classical picture would be of these two 
particles spinning much more slowly than an electron. Some 
mesons, another variety of fundamental particle, are spin‑1 
particles (i.e. s = 1), as are some atomic nuclei, but for our pur­
poses the most important spin‑1 particle is the photon. The 
importance of photon spin in spectroscopy is explained in 
Topic 11A; nuclear spin is the basis of nuclear magnetic reso­
nance (Topic 12A).
Brief illustration 8B.2
The magnitude of the spin angular momentum, like any 
angular momentum, is {s(s + 1)}1/2 ħ. For any spin- 1
2  particle, 
not only electrons, this angular momentum is ( )
3
4
1/2ħ = 0.866ħ, 
or 9.13 × 10−35 J s. The component on the z-axis is msħ, which 
for a spin-1
2  particle is ± 1
2 ħ, or ±5.27 × 10−35 J s.
Particles with half‑integral spin are called fermions and 
those with integral spin (including 0) are called bosons. Thus, 
electrons and protons are fermions; photons are bosons. It is 
a very deep feature of nature that all the elementary particles 
that constitute matter are fermions whereas the elementary 
particles that transmit the forces that bind fermions together 
are all bosons. Photons, for example, transmit the electromag­
netic force that binds together electrically charged particles. 
Matter, therefore, is an assembly of fermions held together by 
forces conveyed by bosons.
(b)  The Pauli principle
With the concept of spin established, it is possible to resume 
discussion of the electronic structures of atoms. Lithium, with 
Z = 3, has three electrons. The first two occupy a 1s orbital 
drawn even more closely than in He around the more highly 
charged nucleus. The third electron, however, does not join the 
first two in the 1s orbital because that configuration is forbid­
den by the Pauli exclusion principle:
No more than two electrons may occupy any 
given orbital, and if two do occupy one orbital, 
then their spins must be paired.
Electrons with paired spins, denoted ↑↓, have zero net spin an­
gular momentum because the spin of one electron is cancelled 
by the spin of the other. Specifically, one electron has ms = + 1
2 
the other has ms = − 1
2 and in the vector model they are orien­
tated on their respective cones so that the resultant spin is zero 
(Fig. 8B.3). The exclusion principle is the key to the structure 
of complex atoms, to chemical periodicity, and to molecular 
structure. It was proposed by Wolfgang Pauli in 1924 when he 
was trying to account for the absence of some lines in the spec­
trum of helium. Later he was able to derive a very general form 
of the principle from theoretical considerations.
The Pauli exclusion principle is a special case of a general 
statement called the Pauli principle:
ms = +
ms = –
1
2
1
2
Figure 8B.2  The vector representation of the spin of an electron. 
The length of the side of the cone is 3
2
1/2/  units and the projections 
on to the z-axis are ± 1
2 units. 
Pauli 
exclusion 
principle
ms = +
ms = –
1
2
1
2
Figure 8B.3  Electrons with paired spins have zero resultant spin 
angular momentum. They can be represented by two vectors that 
lie at an indeterminate position on the cones shown here, but 
wherever one lies on its cone, the other points in the opposite 
direction; their resultant is zero.


## Página 351

8B  Many-electron atoms  319
When the labels of any two identical fermions are 
exchanged, the total wavefunction changes sign; when 
the labels of any two identical bosons are exchanged, 
the sign of the total wavefunction remains the same.
By ‘total wavefunction’ is meant the entire wavefunction, in­
cluding the spin of the particles.
To see that the Pauli principle implies the Pauli exclusion 
principle, consider the wavefunction for two electrons, Ψ(1,2). 
The Pauli principle implies that it is a fact of nature (which has 
its roots in the theory of relativity) that the wavefunction must 
change sign if the labels 1 and 2 are interchanged wherever 
they occur in the function:
Ψ(2,1) = −Ψ(1,2)
(8B.2)
Suppose the two electrons in a two-electron atom occupy the 
same orbital ψ, then in the orbital approximation the overall 
spatial wavefunction is ψ(r1)ψ(r2), which for simplicity will be 
denoted ψ(1)ψ(2). To apply the Pauli principle, it is necessary 
to consider the total wavefunction, the wavefunction includ­
ing spin. There are several possibilities for two electrons: both 
α, denoted α(1)α(2), both β, denoted β(1)β(2), and one α and 
the other β, denoted either α(1)β(2) or α(2)β(1). Because it is 
not possible to know which electron is α and which is β, in the 
last case it is appropriate to express the spin states as the (nor­
malized) linear combinations1
σ+(1,2) = 



1
21/2 {α(1)β(2) + β(1)α(2)}
σ−(1,2) = 



1
21/2 {α(1)β(2) − β(1)α(2)}
(8B.3)
These combinations allow one spin to be α and the other 
β with equal probability; the former corresponds to paral­
lel spins (the individual spins do not cancel) and the latter to 
paired spins (the individual spins cancel). The total wavefunc­
tion of the system is therefore the product of the orbital part 
and one of the four spin states:
ψ(1)ψ(2)α(1)α(2)       ψ(1)ψ(2)β(1)β(2)
ψ(1)ψ(2)σ+(1,2)          ψ(1)ψ(2)σ−(1,2)
(8B.4)
The Pauli principle says that for a wavefunction to be accept­
able (for electrons), it must change sign when the electrons are 
exchanged. In each case, exchanging the labels 1 and 2 con­
verts ψ(1)ψ(2) into ψ(2)ψ(1), which is the same, because the 
order of multiplying the functions does not change the value 
of the product. The same is true of α(1)α(2) and β(1)β(2). 
Therefore, ψ(1)ψ(2)α(1)α(2) and ψ(1)ψ(2)β(1)β(2) are not 
allowed, because they do not change sign. When the labels are 
exchanged the combination σ+(1,2) becomes
σ+(2,1) = 



1
21/2 {α(2)β(1) + β(2)α(1)} = σ+(1,2)
because the central term is simply the original function writ­
ten in a different order. The product ψ(1)ψ(2)σ+(1,2) is there­
fore also disallowed. Finally, consider σ−(1,2):
σ−(2,1) = 



1
21/2 {α(2)β(1) − β(2)α(1)}
= − 



1
21/2 {α(1)β(2) − β(1)α(2)} = −σ−(1,2)
The combination ψ(1)ψ(2)σ−(1,2) therefore does change sign 
(it is ‘antisymmetric’) and is acceptable.
In summary, only one of the four possible states is allowed 
by the Pauli principle: the one that survives has paired α and β 
spins. This is the content of the Pauli exclusion principle. The 
exclusion principle (but not the more general Pauli principle) 
is irrelevant when the orbitals occupied by the electrons are 
different, and both electrons may then have, but need not have, 
the same spin state. In each case the overall wavefunction 
must still be antisymmetric and must satisfy the Pauli prin­
ciple itself.
Now returning to lithium, Li (Z = 3), the third electron can­
not enter the 1s orbital because that orbital is already full: the 
K shell (the shell with n = 1, Topic 8A) is complete and the two 
electrons form a closed shell, a shell in which all the orbitals 
are fully occupied. Because a similar closed shell is character­
istic of the He atom, it is commonly denoted [He]. The third 
electron cannot enter the K shell and must occupy the next 
available orbital, which is one with n = 2 and hence belonging 
to the L shell (which consists of the four orbitals with n = 2). It 
is now necessary to decide whether the next available orbital is 
the 2s orbital or a 2p orbital, and therefore whether the lowest 
energy configuration of the atom is [He]2s1 or [He]2p1.
8B.3  The building-up principle
Unlike in hydrogenic atoms, the 2s and 2p orbitals (and, in 
general, the subshells of a given shell) do not have the same 
energy in many-electron atoms.
(a)  Penetration and shielding
An electron in a many-electron atom experiences a Coulombic 
repulsion from all the other electrons present. If the electron is 
at a distance r from the nucleus, it experiences an average re­
pulsion that can be represented by a point negative charge lo­
cated at the nucleus and equal in magnitude to the total charge 
Pauli principle
1 A stronger justification for taking these linear combinations is that they 
correspond to eigenfunctions of the total spin operators S2 and Sz, with MS = 
0 and, respectively, S = 1 and 0.


## Página 352

320 
8  Atomic structure and spectra
of all the other electrons within a sphere of radius r (Fig. 8B.4). 
This property is a conclusion of classical electrostatics, where 
the effect of a spherical distribution of charge can be repre­
sented by a point charge of the same magnitude located at its 
centre. The effect of this point negative charge is to reduce the 
full charge of the nucleus from Ze to Zeffe, the effective nuclear 
charge. In everyday parlance, Zeff itself is commonly referred 
to as the ‘effective nuclear charge’. The electron is said to expe­
rience a shielded nuclear charge, and the difference between Z 
and Zeff is called the shielding constant, σ:
Zeff = Z − σ
Nuclear shielding  
(8B.5)
The electrons do not actually ‘block’ the full Coulombic at­
traction of the nucleus: the shielding constant is simply a way 
of expressing the net outcome of the nuclear attraction and the 
electronic repulsions in terms of a single equivalent charge at 
the centre of the atom.
The shielding constant is different for s and p electrons be­
cause they have different radial distribution functions and 
therefore respond to the other electrons in the atom to differ­
ent extents (Fig. 8B.5). An s electron has a greater penetration 
through inner shells than a p electron, in the sense that an s 
electron is more likely to be found close to the nucleus than a 
p electron of the same shell. Because only electrons inside the 
sphere defined by the location of the electron of interest con­
tribute to shielding, an s electron experiences less shielding 
than a p electron. Consequently, as a result of the combined 
effects of penetration and shielding, an s electron is more 
tightly bound than a p electron of the same shell. Similarly, 
a d electron penetrates less than a p electron of the same shell 
(recall that a d orbital is proportional to r2 close to the nucleus, 
whereas a p orbital is proportional to r, so the amplitude of a d 
orbital is smaller there than that of a p orbital), and therefore 
experiences more shielding.
Shielding constants for different types of electrons in atoms 
have been calculated from wavefunctions obtained by nu­
merical solution of the Schrödinger equation (Table 8B.1). In 
general, valence-shell s electrons do experience higher effec­
tive nuclear charges than p electrons, although there are some 
discrepancies.
Brief illustration 8B.3
The effective nuclear charge for 1s, 2s, and 2p electrons in a 
carbon atom are 5.6727, 3.2166, and 3.1358, respectively. The 
radial distribution functions for these orbitals (Topic 8A) are 
generated by forming P(r) = r2R(r)2, where R(r) is the radial 
wavefunction, which are given in Table 8A.1. The three radial 
distribution functions are plotted in Fig. 8B.6. As can be seen 
(especially in the magnified view close to the nucleus), the s 
orbital has greater penetration than the p orbital. The average 
radii of the 2s and 2p orbitals are 99 pm and 84 pm, respective­
ly, which shows that the average distance of a 2s electron from 
the nucleus is greater than that of a 2p orbital. To account for 
the lower energy of the 2s orbital, the extent of penetration is 
more important than the average distance from the nucleus.
The consequence of penetration and shielding is that the en­
ergies of subshells of a shell in a many-electron atom (those 
No net effect of
these electrons
Net effect equivalent 
to a point charge at
the nucleus
r
Electron location
Figure 8B.4  An electron at a distance r from the nucleus 
experiences a Coulombic repulsion from all the electrons within a 
sphere of radius r. This repulsion is equivalent to that from a point 
negative charge located on the nucleus. The negative charge 
reduces the effective nuclear charge of the nucleus from Ze to 
Zeffe.
Radial distribution function, P
3p
3s
Radius, Zr/a0
0
0
4
8
12
16
20
Figure 8B.5  An electron in an s orbital (here a 3s orbital) is more 
likely to be found close to the nucleus than an electron in a p 
orbital of the same shell (note the closeness of the innermost 
peak of the 3s orbital to the nucleus at r = 0). Hence an s electron 
experiences less shielding and is more tightly bound than a p 
electron of the same shell.
Table 8B.1  Effective nuclear charge*
Element
Z
Orbital
Zeff
He
2
1s
1.6875
C
6
1s
5.6727
2s
3.2166
2p
3.1358
* More values are given in the Resource section.


## Página 353

8B  Many-electron atoms  321
with the same values of n but different values of l) in general lie 
in the order s < p < d < f. The individual orbitals of a given sub­
shell (those with the same value of l but different values of ml) 
remain degenerate because they all have the same radial char­
acteristics and so experience the same effective nuclear charge.
To complete the Li story, consider that, because the shell 
with n = 2 consists of two subshells, with the 2s subshell lower 
in energy than the 2p subshell, the third electron occupies the 
2s orbital (the only orbital in that subshell). This occupation 
results in the ground-state configuration 1s22s1, with the cen­
tral nucleus surrounded by a complete helium-like shell of two 
1s electrons, and around that a more diffuse 2s electron. The 
electrons in the outermost shell of an atom in its ground state 
are called the valence electrons because they are largely re­
sponsible for the chemical bonds that the atom forms (and ‘va­
lence’, as explained in Focus 9, refers to the ability of an atom 
to form bonds). Thus, the valence electron in Li is a 2s electron 
and its other two electrons belong to its core.
(b)  Hund’s rules
The extension of the argument used to account for the structures 
of H, He, and Li is called the building-up principle, or the 
Aufbau principle, from the German word for “building up”, 
and should be familiar from introductory courses. In brief, 
imagine the bare nucleus of atomic number Z, and then feed 
into the orbitals Z electrons in succession. The order of oc­
cupation, following the shells and their subshells arranged in 
order of increasing energy, is
1s   2s   2p   3s   3p   4s   3d   4p   5s   4d   5p   6s
Each orbital may accommodate up to two electrons.
Brief illustration 8B.4
Consider the carbon atom, for which Z = 6 and there are six 
electrons to accommodate. Two electrons enter and fill the 1s 
orbital, two enter and fill the 2s orbital, leaving two electrons 
to occupy the orbitals of the 2p subshell. Hence the ground-
state configuration of C is 1s22s22p2, or more succinctly 
[He]2s22p2, with [He] the helium-like 1s2 core.
It is possible to be more precise about the configuration 
of a carbon atom than in Brief illustration 8B.4. The last two 
electrons are expected to occupy different 2p orbitals because 
they are then farther apart on average and repel each other less 
than if they were in the same orbital. Thus, one electron can 
be thought of as occupying the 2px orbital and the other the 
2py orbital (the x, y, z designation is arbitrary, and it would be 
equally valid to use the complex forms of these orbitals), and 
the lowest energy configuration of the atom is [He]2s22px
12py
1. 
The same rule applies whenever degenerate orbitals of a sub­
shell are available for occupation. Thus, another rule of the 
building-up principle is:
Electrons occupy different orbitals of a given subshell 
before doubly occupying any one of them.
For instance, nitrogen (Z = 7) has the ground-state configura­
tion [He]2s22px
1 2py
12pz
1, and only at oxygen (Z = 8) is a 2p orbital 
doubly occupied, giving [He]2s22px
22py
12pz
1.
When electrons occupy orbitals singly it is necessary to in­
voke Hund’s maximum multiplicity rule:
An atom in its ground state adopts a 
configuration with the greatest number of 
unpaired electrons.
The explanation of Hund’s rule is subtle, but it reflects the 
quantum mechanical property of spin correlation. In essence, 
the effect of spin correlation is to allow the atom to shrink 
slightly when the spins are parallel, so the electron–nucleus 
interaction is improved. As a consequence, in the ground 
state of the carbon atom, the two 2p electrons have parallel 
spins, all three 2p electrons in the N atoms have parallel spins, 
and the two 2p electrons in different orbitals in the O atom 
have parallel spins (the two in the 2px orbital are necessarily 
paired). The effect can be explained by considering the Pauli 
principles and showing that electrons with parallel spins be­
have as if they have a tendency to stay apart, and hence repel 
each other less.
How is that done? 8B.2  Exploring the origins of spin 
correlation
Suppose electron 1 is in orbital a and described by a wavefunc­
tion ψa(r1), and electron 2 is in orbital b with wavefunction 
ψb(r2). Then, in the orbital approximation, the joint spatial 
wavefunction of the electrons is the product Ψ = ψa(r1)ψb(r2). 
However, this wavefunction is not acceptable, because it 
suggests that it is possible to know which electron is in 
0
1
2
3
4
5
0
0.5
1
1.5
2
2.5
3
3.5
1s
2s
2p
r/a0
P(r)a0
0
0
Figure 8B.6  The radial distribution functions for electrons in a 
carbon atom, as calculated in Brief illustration 8B.3.
Hund’s 
maximum 
multiplicity 
rule


## Página 354

322 
8  Atomic structure and spectra
which orbital. According to quantum mechanics, the correct 
description is either of the two following wavefunctions:
Ψ ± = 



1
21/2 {ψa(r1)ψb(r2) ± ψb(r1)ψa(r2)}
According to the Pauli principle, because Ψ+ is symmetri­
cal under particle interchange, it must be multiplied by an 
antisymmetric spin state (the one denoted σ−). That combi­
nation corresponds to a spin-paired state. Conversely, Ψ− is 
antisymmetric, so it must be multiplied by one of the three 
symmetric spin states. These three symmetric states cor­
respond to electrons with parallel spins (see Topic 8C for an 
explanation of this point).
Now consider the behaviour of the two wavefunctions Ψ± 
when one electron approaches another, and r1 = r2. As a result, 
Ψ− vanishes, which means that there is zero probability of 
finding the two electrons at the same point in space when they 
have parallel spins. In contrast, the wavefunction Ψ+ does not 
vanish when the two electrons are at the same point in space. 
Because the two electrons have different relative spatial distri­
butions depending on whether their spins are parallel or not, 
it follows that their Coulombic interaction is different, and 
hence that the two states described by these wavefunctions 
have different energies, with the spin-parallel state lower in 
energy than the spin-paired state.
Neon, with Z = 10, has the configuration [He]2s22p6, which 
completes the L shell. This closed-shell configuration is de­
noted [Ne], and acts as a core for subsequent elements. The 
next electron must enter the 3s orbital and begin a new shell, 
so an Na atom, with Z = 11, has the configuration [Ne]3s1. Like 
lithium with the configuration [He]2s1, sodium has a single s 
electron outside a complete core. This analysis hints at the ori­
gin of chemical periodicity. The L shell is completed by eight 
electrons, so the element with Z = 3 (Li) should have similar 
properties to the element with Z = 11 (Na). Likewise, Be (Z = 
4) should be similar to Z = 12 (Mg), and so on, up to the noble 
gases He (Z = 2), Ne (Z = 10), and Ar (Z = 18).
At potassium (Z = 19) the next orbital in line for occupa­
tion is 4s: this orbital is brought below 3d by the effects of pen­
etration and shielding, and the ground state configuration is 
[Ar]4s1. Calcium (Z = 20) is likewise [Ar]4s2. At this stage the 
five 3d orbitals are in line for occupation, but there are compli­
cations arising from the energy changes arising from the in­
teraction of the electrons in the valence shell, and penetration 
arguments alone are no longer reliable.
Calculations of the type discussed in Section 8B.4 show that 
for the atoms from scandium to zinc the energies of the 3d 
orbitals are always lower than the energy of the 4s orbital, in 
spite of the greater penetration of a 4s electron. However, spec­
troscopic results show that Sc has the configuration [Ar]3d14s2, 
not [Ar]3d3 or [Ar]3d24s1. To understand this observation, 
consider the nature of electron–electron repulsions in 3d and 
4s orbitals. Because the average distance of a 3d electron from 
the nucleus is less than that of a 4s electron, two 3d electrons 
are so close together that they repel each other more strongly 
than two 4s electrons do and 3d2 and 3d3 configurations are 
disfavoured. As a result, Sc has the configuration [Ar]3d14s2 
rather than the two alternatives, for then the strong electron–
electron repulsions in the 3d orbitals are minimized. The total 
energy of the atom is lower despite the cost of allowing elec­
trons to populate the high energy 4s orbital (Fig. 8B.7). The ef­
fect just described is generally true for scandium to zinc, so 
their electron configurations are of the form [Ar]3dn4s2, where 
n = 1 for scandium and n = 10 for zinc. Two notable excep­
tions, which are observed experimentally, are Cr, with electron 
configuration [Ar]3d54s1, and Cu, with electron configuration 
[Ar]3d104s1. At gallium, these complications disappear and 
the building-up principle is used in the same way as in pre­
ceding periods. Now the 4s and 4p subshells constitute the va­
lence shell, and the period terminates with krypton. Because 
18 electrons have intervened since argon, this row is the first 
‘long period’ of the periodic table.
At this stage it becomes apparent that sequential occupation 
of the orbitals in successive shells results in periodic similari­
ties in the electronic configurations. This periodicity of struc­
ture accounts for the formulation of the periodic table (see 
inside the back cover). The vertical columns of the periodic 
table are called groups and (in the modern convention) num­
bered from 1 to 18. Successive rows of the periodic table are 
called periods, the number of the period being equal to the 
principal quantum number of the valence shell.
The periodic table is divided into s, p, d, and f blocks, ac­
cording to the subshell that is last to be occupied in the for­
mulation of the electronic configuration of the atom. The 
members of the d block (specifically the members of Groups 
3–11 in the d block) are also known as the transition met­
als; those of the f block (which is not divided into numbered 
groups) are sometimes called the inner transition metals. The 
upper row of the f block (Period 6) consists of the lanthanoids 
Energy
Figure 8B.7  Strong electron–electron repulsions in the 3d 
orbitals are minimized in the ground state of Sc if the atom 
has the configuration [Ar]3d14s2 (shown on the left) instead of 
[Ar]3d24s1 (shown on the right). The total energy of the atom is 
lower when it has the [Ar]3d14s2 configuration despite the cost 
of populating the high energy 4s orbital.


## Página 355

8B  Many-electron atoms  323
(still commonly the ‘lanthanides’) and the lower row (Period 7) 
consists of the actinoids (still commonly the ‘actinides’).
The configurations of cations of elements in the s, p, and d 
blocks of the periodic table are derived by removing electrons 
from the ground-state configuration of the neutral atom in a 
specific order. First, remove valence p electrons, then valence 
s electrons, and then as many d electrons as are necessary to 
achieve the specified charge. The configurations of anions of 
the p-block elements are derived by continuing the building-
up procedure and adding electrons to the neutral atom until 
the configuration of the next noble gas has been reached.
Brief illustration 8B.5
Because the configuration of vanadium is [Ar]3d34s2, the V2+ 
cation has the configuration [Ar]3d3. It is reasonable to remove 
the more energetic 4s electrons in order to form the cation, but 
it is not obvious why the [Ar]3d3 configuration is preferred 
in V2+ over the [Ar]3d14s2 configuration, which is found in 
the isoelectronic Sc atom. Calculations show that the energy 
difference between [Ar]3d3 and [Ar]3d14s2 depends on Zeff. As 
Zeff increases, transfer of a 4s electron to a 3d orbital becomes 
more favourable because the electron–electron repulsions are 
compensated by attractive interactions between the nucleus 
and the electrons in the spatially compact 3d orbital. Indeed, 
calculations reveal that, for a sufficiently large Zeff, [Ar]3d3 
is lower in energy than [Ar]3d14s2. This conclusion explains 
why V2+ has a [Ar]3d3 configuration and also accounts for the 
observed [Ar]4s03dn configurations of the M2+ cations of Sc 
through Zn.
(c)  Atomic and ionic radii
The atomic radius of an element is half the distance between 
the centres of neighbouring atoms in a solid (such as Cu) or, 
for non-metals, in a homonuclear molecule (such as H2 or S8). 
As seen in Table 8B.2 and Fig. 8B.8, atomic radii tend to de­
crease from left to right across a period of the periodic table, 
and increase down each group. The decrease across a period 
can be traced to the increase in nuclear charge, which draws 
the electrons in closer to the nucleus. The increase in nuclear 
charge is partly cancelled by the increase in the number of 
electrons, but because electrons are spread over a region of 
space, one electron does not fully shield one nuclear charge, 
so the increase in nuclear charge dominates. The increase in 
atomic radius down a group (despite the increase in nuclear 
charge) is explained by the fact that the valence shells of suc­
cessive periods correspond to higher principal quantum num­
bers. That is, successive periods correspond to the start and 
then completion of successive (and more distant) shells of the 
atom that surround each other like the successive layers of an 
onion. The need to occupy a more distant shell leads to a larger 
atom despite the increased nuclear charge.
A modification of the increase down a group is encountered 
in Period 6, for the radii of the atoms in the d block and in 
the following atoms of the p block are not as large as would be 
expected by simple extrapolation down the group. The reason 
can be traced to the fact that in Period 6 the f orbitals are in the 
process of being occupied. An f electron is a very inefficient 
shielder of nuclear charge (for reasons connected with its ra­
dial extension), and as the atomic number increases from La 
to Lu, there is a considerable contraction in radius. By the time 
the d block resumes (at hafnium, Hf), the poorly shielded but 
considerably increased nuclear charge has drawn in the sur­
rounding electrons, and the atoms are compact. They are so 
compact, that the metals in this region of the periodic table 
(iridium to lead) are very dense. The reduction in radius below 
that expected by extrapolation from preceding periods is 
called the lanthanide contraction.
The ionic radius of an element is its share of the distance 
between neighbouring ions in an ionic solid. That is, the dis­
tance between the centres of a neighbouring cation and anion 
is the sum of the two ionic radii. The size of the ‘share’ leads 
Table 8B.2  Atomic radii of main-group elements, r/pm*
Li
157
Be
112
B
88
C
77
N
74
O
66
F
64
Na
191
Mg
160
Al
143
Si
118
P
110
S
104
Cl
99
K
235
Ca
197
Ga
153
Ge
122
As
121
Se
117
Br
114
Rb
250
Sr
215
In
167
Sn
158
Sb
141
Te
137
I
133
Cs
272
Ba
224
Tl
171
Pb
175
Bi
182
Po
167
* More values are given in the Resource section.
Li
Na
K
Rb
Cs
1 
20
40
60
80
100
0
100
200
300
Atomic radius, r/pm
Atomic number, Z
F
Cl
Zn
Br
I
Eu
Lu
Yb
Pb
Ac
Po
Am
Lanthanoids
Figure 8B.8  The variation of atomic radius through the periodic 
table. Note the contraction of radius following the lanthanoids in 
Period 6 (following Lu, lutetium).


## Página 356

324 
8  Atomic structure and spectra
to some ambiguity in the definition. One common definition 
sets the ionic radius of O2− equal to 140 pm, but there are other 
scales, and care must be taken not to mix them. Ionic radii also 
vary with the number of counterions (ions of opposite charge) 
around a given ion; unless otherwise stated, the values in this 
text have been corrected to correspond to an environment of 
six counterions.
When an atom loses one or more valence electrons to 
form a cation, the remaining atomic core is smaller than the 
parent atom. Therefore, a cation is invariably smaller than its 
parent atom. For example, the atomic radius of Na, with the 
configuration [Ne]3s1, is 191 pm, but the ionic radius of Na+, 
with the configuration [Ne], is only 102 pm (Table 8B.3). Like 
atomic radii, cation radii increase down each group because 
electrons are occupying shells with higher principal quantum 
numbers.
An anion is larger than its parent atom because the elec­
trons added to the valence shell repel one another. Without 
a compensating increase in the nuclear charge, which would 
draw the electrons closer to the nucleus and each other, the 
ion expands. The variation in anion radii shows the same 
trend as that for atoms and cations, with the smallest ani­
ons at the upper right of the periodic table, close to fluorine 
(Table 8B.3).
Brief illustration 8B.6
The Ca2+, K+, and Cl− ions have the configuration [Ar]. 
However, their radii differ because they have different nuclear 
charges. The Ca2+ ion has the largest nuclear charge, so it has 
the strongest attraction for the electrons and the smallest 
radius. The Cl− ion has the lowest nuclear charge of the three 
ions and, as a result, the largest radius.
(d)  Ionization energies and electron affinities
The minimum energy necessary to remove an electron from a 
many-electron atom in the gas phase is the first ionization en­
ergy, I1, of the element. The second ionization energy, I2, is the 
minimum energy needed to remove a second electron (from 
the singly charged cation). The variation of the first ionization 
energy through the periodic table is shown in Fig. 8B.9 and 
some numerical values are given in Table 8B.4.
The electron affinity, Eea, is the energy released when an 
electron attaches to a gas-phase atom (Table 8B.5). In a com­
mon, logical (given its name), but not universal convention 
(which is adopted here), the electron affinity is positive if en­
ergy is released when the electron attaches to the atom. That is, 
Eea > 0 implies that electron attachment is exothermic.
As will be familiar from introductory chemistry, ionization 
energies and electron affinities show periodicities. The former 
is more regular and concentrated on here. Lithium has a low 
first ionization energy because its outermost electron is well 
shielded from the nucleus by the core (Zeff = 1.3, compared 
with Z = 3). The ionization energy of Be (Z = 4) is greater but 
that of B is lower because in the latter the outermost electron 
occupies a 2p orbital and is less strongly bound than if it had 
been a 2s electron. The ionization energy increases from B to 
N on account of the increasing nuclear charge. However, the 
ionization energy of O is less than would be expected by sim­
ple extrapolation. The explanation is that at oxygen a 2p or­
bital must become doubly occupied, and the electron–electron 
repulsions are increased above what would be expected by 
simple extrapolation along the row. In addition, the loss of a 
2p electron results in a configuration with a half-filled subshell 
(like that of N), which is an arrangement of low energy, so the 
energy of O+ + e− is lower than might be expected, and the 
ionization energy is correspondingly low too. (The kink is less 
pronounced in the next row, between phosphorus and sulfur 
Table 8B.3  Ionic radii, r/pm*
Li+(4)
Be2+(4)
B3+(4)
N3−
O2−(6)
F−(6)
59
27
12
171
140
133
Na+(6)
Mg2+(6)
Al3+(6)
P3−
S2−(6)
Cl−(6)
102
 72
53
212
184
181
K+(6)
Ca2+(6)
Ga3+(6)
As3−(6)
Se2−(6)
Br−(6)
138
100
62
222
198
196
Rb+(6)
Sr2+(6)
In3+(6)
Te2−(6)
I−(6)
149
116
79
221
220
Cs+(6)
Ba2+(6)
Tl3+(6)
167
136
88
* Numbers in parentheses are the coordination numbers of the ions, the numbers of 
species (for example, counterions, solvent molecules) around the ions. Values for ions 
without a coordination number stated are estimates. More values are given in the 
Resource section.
Figure 8B.9  The first ionization energies of the elements plotted 
against atomic number.
Ionization energy, I/eV
0 0
10
20
20
30
He
Ne
Ar
Kr
Xe
40
60
80
100
Atomic number, Z
Hg
Rn
Li
Na
K
Rb
Cs


## Página 357

8B  Many-electron atoms  325
because their orbitals are more diffuse.) The values for O, F, 
and Ne fall roughly on the same line, the increase of their ioni­
zation energies reflecting the increasing attraction of the more 
highly charged nuclei for the outermost electrons.
The outermost electron in sodium (Z = 11) is 3s. It is far from 
the nucleus, and the latter’s charge is shielded by the compact, 
complete neon-like core, with the result that Zeff ≈ 2.5. As a 
result, the ionization energy of Na is substantially lower than 
that of Ne (Z = 10, Zeff ≈ 5.8). The periodic cycle starts again 
along this row, and the variation of the ionization energy can 
be traced to similar reasons.
Electron affinities are greatest close to fluorine, for the in­
coming electron enters a vacancy in a compact valence shell 
and can interact strongly with the nucleus. The attachment of 
an electron to an anion (as in the formation of O2− from O−) 
is invariably endothermic, so Eea is negative. The incoming 
electron is repelled by the charge already present. Electron af­
finities are also small, and may be negative, when an electron 
enters an orbital that is far from the nucleus (as in the heavier 
alkali metal atoms) or is forced by the Pauli principle to oc­
cupy a new shell (as in the noble gas atoms).
8B.4  Self-consistent field orbitals
The preceding treatment of the electronic configuration of 
many-electron species is only approximate because of the 
complications introduced by electron–electron interactions. 
However, computational techniques are available that give 
reliable approximate solutions for the wavefunctions and en­
ergies. The techniques were originally introduced by D.R. 
Hartree (before computers were available) and then modified 
by V. Fock to take into account the Pauli principle correctly. 
In broad outline, the Hartree–Fock self-consistent field (HF-
SCF) procedure is as follows.
Start with an idea of the structure of the atom as suggested 
by the building-up principle. In the Ne atom, for instance, the 
principle suggests the configuration 1s22s22p6 with the orbitals 
approximated by hydrogenic atomic orbitals with the appropri­
ate effective nuclear charges. Now consider one of the 2p elec­
trons. A Schrödinger equation can be written for this electron 
by ascribing to it a potential energy due to the nuclear attraction 
and the average repulsion from the other electrons. Although 
the equation is for the 2p orbital, that repulsion, and therefore 
the equation, depends on the wavefunctions of all the other 
occupied orbitals in the atom. To solve the equation, guess an 
approximate form of the wavefunctions of all the other orbit­
als and then solve the Schrödinger equation for the 2p orbital. 
The procedure is then repeated for the 1s and 2s orbitals. This 
sequence of calculations gives the form of the 2p, 2s, and 1s or­
bitals, and in general they will differ from the set used to start 
the calculation. These improved orbitals can be used in another 
cycle of calculation, and a second improved set of orbitals and 
a better energy are obtained. The recycling continues until the 
orbitals and energies obtained are insignificantly different from 
those used at the start of the current cycle. The solutions are 
then self-consistent and accepted as solutions of the problem.
The outcomes of HF-SCF calculations are radial distribu­
tion functions that show the grouping of electron density into 
shells, as the building-up principle suggests. These calcula­
tions therefore support the qualitative discussions that are 
used to explain chemical periodicity. They also extend that 
discussion considerably by providing detailed wavefunctions 
and precise energies.
Table 8B.4  First and second ionization energies*
Element
I1/(kJ mol−1)
I2/(kJ mol−1)
H
1312
He
2372
5251
Mg
  738
1451
Na
  496
4562
* More values are given in the Resource section.
Table 8B.5  Electron affinities, Ea/(kJ mol−1)*
Cl
349
F
322
H
  73
O
141
O–
–844
* More values are given in the Resource section.
Checklist of concepts
☐	 1.	 In the orbital approximation, each electron is regarded 
as being described by its own wavefunction; the overall 
wavefunction of a many-electron atom is the product of 
the orbital wavefunctions.
☐	 2.	 The configuration of an atom is the statement of its 
occupied orbitals.
☐	 3.	 The Pauli exclusion principle, a special case of the 
Pauli principle, limits to two the number of electrons 
that can occupy a given orbital.
☐	 4.	 In many-electron atoms, s orbitals lie at a lower energy 
than p orbitals of the same shell due to the combined 
effects of penetration and shielding.


## Página 358

326 
8  Atomic structure and spectra
☐	 5.	 The building-up principle is a procedure for predicting 
the ground state electron configuration of an atom.
☐	 6.	 Electrons occupy different orbitals of a given subshell 
before doubly occupying any one of them.
☐	 7.	 An atom in its ground state adopts a configuration with 
the greatest number of unpaired electrons.
☐	 8.	 The atomic radius of an element is half the distance 
between the centres of neighbouring atoms in a solid 
or in a homonuclear molecule.
☐	 9.	 The ionic radius of an element is its share of the dis­
tance between neighbouring ions in an ionic solid.
☐	10.	 The first ionization energy is the minimum energy 
necessary to remove an electron from a many-electron 
atom in the gas phase.
☐	11.	 The second ionization energy is the minimum energy 
needed to remove an electron from a singly charged cation.
☐	12.	 The electron affinity is the energy released when an 
electron attaches to a gas-phase atom.
☐	13.	 The atomic radius, ionization energy, and electron 
affinity vary periodically through the periodic table.
☐	14.	 The Schrödinger equation for many-electron atoms is 
solved numerically and iteratively until the solutions 
are self-consistent.
Checklist of equations
Property
Equation
Comment
Equation number
Orbital approximation
Ψ(r1,r2, …) = ψ(r1)ψ(r2) …
8B.1
Effective nuclear charge
Zeff = Z − σ
The charge is this number times e
8B.5


## Página 359

TOPIC 8C  Atomic spectra
➤  Why do you need to know this material?
A knowledge of the energies of electrons in atoms is 
essential for understanding many chemical properties 
and chemical bonding.
➤  What is the key idea?
The frequency and wavenumber of radiation emitted or 
absorbed when atoms undergo electronic transitions pro­
vide detailed information about their electronic energy 
states.
➤  What do you need to know already?
This Topic draws on knowledge of the energy levels of 
hydrogenic atoms (Topic 8A) and the configurations of 
many-electron atoms (Topic 8B). In places, it uses the prop­
erties of angular momentum (Topic 7F).
not carry away enough angular momentum. Similarly, an s 
electron cannot make a transition to another s orbital, because 
there would then be no change in the angular momentum of 
the electron to make up for the angular momentum carried 
away by the photon. A more formal treatment of selection 
rules requires mathematical manipulation of the wavefunc­
tions for the initial and final states of the atom.
How is that done? 8C.1  Identifying selection rules
The underlying classical idea behind a spectroscopic transi­
tion is that, for an atom or molecule to be able to interact 
with the electromagnetic field and absorb or create a photon 
of frequency ν, it must possess, at least transiently, a dipole 
oscillating at that frequency. The consequences of this idea are 
explored in the following steps.
Step 1 Write an expression for the transition dipole moment
The transient dipole is expressed quantum mechanically as 
the transition dipole moment, μ fi, between the initial and 
final states i and f, where1
∫
µ
µ
ψ
ψ
τ
=
* ˆ
d
fi
f
i

(8C.1)
and ˆµ is the electric dipole moment operator. For a one-
electron atom µˆ is multiplication by −er. Because r is a vector 
with components x, y, and z, ˆµ is also a vector, with compo­
nents μx = −ex, μy = −ey, and μz = −ez. If the transition dipole 
moment is zero, then the transition is forbidden; the transi­
tion is allowed if the transition moment is non-zero.
Step 2 Formulate the integrand in terms of spherical harmonics
To evaluate a transition dipole moment, consider each com­
ponent in turn. For example, for the z-component,
∫
µ
ψ
ψ
τ
=−e
z
*
d
z,fi
f
i
In spherical polar coordinates (see The chemist’s toolkit 21 
in Topic 7F) z = r cos θ. Then, according to Table 7F.1, z =
rY
(4 /3)1/2
1,0
π
. The wavefunctions for the initial and final states 
are atomic orbitals of the form R
r Y
( )
( , )
n l
l m
,
,
l θ φ  (Topic 8A). 
With these substitutions the integral becomes
 


 




 


 




∫
∫
∫
∫
ψ
ψ
τ
θ θ φ
=
π




π
π
∞
z
R
Y
rY
R
Y
r
r
*
d
*
4
3
d sin d d
n l
l m
n l
l m
f
i
0
0
2
0
,
,
1/2
1,0
,
,
2
l
l
f
f
f
,f
i
i
i
,i
ψf*
ψi
dτ
z
The general idea behind atomic spectroscopy is straightfor­
ward: lines in the spectrum (in either emission or absorption) 
occur when the electron distribution in an atom undergoes a 
transition, a change of state, in which its energy changes by 
ΔE. This transition leads to the emission or is accompanied by 
absorption of a photon of frequency ν = |ΔE|/h and wavenum­
ber ν = |ΔE|/hc. In spectroscopy, transitions are said to take 
place between two terms. Broadly speaking, a term is simply 
another name for the energy level of an atom, but as this Topic 
progresses its full significance will become clear.
8C.1  The spectra of hydrogenic atoms
Not all transitions between the possible terms are observed. 
Spectroscopic transitions are allowed, if they can occur, or 
forbidden, if they cannot occur. A selection rule is a statement 
about which transitions are allowed.
The origin of selection rules can be identified by consider­
ing transitions in hydrogenic atoms. A photon has an intrinsic 
spin angular momentum corresponding to s = 1 (Topic 8B). 
Because total angular momentum is conserved in a transi­
tion, the angular momentum of the electron must change to 
compensate for the angular momentum carried away by the 
photon. Thus, an electron in a d orbital (l = 2) cannot make 
a transition into an s orbital (l = 0) because the photon can­
1 See our Physical chemistry: Quanta, matter, and change (2014) for a de­
tailed development of the form of eqn 8C.1.


## Página 360

328 
8  Atomic structure and spectra
This multiple integral is the product of three factors, an inte­
gral over r and two integrals (in blue) over the angles, so the 
factors on the right can be grouped as follows:
∫
∫
∫∫
ψ
ψ
τ
θ θ φ
=
π




∞
π
π
z
R
r R
r
Y
Y Y
*
d
4
3
d
*
sin d d
n l
n l
l m
l m
f
i
1/2
0
,
3
,
0
2
0
,
1,0
,
l
l
f
f
i
i
f
,f
i
,i
Step 3 Evaluate the angular integral
It follows from the properties of the spherical harmonics that 
the integral
∫∫
θ θ φ
=
π
π
I
Y
Y Y
*
sin d d
l m
l m
l m
0
0
2
,
,
,
l
l
f
,f
i
,i
is zero unless lf = li ± l and ml,f = ml,i + m. Because in the 
present case l = 1 and m = 0, the angular integral, and hence 
the z-component of the transition dipole moment, is zero 
unless Δl = ±1 and Δml = 0, which is a part of the set of selec­
tion rules. The same procedure, but considering the x- and 
y-components, results in the complete set of rules:
Δl = ±1  Δml = 0, ±1
Selection rules for 
hydrogenic atoms  
(8C.2)
The principal quantum number n can change by any amount 
consistent with the value of Δl for the transition, because it 
does not relate directly to the angular momentum.
Brief illustration 8C.1
To identify the orbitals to which a 4d electron may make 
radiative transitions, first identify the value of l and then 
apply the selection rule for this quantum number. Because l = 
2, the final orbital must have l = 1 or 3. Thus, an electron may 
make a transition from a 4d orbital to any np orbital (subject 
to Δml = 0, ±1) and to any nf orbital (subject to the same rule). 
However, it cannot undergo a transition to any other orbital, 
such as an ns or an nd orbital.
The selection rules and the atomic energy levels jointly ac­
count for the structure of a Grotrian diagram (Fig. 8C.1), 
which summarizes the energies of the states and the transi­
tions between them. In some versions, the thicknesses of the 
transition lines in the diagram denote their relative intensities 
in the spectrum.
8C.2  The spectra of many-electron 
atoms
The spectra of atoms rapidly become very complicated as the 
number of electrons increases, in part because their energy 
levels, their terms, are not given solely by the energies of the 
orbitals but depend on the interactions between the electrons.
Lyman
102 824
97 492
82 259
s
p
d
s
p
d
Paschen
Balmer
15 328 (Hα)
20 571 (Hβ)
23 039 (Hγ)
24 380 (Hδ)
s
p
d
Figure 8C.1  A Grotrian diagram that summarizes the appearance 
and analysis of the spectrum of atomic hydrogen. The 
wavenumbers of some transitions (in cm−1) are indicated. The 
colours of the lines are for reference only: they are not the colours 
of the transitions.
(a)  Singlet and triplet terms
Consider the energy levels of a He atom, with its two electrons. 
The ground-state configuration is 1s2, and an excited configu­
ration is one in which an electron has been promoted into a 
different orbital to give, for instance, the configuration 1s12s1. 
The two electrons need not be paired because they occupy dif­
ferent orbitals. According to Hund’s maximum multiplicity 
rule (Topic 8B), the state of the atom with the spins parallel lies 
lower in energy than the state in which they are paired. Both 
states are permissible, correspond to different terms, and can 
contribute to the spectrum of the atom.
Parallel and antiparallel (paired) spins differ in their total 
spin angular momentum. In the paired case, the two spin mo­
menta cancel, and there is zero net spin (as depicted in Fig. 
8C.2(a)). Its state is the one denoted σ− in the discussion of the 
Pauli principle (Topic 8B):
σ
= 


α
β
−β
α
−(1,2)
1
2
{ (1) (2)
(1) (2)}
1/2

(8C.3a)
The angular momenta of two parallel spins add to give a non-
zero total spin. As illustrated in Fig. 8C.2(b), there are three 
ways of achieving non-zero total spin. The three spin states are 
the symmetric combinations introduced in Topic 8B:
α(1)α(2)
σ
= 


α
β
+β
α
+(1,2)
1
2
{ (1) (2)
(1) (2)}
1/2
 
(8C.3b)
β(1)β(2)
The state of the He atom in which the two electrons are paired 
and their spins are described by eqn 8C.3a gives rise to a sing­
let term. The alternative arrangement, in which the spins are 
parallel and are described by any of the three expressions in 
eqn 8C.3b, gives rise to a triplet term. The fact that the parallel 
