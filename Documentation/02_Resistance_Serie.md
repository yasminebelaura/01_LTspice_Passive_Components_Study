# Simulation 2 : Association de résistances en série avec LTspice

## Objectif

Cette deuxième simulation a pour objectif d'étudier le comportement d'une association de résistances en série et de vérifier expérimentalement les lois électriques associées.

Une association en série possède les propriétés suivantes :

- Le courant est identique dans tous les composants traversés.
- La tension totale se répartit entre les résistances.
- La résistance équivalente correspond à la somme des résistances.

La relation théorique de la résistance équivalente est :

$$
R_{eq}=R_1+R_2
$$

---

# 1. Description du circuit

Le circuit étudié est constitué de deux résistances montées en série alimentées par une source continue.

## Paramètres du circuit

| Composant | Valeur |
|---|---:|
| Source V1 | 5 V |
| Résistance R1 | 10 kΩ |
| Résistance R2 | 10 kΩ |

Schéma électrique :

```
          R1                 R2

 +5V ───/\/\/───────●────/\/\/──── GND
        10 kΩ       │     10 kΩ
                    │
                  Vout
```

Le point intermédiaire entre les deux résistances est nommé :

```
Vout
```

L'analyse utilisée dans LTspice est :

```
Operating Point (.op)
```

---

# 2. Calcul théorique

## 2.1 Résistance équivalente

Pour une association série :

$$
R_{eq}=R_1+R_2
$$

Application numérique :

```
Req = 10 kΩ + 10 kΩ
```

Donc :

```
Req = 20 kΩ
```

---

## 2.2 Calcul du courant total

La loi d'Ohm permet de déterminer le courant :

$$
I=\frac{U}{R_{eq}}
$$

Application :

```
I = 5 / 20000
```

Résultat :

```
I = 0,00025 A
```

Soit :

```
I = 0,25 mA
```

---

## 2.3 Répartition des tensions

La tension aux bornes de chaque résistance est :

$$
U_R=R \times I
$$

Pour R1 :

```
U_R1 = 10000 × 0,00025
```

```
U_R1 = 2,5 V
```

Pour R2 :

```
U_R2 = 10000 × 0,00025
```

```
U_R2 = 2,5 V
```

Vérification :

```
Utotal = UR1 + UR2

5 V = 2,5 V + 2,5 V
```

La loi des mailles est respectée.

---

# 3. Résultats de simulation LTspice

Résultat obtenu avec l'analyse Operating Point :

```
--- Operating Point ---

V(vout):  2.5 V
V(n001):  5 V

I(V1):  -0.00025 A

I(R2):   0.00025 A
I(R1):   0.00025 A
```

---

# 4. Détermination de la résistance équivalente

LTspice ne fournit pas directement la résistance équivalente d'une association de résistances.

Elle peut être déterminée à partir de la tension d'alimentation et du courant fourni par la source :

$$
R_{eq}=\frac{U}{I}
$$

Calcul à partir des résultats LTspice :

```
Req = 5 / 0,00025
```

Résultat :

```
Req = 20000 Ω
```

Soit :

```
Req = 20 kΩ
```

---

# 5. Comparaison théorie / simulation

| Grandeur | Théorie | LTspice |
|---|---:|---:|
| Résistance équivalente | 20 kΩ | 20 kΩ |
| Tension d'alimentation | 5 V | 5 V |
| Courant total | 0,25 mA | 0,25 mA |
| Courant dans R1 | 0,25 mA | 0,25 mA |
| Courant dans R2 | 0,25 mA | 0,25 mA |
| Tension Vout | 2,5 V | 2,5 V |

---

# 6. Analyse des résultats

Les résultats obtenus avec LTspice confirment le comportement théorique d'une association de résistances en série.

On vérifie que :

### Le courant est identique dans les résistances

$$
I_{R1}=I_{R2}
$$

Le courant traversant chaque résistance vaut :

```
I = 0,25 mA
```

---

### La résistance équivalente est la somme des résistances

$$
R_{eq}=R_1+R_2
$$

Résultat :

```
Req = 20 kΩ
```

---

### La tension se répartit entre les résistances

La tension totale :

```
5 V
```

se divise en :

```
UR1 = 2,5 V

UR2 = 2,5 V
```

Le point intermédiaire mesuré :

```
Vout = 2,5 V
```

correspond au potentiel situé entre les deux résistances.

---

# 7. Conclusion

Cette simulation valide expérimentalement les propriétés d'une association de résistances en série.

Les résultats LTspice correspondent aux calculs théoriques :

- La résistance équivalente est égale à la somme des résistances.
- Le courant est identique dans chaque résistance.
- La tension se répartit proportionnellement aux valeurs résistives.

Cette étude constitue une base essentielle pour comprendre les circuits électroniques, notamment les ponts diviseurs de tension et les circuits de polarisation.

La prochaine étude portera sur :

- Association de résistances en parallèle
- Pont diviseur de tension
- Puissance dissipée par une résistance