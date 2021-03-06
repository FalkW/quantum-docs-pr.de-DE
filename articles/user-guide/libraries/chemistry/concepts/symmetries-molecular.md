---
title: Symmetries von molekularen inteden
description: Erfahren Sie, wie Sie den Q# Typ "orbitalintegral" verwenden, um molekulare Symmetries aufzulisten.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: conceptual
uid: microsoft.quantum.chemistry.concepts.symmetries
no-loc:
- Q#
- $$v
ms.openlocfilehash: 2622285fd95eddf0d70402ae99dd18bfd8c38087
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858823"
---
# <a name="symmetries-of-molecular-integrals"></a>Symmetries von molekularen inteden

Die inhärente Symmetrie von Coulomb hamiltonan, der hamiltona in [Quantum-Modellen für elektronische Systeme](xref:microsoft.quantum.chemistry.concepts.quantummodels), die die interaktive Interaktion von Elektronen und der Kerne beschreiben, führt zu einer Reihe von Symmetries, die ausgenutzt werden können, um die Begriffe in der hamiltona zu komprimieren.
Im Allgemeinen haben wir nur "\begin{Equation}" H_ {pqrs} = H_ {qpsr}, wenn keine weiteren Annahmen über die Basisfunktionen $ \ psi_j $ vorgenommen werden. \tag{★} \label{EQ: hpqrs} \end{Equation}, das direkt von den inteden in [Quantum-Modellen für elektronische Systeme](xref:microsoft.quantum.chemistry.concepts.quantummodels) eingesehen werden kann, wenn Sie feststellen, dass ihre Werte identisch bleiben, wenn sich $p, q $ und $r, s $ von der Anti--typverarbeitung unterscheiden.

Wenn wir davon ausgehen, dass die Dreh-orbitwerte Real wertig sind (wie es bei gauschen Orbital Basen der Fall ist), haben wir die Funktion "\begin{Equation}" H_ {pqrs} = H_ {qpsr} = H_ {srqp} = H_ {rspq} = H_ {RQPS} = H_ {psrq} = H_ {SPQR} = H_ {qrsp} .\tag {★} \label{EQ: hpqrsreal} \end{Equation}, wenn solche Annahmen angenommen werden, wir können die obigen Symmetries verwenden, um die Daten zu reduzieren, die zum Speichern der Matrix Elemente der hamiltona mit dem Faktor $8 $ erforderlich sind; auf diese Weise wird das Importieren von Daten auf konsistente Weise etwas schwieriger.
Glücklicherweise weist die hamiltonan-Simulations Bibliothek Unterroutinen auf, die verwendet werden können, um ganzzahlige Dateien aus " [Liqui $ | \rangle $](https://www.microsoft.com/en-us/research/project/language-integrated-quantum-operations-liqui/) " oder direkt aus " [nwchem](http://www.nwchem-sw.org/index.php/Main_Page)" zu importieren.

Molekular-Orbital inteder (d. h. die $h \_ {PQ} $ und $h \_ {pqrs} $-Begriffen) wie diese werden mithilfe des- `OrbitalIntegral` Typs dargestellt, der eine Reihe hilfreicher Funktionen zum Ausdrücken dieser Symmetrie bereitstellt.
```csharp
    // Load the namespace containing orbital integral objects.
    using Microsoft.Quantum.Chemistry.OrbitalIntegrals;

    // Create a `OrbitalIntegral` instance to store a one-electron molecular 
    // orbital integral data.
    var oneElectronOrbitalIndices = new[] { 0, 1 };
    var oneElectronCoefficient = 1.0;
    var oneElectronIntegral = new OrbitalIntegral(oneElectronOrbitalIndices, oneElectronCoefficient);

    // This enumerates all one-electron integrals with the same coefficient --
    // an array of equivalent `OrbitalIntegral` instances is generated. In this
    // case, there are two elements.
    var oneElectronIntegrals = oneElectronIntegral.EnumerateOrbitalSymmetries();

    // Create a `OrbitalIntegral` instance to store a two-electron molecular orbital integral data.
    var twoElectronOrbitalIndices = new[] { 0, 1, 2, 3 };
    var twoElectronCoefficient = 0.123;
    var twoElectronIntegral = new OrbitalIntegral(twoElectronOrbitalIndices, twoElectronCoefficient);

    // This enumerates all two-electron integrals with the same coefficient -- 
    // an array of equivalent `OrbitalIntegral` instances is generated. In 
    // this case, there are 8 elements.
    var twoElectronIntegrals = twoElectronIntegral.EnumerateOrbitalSymmetries();
```

Zusätzlich zur Enumeration aller auf numerischer Weise identischen Orbital inteder können Sie eine Liste aller Spin-Orbital-Indizes, die in der von einem dargestellten hamiltona enthalten sind, `OrbitalIntegral` wie folgt generieren.
```csharp
    // Create a `OrbitalIntegral` instance to store a two-electron molecular
    // orbital integral data.
    var twoElectronIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // This enumerates all spin-orbital indices of the `FermionTerm`s in the 
    // Hamiltonian represented by this integral -- this is an array of array 
    // of `SpinOrbital` instances.
    var twoElectronSpinOrbitalIndices = twoElectronIntegral.EnumerateSpinOrbitals();
```
## <a name="constructing-fermionic-hamiltonians-from-molecular-integrals"></a>Konstruieren von fermionic-hamiltonern aus molekularen inteden

Anstatt eine fermionic-hamiltonan durch Hinzufügen von-Objekten `FermionTerm` zu erstellen, werden alle Begriffe, die den einzelnen vollständig verwendeten Ganzzahlen entsprechen, möglicherweise automatisch
Der folgende Code listet z. b. automatisch alle permuational Symmetries auf und ordnet die Begriffe in kanonischer Reihenfolge an: 
```csharp
    // Load the namespace containing fermion objects. This
    // example also uses LINQ queries.
    using Microsoft.Quantum.Chemistry.Fermion;
    using System.Linq;

    // Create a `OrbitalIntegral` instance to store a two-electron molecular 
    // orbital integral data.
    var orbitalIntegral = new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123);

    // Create an `OrbitalIntegralHamiltonian` instance to store the orbital integral
    // terms
    var orbitalIntegralHamiltonian = new OrbitalIntegralHamiltonian();
    orbitalIntegralHamiltonian.Add(orbitalIntegral);

    // Convert the orbital integral representation to a fermion
    // representation. This also requires choosing a convention for 
    // mapping spin orbital indices to integer indices.
    var fermionHamiltonian = orbitalIntegralHamiltonian.ToFermionHamiltonian(IndexConvention.UpDown);

    // Alternatively, one can add orbital integrals directly to a fermion Hamiltonian
    // as follows. This automatically enumerates over all symmetries, and then
    // orders the `HermitianFermionTerm` instances in canonical order. We will need to
    // choose an indexing convention as well.
    fermionHamiltonian.AddRange(orbitalIntegral
        .ToHermitianFermionTerms(0, IndexConvention.UpDown)
        .Select(o => (o.Item1, o.Item2.ToDoubleCoeff())));
```
