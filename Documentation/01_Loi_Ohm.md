# Simulation 1 : Vérification de la loi d'Ohm avec LTspice

## Objectif

Cette première simulation a pour objectif de vérifier expérimentalement la loi d'Ohm à l'aide du logiciel **LTspice**.

La loi d'Ohm établit la relation entre la tension appliquée aux bornes d'une résistance, le courant qui la traverse et sa valeur résistive :

$$
I = \frac{U}{R}
$$

Avec :

- **U** : tension aux bornes de la résistance (Volt)
- **I** : courant traversant la résistance (Ampère)
- **R** : valeur de la résistance (Ohm)

Cette étude permet également de comprendre l'influence de la valeur de la résistance sur le courant circulant dans un circuit.

---

# 1. Description du circuit

Deux circuits résistifs indépendants ont été simulés afin de comparer l'influence de la résistance sur le courant.

Les conditions de simulation sont :

- Source continue : **5 V**
- Analyse LTspice : **Operating Point (.op)**

---

## Circuit 1 : Résistance de 1 kΩ

Paramètres :

- Tension appliquée :

```
U = 5 V
```

- Résistance :

```
R1 = 1 kΩ
```

Schéma LTspice :

*(Ajouter ici la capture du schéma)*

---

## Circuit 2 : Résistance de 10 kΩ

Paramètres :

- Tension appliquée :

```
U = 5 V
```

- Résistance :

```
R2 = 10 kΩ
```

Schéma LTspice :

*(Ajouter ici la capture du schéma)*

---

# 2. Calculs théoriques

## Cas 1 : Résistance R1 = 1 kΩ

Application de la loi d'Ohm :

$$
I = \frac{U}{R}
$$

Calcul :

```
I = 5 / 1000
```

Résultat :

```
I = 0,005 A
```

Soit :

```
I = 5 mA
```

---

## Cas 2 : Résistance R2 = 10 kΩ

Calcul :

```
I = 5 / 10000
```

Résultat :

```
I = 0,0005 A
```

Soit :

```
I = 0,5 mA
```

---

# 3. Résultats de simulation LTspice

Les résultats obtenus avec LTspice sont :

## Circuit 1 : R1 = 1 kΩ

Résultat Operating Point :

```
V(n001) = 5 V

I(R1) = 0.005 A
```

Soit :

```
I(R1) = 5 mA
```

---

## Circuit 2 : R2 = 10 kΩ

Résultat Operating Point :

```
V(n002) = 5 V

I(R2) = 0.0005 A
```

Soit :

```
I(R2) = 0,5 mA
```

---

# 4. Comparaison théorie / simulation

| Circuit | Tension | Résistance | Courant théorique | Courant LTspice |
|---|---|---|---|---|
| Circuit 1 | 5 V | 1 kΩ | 5 mA | 5 mA |
| Circuit 2 | 5 V | 10 kΩ | 0,5 mA | 0,5 mA |

---

# 5. Analyse des résultats

Les résultats obtenus avec LTspice correspondent aux calculs théoriques.

Pour une tension constante de 5 V :

- Une faible résistance permet le passage d'un courant plus important.
- Une résistance élevée limite davantage le courant.

On observe donc :

$$
R \uparrow \Rightarrow I \downarrow
$$

Dans cette étude :

- La résistance de 10 kΩ est 10 fois plus grande que celle de 1 kΩ.
- Le courant obtenu est donc 10 fois plus faible.

Cette simulation met en évidence le rôle fondamental de la résistance dans la limitation du courant électrique.

---

# 6. Conclusion

Cette première simulation valide expérimentalement la loi d'Ohm :

$$
I = \frac{U}{R}
$$

Les résultats obtenus avec LTspice sont conformes aux valeurs calculées théoriquement.

Cette étude constitue une première étape dans l'analyse des composants passifs et permet de comprendre le comportement d'une résistance dans un circuit électronique.

Les prochaines simulations porteront sur :

- Association de résistances en série et en parallèle
- Pont diviseur de tension
- Puissance dissipée par une résistance
- Étude du condensateur
- Étude de l'inductance
