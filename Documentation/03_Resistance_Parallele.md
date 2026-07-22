# Simulation 3 : Association de résistances en parallèle avec LTspice

## Objectif

Cette troisième simulation a pour objectif d'étudier le comportement d'une association de résistances en parallèle et de vérifier expérimentalement les lois électriques associées.

Une association de résistances en parallèle possède les propriétés suivantes :

- La tension est identique aux bornes de chaque branche.
- Le courant total fourni par la source se répartit entre les différentes branches.
- La résistance équivalente est inférieure à la plus petite résistance du montage.

La relation théorique de la résistance équivalente est :

$$
\frac{1}{R_{eq}}=\frac{1}{R_1}+\frac{1}{R_2}
$$

Pour deux résistances :

$$
R_{eq}=\frac{R_1 \times R_2}{R_1+R_2}
$$

---

# 1. Description du circuit

Le circuit étudié est constitué de deux résistances montées en parallèle alimentées par une source continue.

## Paramètres du circuit

| Composant | Valeur |
|---|---:|
| Source V1 | 5 V |
| Résistance R1 | 10 kΩ |
| Résistance R2 | 10 kΩ |

Schéma électrique :

```
              R1
        ┌────/\/\/────┐
        │   10 kΩ     │
        │             │
 +5 V ──●             ●── GND
        │             │
        │   10 kΩ     │
        └────/\/\/────┘
              R2

          Vparallel = 5 V
```

Le nœud de mesure de tension est nommé :

```
Vparallel
```

L'analyse utilisée dans LTspice est :

```
Operating Point (.op)
```

---

# 2. Calcul théorique

## 2.1 Résistance équivalente

Pour deux résistances en parallèle :

$$
R_{eq}=\frac{R_1 \times R_2}{R_1+R_2}
$$

Application numérique :

```
Req = (10000 × 10000) / (10000 + 10000)
```

Résultat :

```
Req = 5000 Ω
```

Donc :

```
Req = 5 kΩ
```

---

## 2.2 Calcul du courant dans chaque branche

La tension étant identique dans chaque branche :

$$
U_{R1}=U_{R2}=5V
$$

Avec la loi d'Ohm :

$$
I=\frac{U}{R}
$$

Pour R1 :

```
I(R1)=5 / 10000
```

Résultat :

```
I(R1)=0,0005 A
```

Soit :

```
I(R1)=0,5 mA
```

Pour R2 :

```
I(R2)=5 / 10000
```

Résultat :

```
I(R2)=0,0005 A
```

Soit :

```
I(R2)=0,5 mA
```

---

## 2.3 Calcul du courant total

Dans une association parallèle :

$$
I_{total}=I_1+I_2
$$

Donc :

```
Itotal = 0,5 mA + 0,5 mA
```

Résultat :

```
Itotal = 1 mA
```

---

# 3. Résultats de simulation LTspice

Résultat obtenu avec l'analyse Operating Point :

```
--- Operating Point ---

V(n001):       0 V
V(vparallel): 5 V

I(V1):        -0,001 A

I(R2):         0,0005 A
I(R1):         0,0005 A
```

---

# 4. Détermination de la résistance équivalente depuis LTspice

LTspice ne donne pas directement la résistance équivalente d'une association.

Elle est calculée à partir de la tension d'alimentation et du courant total fourni par la source :

$$
R_{eq}=\frac{U}{I}
$$

Avec les résultats LTspice :

```
U = 5 V
I = 0,001 A
```

Calcul :

```
Req = 5 / 0,001
```

Résultat :

```
Req = 5000 Ω
```

Soit :

```
Req = 5 kΩ
```

---

# 5. Comparaison théorie / simulation

| Grandeur | Théorie | LTspice |
|---|---:|---:|
| Résistance équivalente | 5 kΩ | 5 kΩ |
| Tension du montage | 5 V | 5 V |
| Tension Vparallel | 5 V | 5 V |
| Courant total | 1 mA | 1 mA |
| Courant dans R1 | 0,5 mA | 0,5 mA |
| Courant dans R2 | 0,5 mA | 0,5 mA |

---

# 6. Analyse des résultats

Les résultats obtenus avec LTspice confirment le comportement théorique d'une association de résistances en parallèle.

On observe que :

## La tension est identique dans chaque branche

\[
U_{R1}=U_{R2}=U_{total}
\]

Chaque résistance reçoit :

```
5 V
```

---

## Le courant se répartit entre les branches

Le courant total fourni par la source est :

```
Itotal = 1 mA
```

Il est réparti dans les deux résistances :

```
I(R1)=0,5 mA

I(R2)=0,5 mA
```

Ainsi :

\[
I_{total}=I_1+I_2
\]

---

## La résistance équivalente diminue

Deux résistances de 10 kΩ en parallèle donnent :

```
Req = 5 kΩ
```

La résistance équivalente est donc plus faible qu'une résistance seule.

---

# 7. Conclusion

Cette simulation valide expérimentalement les propriétés d'une association de résistances en parallèle.

Les résultats LTspice correspondent aux calculs théoriques :

- La tension est identique aux bornes de chaque résistance.
- Le courant total se divise entre les différentes branches.
- La résistance équivalente diminue lorsque plusieurs résistances sont associées en parallèle.

Cette étude complète l'analyse des associations résistives après l'étude des résistances en série.

La prochaine étape portera sur :

- Le pont diviseur de tension
- La puissance dissipée par une résistance
- Les applications pratiques des réseaux résistifs