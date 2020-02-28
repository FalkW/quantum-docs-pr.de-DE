---
title: Simulieren von hamiltona Dynamics
description: Erfahren Sie, wie Sie Trotter-Suzuki-Formeln und die qubisierung verwenden, um mit hamiltona-Simulationen zu arbeiten.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.simulationalgorithms
ms.openlocfilehash: e3ce76f5ddcca497adb519eece959c9dd5dec92f
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904637"
---
# <a name="simulating-hamiltonian-dynamics"></a><span data-ttu-id="05197-103">Simulieren von hamiltona Dynamics</span><span class="sxs-lookup"><span data-stu-id="05197-103">Simulating Hamiltonian Dynamics</span></span>

<span data-ttu-id="05197-104">Sobald der hamiltonan als Summe der elementaren Operatoren ausgedrückt wurde, kann die Dynamics dann mithilfe eines Hosts bekannter Techniken in grundlegende Gate-Vorgänge kompiliert werden.</span><span class="sxs-lookup"><span data-stu-id="05197-104">Once the Hamiltonian has been expressed as a sum of elementary operators the dynamics can then be compiled into fundamental gate operations using a host of well-known techniques.</span></span>
<span data-ttu-id="05197-105">Zu den drei effizienten Ansätzen gehören Trotter – Suzuki-Formeln, lineare Kombinationen von Uni-und qubisierungen.</span><span class="sxs-lookup"><span data-stu-id="05197-105">Three efficient approaches include are Trotter–Suzuki formulas, linear combinations of unitaries, and qubitization.</span></span>
<span data-ttu-id="05197-106">Im folgenden werden diese drei Ansätze erläutert und konkrete Q #-Beispiele für die Implementierung dieser Methoden mithilfe der hamiltonan Simulations Bibliothek erläutert.</span><span class="sxs-lookup"><span data-stu-id="05197-106">We explain these three approaches below and give concrete Q# examples of how to implement these methods using the Hamiltonian simulation library.</span></span>


## <a name="trottersuzuki-formulas"></a><span data-ttu-id="05197-107">Trotter – Suzuki-Formeln</span><span class="sxs-lookup"><span data-stu-id="05197-107">Trotter–Suzuki Formulas</span></span>
<span data-ttu-id="05197-108">Die Idee hinter Trotter – Suzuki-Formeln ist einfach: Ausdrücken Sie die hamiltonan als Summe von leicht zu simulierten hamiltonaten, und nähern Sie die Gesamtentwicklung als Sequenz dieser einfacheren Entwicklungen.</span><span class="sxs-lookup"><span data-stu-id="05197-108">The idea behind Trotter–Suzuki formulas is simple: express the Hamiltonian as a sum of easy to simulate Hamiltonians and then approximate the total evolution as a sequence of these simpler evolutions.</span></span>
<span data-ttu-id="05197-109">Legen Sie insbesondere $H = \ sum_ {j = 1} ^ m H_j $ der hamiltonan.</span><span class="sxs-lookup"><span data-stu-id="05197-109">In particular, let $H=\sum_{j=1}^m H_j$ be the Hamiltonian.</span></span>
<span data-ttu-id="05197-110">Dann $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \ prod_ {j = 1} ^ m e ^ {-iH_j t} + O (m ^ 2 t ^ 2), $ $, was heißt, dass, wenn $t \ll $1, der Fehler in dieser Näherungs Weise unerheblich wird.</span><span class="sxs-lookup"><span data-stu-id="05197-110">Then, $$ e^{-i\sum_{j=1}^m H_j t} =\prod_{j=1}^m e^{-iH_j t} + O(m^2 t^2), $$ which is to say that, if $t\ll 1$, then the error in this approximation becomes negligible.</span></span>
<span data-ttu-id="05197-111">Beachten Sie, dass der Fehler in dieser Näherung nicht $O (m ^ 2 t ^ 2) $, wenn $e ^ {-i H t} $ eine gewöhnliche exponentielle ist.</span><span class="sxs-lookup"><span data-stu-id="05197-111">Note that if $e^{-i H t}$ were an ordinary exponential then the error in this approximation would not be $O(m^2 t^2)$: it would be zero.</span></span>
<span data-ttu-id="05197-112">Dieser Fehler tritt auf, weil $e ^ {-IHT} $ ein Operator exponentiell ist und daher bei der Verwendung dieser Formel ein Fehler aufgetreten ist, da die $H _J $ Terms nicht übernehmen (*d. h.* $H _J H_k \nE H_k H_j $ im allgemeinen).</span><span class="sxs-lookup"><span data-stu-id="05197-112">This error occurs because $e^{-iHt}$ is an operator exponential and as a result there is an error incurred when using this formula due to the fact that the $H_j$ terms do not commute (*i.e.*, $H_j H_k \ne H_k H_j$ in general).</span></span>

<span data-ttu-id="05197-113">Wenn $t $ groß ist, kann Trotter– Suzuki-Formeln weiterhin verwendet werden, um die Dynamics genau zu simulieren, indem Sie Sie in eine Abfolge kurzer Zeit Schritte aufteilen.</span><span class="sxs-lookup"><span data-stu-id="05197-113">If $t$ is large, Trotter–Suzuki formulas can still be used to simulate the dynamics accurately by breaking it up into a sequence of short time-steps.</span></span>
<span data-ttu-id="05197-114">$R $ ist die Anzahl der Schritte, die in der Zeitentwicklung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="05197-114">Let $r$ be the number of steps taken in the time evolution.</span></span>
<span data-ttu-id="05197-115">Dann haben wir die $ $ e ^ {-i \ sum_ {j = 1} ^ m H_j t} = \left (\ prod_ {j = 1} ^ m e ^ {-iH_j t/r} \ right) ^ r + O (m ^ 2 t ^ 2/r), $ $. Dies impliziert, dass der Fehler, wenn $r $ als $m ^ 2 t ^ 2/\ Epsilon $ skaliert werden kann, höchstens $ \epsilon $ für alle $ \epsilon-> 0 $.</span><span class="sxs-lookup"><span data-stu-id="05197-115">Then, we have that $$ e^{-i\sum_{j=1}^m H_j t} =\left(\prod_{j=1}^m e^{-iH_j t/r}\right)^r + O(m^2 t^2/r), $$ which implies that if $r$ scales as $m^2 t^2/\epsilon$ then the error can be made at most $\epsilon$ for any $\epsilon>0$.</span></span>

<span data-ttu-id="05197-116">Genauere Näherungen können erstellt werden, indem eine Sequenz von Operator exponentialen erstellt wird, sodass die fehlerbegriffe abgebrochen werden.</span><span class="sxs-lookup"><span data-stu-id="05197-116">More accurate approximations can be built by constructing a sequence of operator exponentials such that the error terms cancel.</span></span>
<span data-ttu-id="05197-117">Die einfachste Formel, die symmetrische trockformel oder die Rollen Aufteilung, hat die Form $ $ U_1 (t) = \ prod_ {j = 1} ^ m e ^ {-iH_j t/2} \ prod_ {j = m} ^ 1 e ^ {-iH_j t} = e ^ {-IHT} + O (m ^ 3 t ^ 3), $ $, die für alle $ \epsilon-> 0 $ weniger als $ \epsilon $ erstellt werden können, indem Sie $r $ zum Skalieren als $m ^ {3/2} t ^ {3/2}/\sqrt {\ Epsilon} $ auswählen.</span><span class="sxs-lookup"><span data-stu-id="05197-117">The simplest such formula, the symmetric Trotter formula or Strang splitting, takes the form $$ U_1(t) =\prod_{j=1}^m e^{-iH_j t/2}\prod_{j=m}^1 e^{-iH_j t} = e^{-iHt} + O(m^3 t^3), $$ which can be made less than $\epsilon$ for any $\epsilon>0$ by choosing $r$ to scale as $m^{3/2}t^{3/2}/\sqrt{\epsilon}$.</span></span>

<span data-ttu-id="05197-118">Sogar auf $U _1 $ basierende trotterformeln können erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="05197-118">Even higher-order Trotter formulas can be constructed based on $U_1$.</span></span>
<span data-ttu-id="05197-119">Die einfachste ist die folgende Formel für die vierte Bestellung: ursprünglich eingeführt von Suzuki: $ $ U_2 (t) = U_1 ^ 2 (s_1t) U_1 ([1-4s_1] t) U_1 ^ 2 (s_1 t) = e ^ {-IHT} + O (m ^ 5T ^ 5), $ $ WHERE $s _1 = (4-4 ^ {1/3}) ^{-1}$.</span><span class="sxs-lookup"><span data-stu-id="05197-119">The simplest is the following fourth order formula, originally introduced by Suzuki: $$ U_2(t) = U_1^2(s_1t) U_1([1-4s_1]t)U_1^2(s_1 t) = e^{-iHt} +O(m^5t^5), $$ where $s_1 = (4-4^{1/3})^{-1}$.</span></span>
<span data-ttu-id="05197-120">Im Allgemeinen können beliebig hochwertige Formeln ähnlich konstruiert werden. die Kosten, die durch die Verwendung komplexerer Integratoren entstehen, überwiegen jedoch häufig die Vorteile der vierten Reihenfolge für die meisten praktischen Probleme.</span><span class="sxs-lookup"><span data-stu-id="05197-120">In general, arbitrarily high-order formulas can be similarly constructed; however, the costs incurred from using more complex integrators often outweigh the benefits beyond fourth order for most practical problems.</span></span>

<span data-ttu-id="05197-121">Damit die oben genannten Strategien funktionieren, benötigen wir eine Methode zum Simulieren einer breiten Klasse von $e ^ {-iH_j t} $.</span><span class="sxs-lookup"><span data-stu-id="05197-121">In order to make the above strategies work, we need to have a method for simulating a wide class of $e^{-iH_j t}$.</span></span>
<span data-ttu-id="05197-122">Die einfachste Familie der hamiltoner und ist wohl nützlichsten, die wir hier verwenden können, sind Pauli-Operatoren.</span><span class="sxs-lookup"><span data-stu-id="05197-122">The simplest family of Hamiltonians, and arguably most useful, that we could use here are Pauli operators.</span></span>
<span data-ttu-id="05197-123">Die Pauli-Operatoren können problemlos simuliert werden, da Sie mithilfe von Clifford-Vorgängen (Standard Gates in Quantum Computing) diagonalisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="05197-123">Pauli operators can be easily simulated because they can be diagonalized using Clifford operations (which are standard gates in quantum computing).</span></span>
<span data-ttu-id="05197-124">Nach der Diagonalisierung können auch Ihre Eigenwerte gefunden werden, indem die Parität der Qubits berechnet wird, auf die Sie reagieren.</span><span class="sxs-lookup"><span data-stu-id="05197-124">Further, once they have been diagonalized, their eigenvalues can be found by computing the parity of the qubits on which they act.</span></span>

<span data-ttu-id="05197-125">Beispiel: $ $ e ^ {-ix\otimes X t} = (h\otimes h) e ^ {-iz\otimes Z t} (h\otimes h), $ $ WHERE $ $ e ^ {-i Z \otimes Z t} = \begin{bmatrix} e ^ {-IT} & 0 & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="05197-125">For example, $$ e^{-iX\otimes X t}= (H\otimes H)e^{-iZ\otimes Z t}(H\otimes H), $$ where $$ e^{-i Z \otimes Z t} = \begin{bmatrix} e^{-it} & 0  & 0  & 0 </span></span>\\\
        <span data-ttu-id="05197-126">0 & e ^ {i t} & 0 & 0 </span><span class="sxs-lookup"><span data-stu-id="05197-126">0 & e^{i t}  & 0 & 0 </span></span>\\\
        <span data-ttu-id="05197-127">0 & 0 & e ^ {IT} & 0 </span><span class="sxs-lookup"><span data-stu-id="05197-127">0 & 0 & e^{it} & 0 </span></span>\\\
        <span data-ttu-id="05197-128">0 & 0 & 0 & e ^ {-IT} \end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="05197-128">0 & 0 & 0 & e^{-it} \end{bmatrix}.</span></span>
<span data-ttu-id="05197-129">$ $ Hier, $e ^ {-IHT} \ket{00} = e ^ {IT} \ket{00}$ und $e ^ {-IHT} \ket{01} = e ^ {-IT} \ket{01}$, das direkt als Folge der Tatsache angesehen werden kann, dass die Parität von $0 $ $0 $ ist, während die Parität der Bitzeichenfolge $1 $ $1 $ ist.</span><span class="sxs-lookup"><span data-stu-id="05197-129">$$ Here, $e^{-iHt} \ket{00} = e^{it} \ket{00}$ and $e^{-iHt} \ket{01} = e^{-it} \ket{01}$, which can be seen directly as a consequence of the fact that the parity of $00$ is $0$ while the parity of the bit string $01$ is $1$.</span></span>

<span data-ttu-id="05197-130">Exponentiale von Pauli-Operatoren können mithilfe des <xref:microsoft.quantum.intrinsic.exp>-Vorgangs direkt in Q # implementiert werden:</span><span class="sxs-lookup"><span data-stu-id="05197-130">Exponentials of Pauli operators can be implemented directly in Q# using the <xref:microsoft.quantum.intrinsic.exp> operation:</span></span>
```qsharp
    using(qubits = Qubit[2]){
        let pauliString = [PauliX, PauliX];
        let evolutionTime = 1.0;

        // This applies 𝑒^{- 𝑖 𝑋⊗𝑋 𝑡} to qubits 0 and 1.
        Exp(pauliString, - evolutionTime, qubits);
    }
```

<span data-ttu-id="05197-131">Bei fermionic hamiltoniern ordnet die [– Wigner-Zerlegung von Jordanien](xref:microsoft.quantum.chemistry.concepts.jordanwigner) die hamiltonan einer Summe von Pauli-Operatoren zu.</span><span class="sxs-lookup"><span data-stu-id="05197-131">For Fermionic Hamiltonians, the [Jordan–Wigner decomposition](xref:microsoft.quantum.chemistry.concepts.jordanwigner) conveniently maps the Hamiltonian into a sum of Pauli operators.</span></span>
<span data-ttu-id="05197-132">Dies bedeutet, dass die oben beschriebene Vorgehensweise problemlos an die Simulation der Chemie angepasst werden kann.</span><span class="sxs-lookup"><span data-stu-id="05197-132">This means that the above approach can easily be adapted to simulating chemistry.</span></span>
<span data-ttu-id="05197-133">Anstatt alle Pauli-Begriffe in der Jordanien-Wigner-Darstellung manuell zu durchlaufen, finden Sie unten ein einfaches Beispiel für die Ausführung einer solchen Simulation innerhalb der Chemie.</span><span class="sxs-lookup"><span data-stu-id="05197-133">Rather than manually looping over all Pauli terms in the Jordan-Wigner representation, below is a simple example of how executing such a simulation within the chemistry would look.</span></span>
<span data-ttu-id="05197-134">Unser Ausgangspunkt ist eine [Jordanien – Wigner-Codierung](xref:microsoft.quantum.chemistry.concepts.jordanwigner) der fermionic hamiltonan, ausgedrückt als Instanz der `JordanWignerEncoding`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="05197-134">Our starting point is a [Jordan–Wigner encoding](xref:microsoft.quantum.chemistry.concepts.jordanwigner) of the Fermionic Hamiltonian, expressed in code as an instance of the `JordanWignerEncoding` class.</span></span>

```csharp
    // This example uses the following namespaces:
    // using Microsoft.Quantum.Chemistry.OrbitalIntegrals;
    // using Microsoft.Quantum.Chemistry.Fermion;
    // using Microsoft.Quantum.Chemistry.Pauli;
    // using Microsoft.Quantum.Chemistry.QSharpFormat;

    // We create an instance of the `FermionHamiltonian` objecclasst to store the terms.
    var hamiltonian = new OrbitalIntegralHamiltonian(new[] 
    {
        new OrbitalIntegral(new[] { 0, 1, 2, 3 }, 0.123),
        new OrbitalIntegral(new[] { 0, 1 }, 0.456)
    }).ToFermionHamiltonian(IndexConvention.UpDown);

    // We convert this fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = hamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);

    // We now convert this representation into a format consumable by Q#.
    var qSharpData = jordanWignerEncoding.ToQSharpFormat();
```

<span data-ttu-id="05197-135">Dieses Format der –-Darstellung von Jordanien, das von den Q #-Simulations Algorithmen genutzt werden kann, ist ein benutzerdefinierter Typ `JordanWignerEncodingData`.</span><span class="sxs-lookup"><span data-stu-id="05197-135">This format of the Jordan–Wigner representation that is consumable by the Q# simulation algorithms is a user-defined type `JordanWignerEncodingData`.</span></span>
<span data-ttu-id="05197-136">In Q # wird dieses Format an eine Hilfsfunktion `TrotterStepOracle`, die einen Operator zurückgibt, der die Zeit Weiterentwicklung mithilfe des Trotter – Suzuki Integrator zusätzlich zu anderen Parametern zurückgibt, die für seine Ausführung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="05197-136">Within Q#, this format is passed to a convenience function `TrotterStepOracle` that returns an operator approximating time-evolution using the Trotter—Suzuki integrator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// Choose the integrator step size
let stepSize = 1.0;

// Choose the order of the Trotter—Suzuki integrator.
let integratorOrder = 4;

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/stepSize` -- the number of steps required to simulate unit-time evolution.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  TrotterStepOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single time-step.
using(qubits = Qubit[nQubits]){

    // Apply single step of time-evolution
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="05197-137">Wichtig ist, dass diese Implementierung einige Optimierungen anwendet, die in [Simulation der elektronischen Struktur mit Quantum-Computern](https://arxiv.org/abs/1001.3855) erläutert werden, und die [Quantum-Algorithmen für die Quantum-Chemie verbessern](https://arxiv.org/abs/1403.1539) , um die erforderliche Anzahl von Single-Qubit-Drehungen zu minimieren und Simulations Fehler zu verringern.</span><span class="sxs-lookup"><span data-stu-id="05197-137">Importantly, this implementation applies some optimizations discussed in [Simulation of Electronic Structure Hamiltonians Using Quantum Computers](https://arxiv.org/abs/1001.3855) and [Improving Quantum Algorithms for Quantum Chemistry](https://arxiv.org/abs/1403.1539) to minimize the number of single-qubit rotations required, as well as reduce simulation errors.</span></span>

## <a name="qubitization"></a><span data-ttu-id="05197-138">Qubisierung</span><span class="sxs-lookup"><span data-stu-id="05197-138">Qubitization</span></span>

<span data-ttu-id="05197-139">Die qubisierung ist eine alternative Methode für die Simulation, bei der Ideen aus Quantum-Durchgängen zum Simulieren von Quantum Dynamics verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="05197-139">Qubitization is an alternative approach to simulation that uses ideas from quantum walks to simulate quantum dynamics.</span></span>
<span data-ttu-id="05197-140">Obwohl die qubisierung mehr Qubits als trotterformeln erfordert, verspricht die Methode eine optimale Skalierung mit der Entwicklungszeit und der Fehlertoleranz.</span><span class="sxs-lookup"><span data-stu-id="05197-140">While qubitization requires more qubits than Trotter formulas, the method promises optimal scaling with the evolution time and the error tolerance.</span></span>
<span data-ttu-id="05197-141">Aus diesen Gründen wurde sie zu einer bevorzugten Methode zum Simulieren von hamiltona Dynamics im allgemeinen und zum Lösen des Problems mit der elektronischen Struktur.</span><span class="sxs-lookup"><span data-stu-id="05197-141">For these reasons it has become a favored method for simulating Hamiltonian dynamics in general, and for solving the electronic structure problem in particular.</span></span>

<span data-ttu-id="05197-142">Auf hoher Ebene wird dies durch die qubisierung durch die folgenden Schritte erreicht.</span><span class="sxs-lookup"><span data-stu-id="05197-142">At a high level, qubitization accomplishes this through the following steps.</span></span>
<span data-ttu-id="05197-143">Lassen Sie zunächst $H = \ sum_j H_J H_j $ für einheitlich und hermitian $H _J $ und $h _J \ge $0.</span><span class="sxs-lookup"><span data-stu-id="05197-143">First, let $H=\sum_j h_j H_j$ for unitary and Hermitian $H_j$ and $h_j\ge 0$.</span></span>
<span data-ttu-id="05197-144">Durch die Durchführung eines paar von Reflektionen implementiert die qubisierung einen Operator, der $ $W = e ^ {\pm i \cos ^{-1}(H/| H | _1)}, $ $, wobei $ | H | _1 = \ sum_j | H_J | $ entspricht.</span><span class="sxs-lookup"><span data-stu-id="05197-144">By performing a pair of reflections, qubitization implements an operator that is equivalent to $$W=e^{\pm i \cos^{-1}(H/|h|_1)},$$ where $|h|_1 = \sum_j |h_j|$.</span></span>
<span data-ttu-id="05197-145">Der nächste Schritt umfasst das Transformieren der Eigenwerte des Walk-Operators aus $e ^ {i\pm \cos ^{-1}(E_k/| h | _1)} $, wobei $E _K $ die Eigenwerte von $H $ bis $e ^ {-iE_k t} $ sind.</span><span class="sxs-lookup"><span data-stu-id="05197-145">The next step involves transforming the eigenvalues of the walk operator from $e^{i\pm \cos^{-1}(E_k/|h|_1)}$, where $E_k$ are the eigenvalues of $H$ to $e^{-iE_k t}$.</span></span>
<span data-ttu-id="05197-146">Dies kann durch eine Vielzahl von Methoden zur Verwendung von Quantum-Singular-Werten erreicht werden, einschließlich der [Quantum-Signalverarbeitung](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span><span class="sxs-lookup"><span data-stu-id="05197-146">This can be achieved using a variety of quantum singular value transformation methods including [quantum signal processing](https://journals.aps.org/prl/abstract/10.1103/PhysRevLett.118.010501).</span></span>

<span data-ttu-id="05197-147">Wenn nur statische Mengen gewünscht werden (z. b. die Grund Zustands Energie der hamiltonan), genügt es, die [Phasen Schätzung](xref:microsoft.quantum.libraries.characterization) direkt auf $W $ anzuwenden, um die Energie des Grund Zustands aus dem Ergebnis zu schätzen, indem der Kosinus des Ergebnisses übernommen wird.</span><span class="sxs-lookup"><span data-stu-id="05197-147">Alternatively, if only static quantities are desired (such as the ground state energy of the Hamiltonian) then it suffices to apply [phase estimation](xref:microsoft.quantum.libraries.characterization) directly to $W$ to estimate the ground state energy from the result by taking the cosine of the result.</span></span>
<span data-ttu-id="05197-148">Dies ist von großer Bedeutung, da die Transformation für das Spektral-und nicht eine Quantum-Methode zur Singular-Wert-Transformation ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="05197-148">This is significant because it allows the spectral transformation to be performed classically rather than using a quantum singular value transformation method.</span></span>

<span data-ttu-id="05197-149">Auf einer detaillierteren Ebene erfordert die Implementierung der qubisierung zwei Unterroutinen, die die Schnittstellen für die hamiltonan bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="05197-149">On a more detailed level, the implementation of qubitization requires two subroutines that provide the interfaces for the Hamiltonian.</span></span>
<span data-ttu-id="05197-150">Im Gegensatz zu Trotter– Suzuki-Methoden sind diese Unterroutinen Quantum nicht klassisch, und ihre Implementierung erfordert, dass logarithmisch mehr Qubits verwendet werden, als für eine trotterbasierte Simulation erforderlich wären.</span><span class="sxs-lookup"><span data-stu-id="05197-150">Unlike Trotter–Suzuki methods, these subroutines are quantum not classical and their implementation will necessitate using logarithmically more qubits than would be required for a Trotter-based simulation.</span></span>

<span data-ttu-id="05197-151">Die erste Quantum-Unterroutine, die von der qubisierung verwendet wird, heißt $ \operatschmue{SELECT} $, und es wird versprochen, dass Sie "\begin{Equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}" ergeben. \end{Equation}, wobei jeder $H _J $ als hermitian angenommen wird. und einheitlich.</span><span class="sxs-lookup"><span data-stu-id="05197-151">The first quantum subroutine that qubitization uses is called $\operatorname{Select}$ and it is promised to yield \begin{equation} \operatorname{Select} \ket{j} \ket{\psi} = \ket{j} H_j \ket{\psi}, \end{equation} where each $H_j$ is assumed to be Hermitian and unitary.</span></span>
<span data-ttu-id="05197-152">Obwohl dies möglicherweise restriktiv ist, erinnern Sie sich, dass die Pauli-Operatoren hermitian und einheitlich sind und dass Anwendungen wie die Quantum-Chemie-Simulation natürlich in dieses Framework fallen.</span><span class="sxs-lookup"><span data-stu-id="05197-152">While this may seem to be restrictive, recall that Pauli operators are Hermitian and unitary and so applications like quantum chemistry simulation naturally fall into this framework.</span></span>
<span data-ttu-id="05197-153">Der $ \operatorname{Select} $-Vorgang, vielleicht überraschend, ist tatsächlich ein reflektionevorgang.</span><span class="sxs-lookup"><span data-stu-id="05197-153">The $\operatorname{Select}$ operation, perhaps surprisingly, is actually a reflection operation.</span></span>
<span data-ttu-id="05197-154">Dies kann von der Tatsache eingesehen werden, dass $ \operatschmue{Select} ^ 2 \ Ket {j} \ket{\psi} = \ket{j} \ket{\psi} $ seit jeder $H _J $ einheitlich und hermitian ist und somit die Eigenwerte $ \pm $1 aufweisen.</span><span class="sxs-lookup"><span data-stu-id="05197-154">This can be seen from the fact that $\operatorname{Select}^2\ket{j} \ket{\psi} = \ket{j} \ket{\psi}$ since each $H_j$ is unitary and Hermitian and thus has eigenvalues $\pm 1$.</span></span>

<span data-ttu-id="05197-155">Die zweite Unterroutine heißt $ \operatschmue{Prepare} $.</span><span class="sxs-lookup"><span data-stu-id="05197-155">The second subroutine is called $\operatorname{Prepare}$.</span></span>
<span data-ttu-id="05197-156">Während der SELECT-Vorgang eine Möglichkeit bietet, auf jeden der hamiltona-Begriffe einheitlich zuzugreifen $H _J $ bietet die Prepare-Unterroutine eine Methode für den Zugriff auf die Koeffizienten $h _J $, \begin{Equation} \operatorname{Prepare}\ket{0} = \ sum_j \sqrt{\bruchteil {H_J} {| H | _1}} \ket{j}.</span><span class="sxs-lookup"><span data-stu-id="05197-156">While the select operation provides a means to coherently access each of the Hamiltonian terms $H_j$ the prepare subroutine gives a method for accessing the coefficients $h_j$, \begin{equation} \operatorname{Prepare}\ket{0} = \sum_j \sqrt{\frac{h_j}{|h|_1}}\ket{j}.</span></span>
<span data-ttu-id="05197-157">\end{Equation} bei Verwendung eines multipliziert kontrollierten Phasen Gates sehen wir, dass $ $ \lambda\ket{0}^ {\otimes n} = \begin{Cases} \-\ket{x} & \text{if} x = 0 </span><span class="sxs-lookup"><span data-stu-id="05197-157">\end{equation} Then, by using a multiply controlled phase gate, we see that $$ \Lambda\ket{0}^{\otimes n} = \begin{cases} \-\ket{x} & \text{if } x = 0 </span></span>\\\
        <span data-ttu-id="05197-158">\ket{x} & \text{otherwi\*} \end{Cases}.</span><span class="sxs-lookup"><span data-stu-id="05197-158">\ket{x}   & \text{otherwise} \end{cases}.</span></span>
$$

<span data-ttu-id="05197-159">Der $ \operatorname{Prepare} $-Vorgang wird nicht direkt in der qubisierung verwendet, sondern stattdessen verwendet, um eine Reflektion über den Status zu implementieren, den $ \operatorname{Prepare} $ erstellt $ $ \begin{align} R &amp; = 1-2 \ Operatorname {Prepare} \ket{0}\bra{0} \operatschmue{Prepare} ^{-1} \\\\ &amp; = \operatschmue{Prepare} \lambda \operatschmue{Prepare} ^{-1}.</span><span class="sxs-lookup"><span data-stu-id="05197-159">The $\operatorname{Prepare}$ operation is not used directly in qubitization, but rather is used to implement a reflection about the state that $\operatorname{Prepare}$ creates $$ \begin{align} R &amp; = 1 - 2\operatorname{Prepare} \ket{0}\bra{0} \operatorname{Prepare}^{-1} \\\\ &amp; = \operatorname{Prepare} \Lambda \operatorname{Prepare}^{-1}.</span></span>
<span data-ttu-id="05197-160">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="05197-160">\end{align} $$</span></span>

<span data-ttu-id="05197-161">Der Walk-Operator, $W $, kann im Format $ \operatschmue{SELECT} $ und $R $ als $ $ W = \operatorname{Select} R ausgedrückt werden. $ $, das wiederum angezeigt werden kann, um einen Operator zu implementieren, der (bis zu einem isometry) zum $e ^ {\pm i \cos ^{-1}(H/| H | _1)} $ entspricht.</span><span class="sxs-lookup"><span data-stu-id="05197-161">The walk operator, $W$, can be expressed in terms of the $\operatorname{Select}$ and $R$ operations as $$ W = \operatorname{Select} R, $$ which again can be seen to implement an operator that is equivalent (up to an isometry) to $e^{\pm i \cos^{-1}(H/|h|_1)}$.</span></span>

<span data-ttu-id="05197-162">Diese Unterroutinen können einfach in Q # eingerichtet werden.</span><span class="sxs-lookup"><span data-stu-id="05197-162">These subroutines are easy to set up in Q#.</span></span>
<span data-ttu-id="05197-163">Stellen Sie sich als Beispiel das einfache Qubit-Kreuz, das eine Kreuz Zerlegung durch $H = x_1 + X_2 + Z_1 Z_2 $ in Erwägung.</span><span class="sxs-lookup"><span data-stu-id="05197-163">As an example, consider the simple qubit transverse-Ising Hamiltonian where $H = X_1 + X_2 + Z_1 Z_2$.</span></span>
<span data-ttu-id="05197-164">In diesem Fall wird der f #-Code, der den Vorgang $ \operatschmue{Select} $ implementiert, von <xref:microsoft.quantum.canon.multiplexoperations>aufgerufen, während der $ \operatorname{Prepare} $-Vorgang mithilfe von <xref:microsoft.quantum.preparation.preparearbitrarystate>implementiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="05197-164">In this case, Q# code that would implement the $\operatorname{Select}$ operation is invoked by <xref:microsoft.quantum.canon.multiplexoperations>, whereas the $\operatorname{Prepare}$ operation can be implemented using <xref:microsoft.quantum.preparation.preparearbitrarystate>.</span></span>
<span data-ttu-id="05197-165">Ein Beispiel zum Simulieren des Hubbard-Modells finden Sie in einem [Q #](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard)-Beispiel.</span><span class="sxs-lookup"><span data-stu-id="05197-165">An example that involves simulating the Hubbard model can be found as a [Q# sample](https://github.com/microsoft/Quantum/tree/master/samples/simulation/hubbard).</span></span>

<span data-ttu-id="05197-166">Wenn Sie diese Schritte für willkürliche chemische Probleme manuell angeben, wäre dies sehr aufwändig, was mithilfe der Chemie Bibliothek vermieden werden sollte.</span><span class="sxs-lookup"><span data-stu-id="05197-166">Manually specifying these steps for arbitrary chemistry problems would require much effort, which is avoided using the chemistry library.</span></span>
<span data-ttu-id="05197-167">Ähnlich wie beim Trotter– Suzuki-Simulations Algorithmus wird der `JordanWignerEncodingData` an die Hilfsfunktion `QubitizationOracle` weitergegeben, die den walkoperator zurückgibt, zusätzlich zu anderen Parametern, die für die Ausführung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="05197-167">Similarly to the Trotter–Suzuki simulation algorithm above, the `JordanWignerEncodingData` is passed to the convenience function `QubitizationOracle` that returns the walk-operator, in addition to other parameters required for its execution.</span></span>

```qsharp
// qSharpData passed from driver
let qSharpData = ... 

// `oracle` is an operation that applies a single time-step of evolution for duration `stepSize`.
// `rescale` is just `1.0/oneNorm`, where oneNorm is the sum of absolute values of all probabilities in state prepared by `Prepare`.
// `nQubits` is the number of qubits that must be allocated to run the `oracle` operation.
let (nQubits, (rescale, oracle)) =  QubitizationOracle (qSharpData, stepSize, integratorOrder);

// Let us now apply a single step of the quantum walk.
using(qubits = Qubit[nQubits]){

    // Apply single step of quantum walk.
    oracle(qubits);

    // Reset all qubits to the 0 state to be successfully released.
    ResetAll(qubits);
}
```

<span data-ttu-id="05197-168">Wichtig ist, dass die Implementierungs <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> auf beliebige hamiltonane anwendbar ist, die als lineare Kombination von Pauli-Zeichen folgen angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="05197-168">Importantly, the implementation <xref:microsoft.quantum.chemistry.jordanwigner.qubitizationoracle> is applicable to arbitrary Hamiltonians specified as a linear combination of Pauli strings.</span></span>
<span data-ttu-id="05197-169">Eine Version, die für Chemie Simulationen optimiert ist, wird mithilfe von <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="05197-169">A version optimized for chemistry simulations is invoked using <xref:microsoft.quantum.chemistry.jordanwigner.optimizedqubitizationoracle>.</span></span>
<span data-ttu-id="05197-170">Diese Version ist so optimiert, dass die Anzahl der T-Gates mithilfe der Techniken, die in [Encoding Electronic Spectra in Quantum-Leitungen mit linearer T-Komplexität](https://arxiv.org/abs/1805.03662)erläutert werden,</span><span class="sxs-lookup"><span data-stu-id="05197-170">This version is optimized to minimize the number of T gates using techniques discussed in [Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity](https://arxiv.org/abs/1805.03662).</span></span>
