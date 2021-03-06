---
title: Zweite Quantifizierung
description: Erfahren Sie mehr über den zweiten quantifisierungsansatz zum Modellieren elektronischer Strukturen in der Quantum-Programmierung.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.secondquantization
no-loc:
- Q#
- $$v
ms.openlocfilehash: a08e20d5b53aa97cb12ead0dc3a36069d0ec5df8
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858836"
---
# <a name="second-quantization"></a>Zweite Quantifizierung

Die zweite Quantifizierung untersucht das Problem der elektronischen Struktur durch einen anderen.
Anstatt die einzelnen $N _E $-Elektronen einem bestimmten Zustand (oder einer beliebigen Orbital) zuzuweisen, verfolgt die zweite Quantifizierung jede Zwischenspeicherung nach und speichert, ob ein-oder ein-metadatenpaar vorhanden ist, und stellt gleichzeitig automatisch die symmetrischen Eigenschaften der entsprechenden Wave-Funktion sicher.
Dies ist wichtig, da die Verwendung von Quantum-Chemie Modellen möglich ist, ohne sich Gedanken über die antisymmetrierung des Eingabe Zustands machen zu müssen (wie dies für Fermionen erforderlich ist), und dass die zweite Quantifizierung ermöglicht, dass solche Modelle mit kleinen Quantum-Computern simuliert werden.

Als Beispiel für die zweite Quantifizierung in Aktion gehen wir davon aus, dass $ \ psi_0 \cdots \ psi_ {N-1} $ ein orthonormale Satz räumlicher Orbit ist.
Diese Orbitals stellen fest, dass das System so genau wie möglich innerhalb des festgelegten begrenzten Basis Satzes dargestellt wird.
Ein gängiges Beispiel für solche Orbitals sind atomarische Orbitals, die eine eigenständige Basis für das Atom-Atom bilden.
Da mit zwei Dreh Zuständen zwei Elektronen vorhanden sind, können zwei Elektronen in jeder solchen räumlichen zwischen Raum angezeigt werden.
Das heißt, die gültigen Basiszustände weisen die Form "$ \ psi_ {0, \uanrow}" auf. \ldots, \ psi_ {N-1, \uparamerow}, \ psi_ {0, \downarrow}, \ldots, \ psi_ {N-1, \downarrow} $ WHERE $ \ubirow $ und $ \downpfeil $ sind Bezeichnungen, die die beiden eigen Zustände des Drehungs Freiheits Grads angeben.
Dieser kombinierte Index von $ (j, \sigma) $ für $ \sigma \in \{ \ubirow, \downpfeil \} $ wird als Spin-Orbital bezeichnet, da sowohl der räumliche als auch der Drehungs Grad der Freiheit gespeichert werden.
In der Chemie Bibliothek werden Spin-Orbitals in einer `SpinOrbital` Datenstruktur gespeichert und wie folgt erstellt.

```csharp
    // First, we load the namespace containing spin-orbital objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // First, we assign an orbital index, say `5`. Note that we use 0-indexing,
    // so this is the 6th orbital.
    var orbitalIdx = 5;

    // Second, we assign a spin index, say `Spin.u` for spin up or `Spin.d` for spin down.
    var spin = Spin.d;

    // the spin-orbital (5, ↓) is then
    var spinOrbital = new SpinOrbital(orbitalIdx, spin);

    // A tuple `(int, Spin)` is also implicitly recognized as a spin-orbital.
    (int, Spin) tuple = (orbitalIdx, spin);

    // We explicitly specify the type of `spinOrbital1` to demonstrate
    // the implicit cast to `SpinOrbital`.
    SpinOrbital spinOrbital1 = tuple;
```

Dies bedeutet, dass wir formal die Basis für die Drehung und den räumlichen Teil der Wave-Funktion als $ \ psi_ {0} \cdots \ psi_ {2n-1} $ vorstellen können, wobei jeder der Indizes jetzt eine Enumeration von $ (j, \sigma) $ ist.
Eine mögliche Enumeration ist $g (j, \sigma) = j + n\sigma ' $.
Eine weitere mögliche Enumeration ist $h (j, \sigma) = 2 * j + \sigma $.
Die Quantum-Chemie Bibliothek kann diese Konventionen verwenden, und die Spin-Orbitals in einer solchen Codierung können wie folgt instanziiert werden.

```csharp
    // Let us use the spin orbital created in the previous snippet.
   var spinOrbital = new SpinOrbital(5, Spin.d);

   // Let us set the total number of orbitals to be say, `7`.
   var nOrbitals = 7;

    // This converts a spin-orbital index to a unique integer, in this case `12`,
    // using the formula `g(j,σ)`.
    var integerIndexHalfUp = spinOrbital.ToInt(IndexConvention.HalfUp);

    // This converts a spin-orbital index to a unique integer, in this case `11`,
    // using the formula `h(j,σ)`.
    var integerIndexUpDown = spinOrbital.ToInt(IndexConvention.UpDown);

    // The default conversion uses the formula `h(j,σ)`, in this case `11`.
    var integerIndexDefault = spinOrbital.ToInt();
```

Bei fermionic Systems verhindert das Ausschlussprinzip von Pauli, dass mehrere Elektronen gleichzeitig in einer beliebigen Spin-Orbital vorhanden sind.
Dies bedeutet, dass wir die zwei rechtlichen Zustände für "$ \ psi_1 $" in "\begin{Equation} \ psi_1 \rightarrow \begin{Cases} \ket {0} _1 & \text{}" schreiben können, wenn "$ \ psi_1 $" nicht belegt ist,} \\\
\ket {1} _1 & \text{if $ \ psi_1 $ ist belegt.} \end{Cases} \end{Equation} diese Codierung eignet sich hervorragend für Quantum-Computer, da dies bedeutet, dass wir den elektronischen Beruf als einzelnes Quantum-Bit speichern können.

Die Berufs Zustände für die $2N $ Spin-Orbitals können auf ähnliche Weise in $2N $ Qubits gespeichert werden.
Beispiel: Wenn $N = $2, dann lautet der Status $ $ \ket {0} \ket {1} \ket {1} \ket {0} , $ $

entspricht den Dreh Orbitals $1 $ und $2 $, die mit dem Restwert "Empty" belegt werden.
Ebenso lautet der Status "$ $ \ket {0} \equiv \ket {0} _{0} \cdots \ket {0}_{N-1}", "$ $".

hat keine Elektronen und wird als "Vakuumzustand" bezeichnet.

Ein schöner Nebeneffekt der zweiten Quantifizierung besteht darin, dass die Antisymmetrie des Quantum-Zustands nicht mehr explizit verfolgt werden muss.
Der Grund hierfür ist, dass die Antisymmetrie des Zustands selbst durch die Anti-komtypregeln der Operatoren, die elektronische Berufe einer Spin-Orbital erstellen und zerstören, repräsentiert.

## <a name="fermionic-operators"></a>Fermionic-Operatoren

Die beiden grundlegenden Operatoren, die auf die zweiten quantifizierten Basis-Vektoren reagieren, werden als Erstellungs-und Vernichtungs Operatoren bezeichnet.
Diese Operatoren fügen Elektronen an einer bestimmten Position ein oder zerstören diese.
Diese werden $a ^ \ dagger_j $ und $a _J $ bezeichnet.

Beispiel: \begin{align} a ^ \ dagger_1 \ket {0} _1 = \ket {1} _1, \quad a ^ \ dagger_1 \ket {1} _1 = 0, \quad A_1 \ket {0} _1 = 0, \quad A_1 \ket {1} _1 = \ket {0} _1.
\end{align} beachten Sie, dass hier $a ^ \ dagger_1 \ket {1} _1 = 0 $ und $a _1 \ket {0} _1 $ den NULL-Vektor nicht $ \ket {0} _1 $ ergibt.
Diese Operatoren sind daher weder hermitian noch einheitlich.
Wir stellen allgemeine Erstellungs-und Vernichtungs Operatoren mithilfe des- <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderOperator`1> Typs dar.
Beispielsweise wird ein einzelner Erstellungs Operator wie folgt dargestellt.

```csharp
    // We load the namespace containing ladder operator objects.
    using Microsoft.Quantum.Chemistry.LadderOperators;

    // Let us use the spin orbital created in the previous snippet.
    var spinOrbitalInteger = new SpinOrbital(5, Spin.d).ToInt();

    // We specify either a creation or annihilation operator using 
    // the enumerable type `RaisingLowering.u` or `RaisingLowering.d`
    // respectively;
    var creationEnum = RaisingLowering.u;

    // The type representing a creation operator is then initialized 
    // as follows. Here, we index these operators with integers.
    // Hence we initialize the generic ladder operator with an
    // integer index type.
    var ladderOperator0 = new LadderOperator<int>(creationEnum, spinOrbitalInteger);

    // An alternate constructor for a LadderOperator instead uses
    // a tuple.
    var ladderOperator1 = new LadderOperator<int>((creationEnum, spinOrbitalInteger));
```

Mit diesen Operatoren können wir auch $ $ \ket {0} \ket {1} \ket {1} \ket {0} = a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} ^ {\otimes 4} Ausdrücken.
$ $ Diese Sequenz von Operatoren wird in der hamiltona-Simulations Bibliothek mit c#-Code erstellt, der mit dem im obigen Beispiel beschriebenen Single-Spin-Orbital Fall vergleichbar ist:
```csharp
    // We load the namespace containing fermion-related objects.
    using Microsoft.Quantum.Chemistry.Fermion;

    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We can convert this array of tuples to a sequence of ladder
    // operators using the `ToLadderSequence()` methods.
    var ladderSequences = indices.ToLadderSequence();

    // Sequences of ladder operators are quite general. For instance,
    // they could be bosonic operators, instead of fermionic operators.
    // We specialize them by constructing a `FermionTerm` representing 
    // a fermion creation operator on the index `2` followed by `1`.
    var fermionTerm = new FermionTerm(ladderSequences);
```

Bei einem System von $k $ Fermions wird bei der zweiten Quantisierung die Aktion des Erstellungs Operators $a ^ \ dagger_i $ durch $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 0_i, \ldots, n_k} = (-1) ^ {S_i} \ket{n_1, n_2, \ldots, 1_I, angegeben. \ldots, n_k}, $ $ und $ $ a ^ \ dagger_i \ket{n_1, n_2, \ldots, 1_I, \ldots, n_k} = 0, $ $ WHERE $S _I = \ sum_ {j<i} a ^ \ dagger_j a_j $ misst die Gesamtzahl der Fermions im Zustand eines einzelnen Partikels, die über einen Index $j < i $ verfügen.

Ein Dritter Operator wird häufig auch in zweiten quantifizierten Darstellungen verwendet.
Dieser Operator wird als Zahlen Operator bezeichnet und durch \begin{Equation} n_i = a ^ \ dagger_i a_i definiert.
\end{Equation} dieser Operator zählt die Besetzung eines bestimmten Drehfelds, d. h. "\begin{align} n_i \ket {0} _I &= 0 \ nicht Zuber".\\\
n_i \ket {1} _I &= \ket {1} _i.
\end{align} wie in den obigen `FermionTerm` Beispielen, wird dieser Zahlen Operator wie folgt konstruiert.
```csharp
    // Let us use a new method to compactly create a sequence of ladder
    // operators. Note that we have omitted specifying whether the 
    // operators are raising or lowering. In this case, the first half
    // will be raising operators, and the second half will be lowering 
    // operators.
    var indices = new[] { 1, 1 }.ToLadderSequence();

    // We now construct a `FermionTerm` representing an annihilation operator
    // on the index 1 followed by the creation operator on the index 1.
    var fermionTerm0 = new FermionTerm(indices);
```

Bei der Verwendung von Erstellungs-oder Vernichtungs Operatoren in fermionic-Systemen tritt jedoch eine Feinheit auf.
Wir verlangen, dass ein beliebiger gültiger Quantum-Zustand unter dem Austausch von Bezeichnungen antisymmetrisch ist.
Dies bedeutet, dass $ $ a ^ \ dagger_2 a ^ \ dagger_1 \ket {0} =-a ^ \ dagger_1 a ^ \ dagger_2 \ket {0} .
$ $ Solche Operatoren werden als "Anti-pendeln" und im Allgemeinen für alle $i bezeichnet. j $ wir haben diese \begin{align} a ^ \ dagger_i a ^ \ dagger_j =-(1-\ delta_ {i, j}) a ^ \ dagger_j a ^ \ dagger_i, \quad a ^ \ dagger_i a_j = \ delta_ {i, j}-a_j a ^ \ dagger_i.
\end{align} folglich werden die folgenden beiden <xref:Microsoft.Quantum.Chemistry.LadderOperators.LadderSequence`1> Instanzen als nicht äquivalent betrachtet.
```csharp
    // Let us initialize an array of tuples representing the
    // desired sequence of creation operators.
    var indices = new[] { (RaisingLowering.u, 1), (RaisingLowering.u, 2) };

    // We now construct a `LadderSequence` representing a creation operator
    // on the index 1 followed by 2, then a term with the reverse ordering.
    var laddderSeqeunce = indices.ToLadderSequence();
    var laddderSeqeunceReversed = indices.Reverse().ToLadderSequence();

    // The following Boolean is `false`.
    var equal = laddderSeqeunce == laddderSeqeunceReversed;
```

Durch die Verwendung einer zweiten quantifizierten Darstellung werden die Anforderungen der Antisymmetrie von Fermionen durch die Verwendung einer zweiten quantifizierten Darstellung vermieden.
Stattdessen wird die Herausforderung in unserer Definition der Erstellungs Operatoren wieder auftauchen. 

Bei Verwendung der Anti-Pendel Regeln entsprechen einige `LadderSequence` Instanzen tatsächlich derselben Sequenz von fermionic-Operatoren, manchmal bis zu einem Minuszeichen.
Sehen Sie sich beispielsweise den hamiltonan $a _0 ^ \dagger A_1 ^ \dagger A_1 a_0 =-A_1 ^ \dagger a_0 ^ \dagger A_1 a_0 $.
Dies motiviert uns, eine kanonische Reihenfolge für jeden zu definieren `FermionTerm` .
Alle werden `FermionTerm` automatisch wie folgt in kanonische Reihenfolge eingefügt.
```csharp
    // We now construct two `FermionTerms` that are equivalent with respect to
    // anti-commutation up to a sign change.
    var fermionTerm0 = new FermionTerm(new[] { 0, 1, 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 1, 0, 1, 0 }.ToLadderSequence());

    // The following Boolean is `true`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // The change in sign is not compared above, but is an internally tracked
    // property of `FermionTerm`.
    int sign0 = fermionTerm0.Coefficient;
    var sign1 = fermionTerm1.Coefficient;

    // The following Boolean is `false`.
    var signEqual = sign0 == sign1;
```

## <a name="second-quantized-fermionic-hamiltonian"></a>Second-Quantized fermionic hamiltonan

Vielleicht ist es nicht verwunderlich, dass die hamiltonan in [Quantum-Modellen für elektronische Systeme](xref:microsoft.quantum.chemistry.concepts.quantummodels) in Form von Erstellungs-und Vernichtungs Operatoren geschrieben werden kann.
Insbesondere, wenn "$ \psi \_ j $" die Dreh-und Ausgangs Typen sind, die die Grundlage bilden,

\begin{Equation} \hat{h} = \sum \_ {PQ} H \_ {PQ} a ^ \dagger \_ p a \_ q + \frac {1} {2} \sum \_ {pqrs} h \_ {pqrs} a ^ \dagger \_ p a ^ \dagger \_ q a \_ RA \_ s + H \_ {\textrm NUC}, \label{EQ: totalham} \end{Equation}, wobei $h \_ {\textrm NUC} $ die atomare Energie (eine Konstante unter der Born-Oppenheimer Näherung) und

\begin{align} h \_ {PQ} &= \int \_ {-\infty} ^ \infty \psi ^ \* \_ p (x \_ 1) \left (-\bruchteil {\nabla ^ 2} {2} + V (x \_ 1) \right) \psi \_ q (x \_ 1) \mathrm{d} ^ 3X \_ 1, \end{align}

Dabei ist $V (x) $ das Mittelfeld Potenzial und

\begin{align} h \_ {pqrs} &= \int \_ {-\infty} ^ \infty \int \_ {-\infty} ^ \infty\psi \_ p ^ \* (x \_ 1) \psi \_ q ^ \* (x \_ 2) \left (\frac {1} {| x_1-x_2 |} \right) \psi \_ r (x \_ 2) \psi \_ s (x \_ 1) \mathrm{d} ^ 3X \_ 1 \ mathrm {d} ^ 3X \_ 2. \ Bezeichnung {EQ: Integrals} \end{align}

Die Begriffe $h \_ {PQ} $ werden als One-Electron-integrale bezeichnet, da all diese Begriffe nur einzelne Elektronen einschließen und $h \_ {pqrs} $ die zwei-Elektronen-integleich sind.
Sie werden als integrale bezeichnet, da das Berechnen der Werte dieser Koeffizienten einen integralen Wert erfordert.
Die einzelnen Elektronen Begriffe beschreiben die kinetische Energie der einzelnen Elektronen und ihre Interaktionen mit den elektrischen Feldern der Kerne.
Die zwei-Elektronen-inteder auf der anderen Seite beschreiben die Interaktionen zwischen den Elektronen.

Eine Intuition für das, was diese Begriffe bedeuten, kann von den Erstellungs-und Vernichtungs Operatoren abgeleitet werden, die die einzelnen Komponenten bilden.
Beispielsweise beschreibt $h _ {PQ} a ^ \ dagger_p a_q $ den aus Spin-Orbital $q $ zum Spin-Orbital $p $.
Ebenso beschreibt der Begriff $h _ {pqrs} a ^ \ dagger_p a ^ \ dagger_q a_r a_s $ (für unterschiedliche $p, q, r, s $) zwei Elektronen in Drehungs-und $r $-und-$s $-Gliederung voneinander und endet in Drehungs-Orbitals $p $ und $q $.
Wenn $r = q $ und $p = s $, gibt $h _ {prrp} a ^ \ dagger_p a ^ \ dagger_r a_r a_p = H_ {prrp} n_p n_r $ den Energieverlust aus, der den beiden einander naheliegenden Elektronen zugeordnet ist, aber keinen dynamischen Prozess beschreibt.

Mit der- `FermionHamiltonian` Klasse, bei der es sich um eine Liste mit allen gewünschten Instanzen handelt, kann es sich um eine solche hamiltones handeln `FermionTerm` .
Da hamiltonane in der Definition "hermitian" sind, indizieren wir Begriffe mit dem spezielleren Typ, der `HermitianFermionTerm` auch hermitian Symmetrie verwendet, wenn überprüft wird, ob Begriffe äquivalent sind.

Lassen Sie uns einige anschauliche Beispiele erstellen.
Beachten Sie die hamiltonan $ \hat{h} = a_0 ^ \dagger A_1 + A_1 ^ \dagger a_0 $.
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the terms to be added.
    var fermionTerm0 = new FermionTerm(new[] { 1, 0 }.ToLadderSequence());
    var fermionTerm1 = new FermionTerm(new[] { 0, 1 }.ToLadderSequence());

    // These fermion terms are not equal. The following Boolean is `false`.
    var sequenceEqual = fermionTerm0 == fermionTerm1;

    // However, these terms are equal under Hermitian symmetry.
    // We also take the opportunity to demonstrate equivalent constructors
    // for hermitian fermion terms
    var hermitianFermionTerm0 = new HermitianFermionTerm(fermionTerm0);
    var hermitianFermionTerm1 = new HermitianFermionTerm(new[] { 0, 1 });

    // These Hermitian fermion terms are equal. The following Boolean is `true`.
    var hermitianSequenceEqual = hermitianFermionTerm0 == hermitianFermionTerm1;

    // We add the terms to the Hamiltonian with the appropriate coefficient.
    // Note that these terms are identical.
    hamiltonian.Add(hermitianFermionTerm0, 1.0);
    hamiltonian.Add(hermitianFermionTerm1, 1.0);
```
Wir können diese Konstruktion mit der Tatsache vereinfachen, dass hamiltonan-Operatoren hermitian-Operatoren sind.
Beim Hinzufügen von Begriffen zu "hamiltona" mit `Add` wird davon ausgegangen, dass jeder nicht hermitische Begriff, wie z `fermionTerm0` . b., mit seinem hermitian-konjugitor gekoppelt wird.
Der folgende Code Ausschnitt stellt daher auch dieselbe hamiltonan dar:
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We construct the term to be added -- note the doubled coefficient.
    hamiltonian.Add(new HermitianFermionTerm(new[] { 1, 0 }), 2.0);
```

Bei der Verwendung der Anti--typzustellungs Regeln `FermionTerm` entsprechen einige Instanzen in der hamiltona tatsächlich derselben Sequenz von fermionic-Operatoren, manchmal bis zu einem Minuszeichen.
Nehmen Sie zum Beispiel den hamiltonan $H = a_0 ^ \dagger A_1 ^ \dagger A_1 a_0-A_1 ^ \dagger a_0 ^ \dagger A_1 a_0 = 2a_0 ^ \dagger A_1 ^ \dagger A_1 a_0 $. Dies ist eine Summe der oben erstellten Begriffe.
Es ist für den Benutzer möglicherweise nicht immer klar, dass es sich um äquivalente Begriffe handelt, und daher können Sie der hamiltona separat hinzugefügt werden.
Alternativ kann eine Änderung bereits vorhandener Begriffe in der hamiltonan sinnvoll sein.
In diesen Fällen können wir äquivalente Begriffe wie folgt kombinieren.
```csharp
    // We create a `FermionHamiltonian` instance to store the fermion terms.
    var hamiltonian = new FermionHamiltonian();

    // We now create two Hermitian fermion terms that are equivalent with respect to
    // anti-commutation and Hermitian symmetry.
    var terms = new[] {
        (new[] { 0, 1, 1, 0 }, 1.0),
        (new[] { 1, 0, 1, 0 }, 1.0) }
    .Select(o => (new HermitianFermionTerm(o.Item1.ToLadderSequence()), o.Item2.ToDoubleCoeff()));

    // Now add `terms` to the Hamiltonian.
    hamiltonian.AddRange(terms);

    // There is only one unique term. `nTerms == 1` is `true`.
    var nTerms = hamiltonian.CountTerms();
```
Durch die Kombination von Koeffizienten der äquivalenten Begriffe verringern wir die Gesamtzahl der Begriffe in der hamiltona.
Später wird dadurch die Anzahl der zum Simulieren der hamiltonan erforderlichen Quantum-Gates reduziert.

### <a name="internal-representation"></a>Interne Darstellung

Eine fermionic-hamiltonan mit ein-und zwei-Text-Interaktionen wird in der zweiten quantifizierten Notation als dargestellt.

$ $ \begin{align} h = \sum \_ {PQ} h \_ {PQ} a ^ \dagger \_ {p} a \_ {q} + \frac {1} {2} \sum \_ {pqrs} h \_ {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a { \_ s}.
\end{align} $ $

In dieser Notation sind höchstens $N ^ 2 + N ^ 4 $ Koeffizienten vorhanden.
Viele dieser Koeffizienten können jedoch gesammelt werden, da Sie demselben Operator entsprechen.
Beispielsweise in dem Fall, in dem $p, q, r, bei s $ handelt es sich um unterschiedliche Indizes. Wir können die antikomoringregeln verwenden, um Folgendes anzuzeigen: $ $ a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} =-a ^ \dagger \_ {q} a ^ \dagger \_ {p} a \_ {r} a \_ {s} =-a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {s} a \_ {r} = a ^ \dagger \_ {q} a ^ \dagger \_ {p} a { \_ s} a \_ {r}.
$$

Ebenso wie $H $ "hermitian" ist jeder nicht-hermitian-fermionic-Operator, z \_ . b. $h {pqrs} a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} $, ein hermitian-Konjugate, das auch in $H $ gefunden wird. Um Gruppen von Begriffen eindeutig zu indizieren, die durch diese Symmetries gekennzeichnet sind, definieren wir eine kanonische Reihenfolge für die Indizes $ (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) $ einer beliebigen Sequenz von $n + m $ fermionic-Operatoren $a ^ \dagger \_ {i \_ 1} \cdots a ^ \dagger \_ {i \_ n} a \_ {j \_ 1} \cdots a \_ {j \_ m} $As folgt:
-   Alle Erstellungs Operatoren $a ^ \dagger \_ {i \_ \cdot} $ werden vor allen Vernichtungs Operatoren $a \_ {j \_ \cdot} $ platziert.
-   Alle Erstellungs Operator Indizes werden in aufsteigender Reihenfolge sortiert, \_ d. h. $i 1< i \_ 2< \cdots < i \_ n $.
-   Alle Vernichtungs Operator Indizes werden in absteigender Reihenfolge sortiert, d \_ . h. $j 1> j \_ 2 \cdots > j \_ m $.
-   Der linke Index ist kleiner als oder gleich dem äußersten rechten Index, d \_ . h. $i 1 \ Le j \_ m $.

Lassen Sie uns diesen Satz von kanonisch geordneten Indizes als $ $ \begin{align} (i \_ 1, \cdots, i \_ n, j \_ 1, \cdots, j \_ m) \in S \_ {n, m} identifizieren.
\end{align} $ $

Bei dieser kanonischen Reihenfolge kann die fermionische hamiltonan als $ $ \begin{align} H = \sum \_ {(p, q) \in S \_ {1,1} } H " \_ {PQ} \bruchteil {a ^ \dagger \_ {p} a \_ {q} + a ^ \dagger \_ {q} a \_ {p}} {2} + \sum \_ {(p, q, r, e) \in s \_ {2,2} } H" \_ {pqrs} \bruchteil {a ^ \dagger \_ {p} a ^ \dagger \_ {q} a \_ {r} a \_ {s} + a ^ \dagger \_ {s} a ^ \dagger \_ {r} a \_ {q} a \_ {p}} {2} , \end{align} $ $ mit passend angepassten 1-und zwei-Elektronen-inteden $h " \_ {PQ} $ und $h" \_ {pqrs} $.

