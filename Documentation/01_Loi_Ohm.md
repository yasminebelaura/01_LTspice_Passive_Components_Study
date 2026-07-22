\# Simulation 1 : Vérification de la loi d'Ohm avec LTspice



\## Objectif



Cette première simulation a pour objectif de vérifier expérimentalement la loi d'Ohm à l'aide du logiciel LTspice.



La loi d'Ohm établit la relation entre la tension appliquée aux bornes d'un dipôle résistif, le courant qui le traverse et sa résistance :



\\\[

I = \\frac{U}{R}

\\]



avec :



\- \*\*U\*\* : tension aux bornes de la résistance (V)

\- \*\*I\*\* : courant traversant la résistance (A)

\- \*\*R\*\* : valeur de la résistance (Ω)



Cette étude permet également d'observer l'influence de la valeur de la résistance sur le courant consommé par un circuit.



\---



\# 1. Description du circuit



Deux circuits résistifs indépendants ont été simulés.



\## Circuit 1 : Résistance de 1 kΩ



Paramètres :



\- Source continue : \*\*U = 5 V\*\*

\- Résistance : \*\*R1 = 1 kΩ\*\*



Schéma :



\*(Insérer ici la capture du schéma LTspice)\*



\---



\## Circuit 2 : Résistance de 10 kΩ



Paramètres :



\- Source continue : \*\*U = 5 V\*\*

\- Résistance : \*\*R2 = 10 kΩ\*\*



Schéma :



\*(Insérer ici la capture du schéma LTspice)\*



\---



\# 2. Calculs théoriques



\## Cas 1 : R = 1 kΩ



D'après la loi d'Ohm :



\\\[

I = \\frac{U}{R}

\\]



Application numérique :



\\\[

I = \\frac{5}{1000}

\\]



\\\[

I = 0,005A

\\]



Soit :



\\\[

\\boxed{I = 5mA}

\\]



\---



\## Cas 2 : R = 10 kΩ



\\\[

I = \\frac{5}{10000}

\\]



\\\[

I = 0,0005A

\\]



Soit :



\\\[

\\boxed{I = 0,5mA}

\\]



\---



\# 3. Résultats de simulation LTspice



Les résultats obtenus avec l'analyse \*\*Operating Point (.op)\*\* sont :



\### Circuit 1 : R = 1 kΩ



Soit :



\\\[

I(R1)=5mA

\\]



\---



\### Circuit 2 : R = 10 kΩ



Soit :



\\\[

I(R2)=0,5mA

\\]



\---



\# 4. Comparaison théorie / simulation



| Circuit | Tension appliquée | Résistance | Courant théorique | Courant LTspice |

|---|---:|---:|---:|---:|

| 1 | 5 V | 1 kΩ | 5 mA | 5 mA |

| 2 | 5 V | 10 kΩ | 0,5 mA | 0,5 mA |



\---



\# 5. Analyse des résultats



Les résultats obtenus avec LTspice sont conformes aux calculs théoriques.



Pour une tension constante de \*\*5 V\*\*, on observe que :



\- Lorsque la résistance diminue, le courant augmente.

\- Lorsque la résistance augmente, le courant diminue.



Dans ce cas :



\\\[

R\_2 = 10 \\times R\_1

\\]



donc :



\\\[

I\_2 = \\frac{I\_1}{10}

\\]



Le courant traversant la résistance de \*\*10 kΩ\*\* est donc dix fois plus faible que celui traversant la résistance de \*\*1 kΩ\*\*.



Cette simulation met en évidence le rôle fondamental de la résistance dans la limitation du courant électrique.



\---



\# 6. Conclusion



Cette première simulation valide expérimentalement la loi d'Ohm :



\\\[

I=\\frac{U}{R}

\\]



Les résultats LTspice correspondent aux valeurs calculées théoriquement.



Cette étude constitue une première étape dans l'analyse des composants passifs et permet de comprendre le comportement d'une résistance dans un circuit électronique.



Les prochaines simulations porteront sur :

\- l'association de résistances (série et parallèle),

\- le pont diviseur de tension,

\- la puissance dissipée par une résistance,

\- puis l'étude des autres composants passifs : condensateur et inductance.

