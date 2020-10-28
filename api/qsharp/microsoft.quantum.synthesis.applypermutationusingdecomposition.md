---
uid: Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecomposition
title: Applypermutationusingzerlegungs-Vorgang
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyPermutationUsingDecomposition
qsharp.summary: Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.
ms.openlocfilehash: 40b51807da155c57c3fa8d740eff28ceef0a0ffc
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725314"
---
# <a name="applypermutationusingdecomposition-operation"></a><span data-ttu-id="fb91d-102">Applypermutationusingzerlegungs-Vorgang</span><span class="sxs-lookup"><span data-stu-id="fb91d-102">ApplyPermutationUsingDecomposition operation</span></span>

<span data-ttu-id="fb91d-103">Namespace: [Microsoft. Quantum. Synthese](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="fb91d-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="fb91d-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fb91d-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fb91d-105">Pertrauert die Verstärkung in einem Quantum-Zustand, wenn eine permutations mithilfe der Zerlegungs basierten Synthese verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb91d-105">Permutes the amplitudes in a quantum state given a permutation using decomposition-based synthesis.</span></span>

```qsharp
operation ApplyPermutationUsingDecomposition (perm : Int[], qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a><span data-ttu-id="fb91d-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="fb91d-106">Description</span></span>

<span data-ttu-id="fb91d-107">Mit dieser Prozedur wird der Ansatz der Zerlegungs basierten Synthese implementiert.</span><span class="sxs-lookup"><span data-stu-id="fb91d-107">This procedure implements the decomposition based synthesis approach.</span></span>  <span data-ttu-id="fb91d-108">Die Eingabe ist eine permutations $ \pi $ over $2 ^ n $ Elements $ \{ 0, \dots, 2 ^ n-1 \} $, was eine $n $-Variable umkehrbare boolesche Funktion darstellt.</span><span class="sxs-lookup"><span data-stu-id="fb91d-108">The input is a permutation $\pi$ over $2^n$ elements $\{0, \dots, 2^n-1\}$, which represents an $n$-variable reversible Boolean function.</span></span>
<span data-ttu-id="fb91d-109">Der Algorithmus führt iterativ die folgenden Schritte für jeden Variablen Index aus $i $:</span><span class="sxs-lookup"><span data-stu-id="fb91d-109">The algorithm iteratively performs the following steps for each variable index $i$:</span></span>

1. <span data-ttu-id="fb91d-110">Compute $ ((\ pi_l, \ pi_r), \pi ') $ so, dass die Bilder von $ \ pi_l $ und $ \ pi_r $ keine Bits in ihren Elementen in anderen Indizes als $i $ und Bilder von $ \pi ' $ do not Change Bit $i $ in ihren Elementen ändern.</span><span class="sxs-lookup"><span data-stu-id="fb91d-110">Compute $((\pi_l, \pi_r), \pi')$ such that the images of $\pi_l$ and $\pi_r$ do not change bits in their elements at indexes other than $i$ and images of $\pi'$ do not change bit $i$ in their elements.</span></span>
2. <span data-ttu-id="fb91d-111">Legen Sie $ \pi \leftpfeil \pi ' $, und leiten Sie Wahrheitstabellen aus $ \ pi_l $ und $ \ pi_r $ auf der Grundlage von Elementen, die keine Festpunkte sind, ab.</span><span class="sxs-lookup"><span data-stu-id="fb91d-111">Set $\pi \leftarrow \pi'$, and derive truth tables from $\pi_l$ and $\pi_r$ based on elements that are not fixed-points.</span></span>

<span data-ttu-id="fb91d-112">Nachdem Sie diese Schritte für alle Variablen Indizes ausgeführt haben, ist die verbleibende permutations $ \pi $ die Identität. basierend auf den gesammelten Wahrheitstabellen und-Indizes kann eine durch Wahrheitstabelle kontrollierte @"microsoft.quantum.intrinsic.x" Vorgänge mithilfe des-Vorgangs angewendet werden @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" .</span><span class="sxs-lookup"><span data-stu-id="fb91d-112">After applying these steps for all variable indexes, the remaining permutation $\pi$ will be the identity, and based on the collected truth tables and indexes, one can apply truth-table controlled @"microsoft.quantum.intrinsic.x" operations using the @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" operation.</span></span>

<span data-ttu-id="fb91d-113">Die Reihenfolge der Variablen ist $0, \dots, n-$1.</span><span class="sxs-lookup"><span data-stu-id="fb91d-113">The variable order is $0, \dots, n - 1$.</span></span>  <span data-ttu-id="fb91d-114">Eine benutzerdefinierte Reihenfolge der Variablen kann im Vorgang angegeben werden @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder" .</span><span class="sxs-lookup"><span data-stu-id="fb91d-114">A custom variable order can be specified in the operation @"microsoft.quantum.synthesis.applypermutationusingdecompositionwithvariableorder".</span></span>

## <a name="input"></a><span data-ttu-id="fb91d-115">Eingabe</span><span class="sxs-lookup"><span data-stu-id="fb91d-115">Input</span></span>

### <a name="perm--int"></a><span data-ttu-id="fb91d-116">Perm: [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="fb91d-116">perm : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="fb91d-117">Eine permutations von $2 ^ n $ Elementen, beginnend bei 0.</span><span class="sxs-lookup"><span data-stu-id="fb91d-117">A permutation of $2^n$ elements starting from 0.</span></span>


### <a name="qubits--littleendian"></a><span data-ttu-id="fb91d-118">Qubits: [littleenddian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="fb91d-118">qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="fb91d-119">Eine Liste von $n $ Qubits, auf die die permutations angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="fb91d-119">A list of $n$ qubits to which the permutation is applied to.</span></span>



## <a name="output--unit"></a><span data-ttu-id="fb91d-120">Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="fb91d-120">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="references"></a><span data-ttu-id="fb91d-121">Referenzen</span><span class="sxs-lookup"><span data-stu-id="fb91d-121">References</span></span>

- [<span data-ttu-id="fb91d-122">*Alexis de Vos* , *Yvan Van Rentergem* , ADV. in Math. of comm. 2 (2), 2008, pp. 183--200</span><span class="sxs-lookup"><span data-stu-id="fb91d-122">*Alexis De Vos* , *Yvan Van Rentergem* , Adv. in Math. of Comm. 2(2), 2008, pp. 183--200</span></span>](http://www.aimsciences.org/article/doi/10.3934/amc.2008.2.183)
- [<span data-ttu-id="fb91d-123">*Mathias soeken* , *Laura tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , Journal der symbolischen Berechnung 73 (2016), pp. 1--26</span><span class="sxs-lookup"><span data-stu-id="fb91d-123">*Mathias Soeken* , *Laura Tague* , *Gerhard W. Dueck* , *Rolf Drechsler* , Journal of Symbolic Computation 73 (2016), pp. 1--26</span></span>](https://www.sciencedirect.com/science/article/pii/S0747717115000188?via%3Dihub)

## <a name="see-also"></a><span data-ttu-id="fb91d-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb91d-124">See Also</span></span>

- [<span data-ttu-id="fb91d-125">Microsoft. Quantum. Synthese. applypermutationusingumcompositionwithvariableorder</span><span class="sxs-lookup"><span data-stu-id="fb91d-125">Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingDecompositionWithVariableOrder)
- [<span data-ttu-id="fb91d-126">Microsoft. Quantum. Synthese. applypermutationusingtransformation</span><span class="sxs-lookup"><span data-stu-id="fb91d-126">Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation</span></span>](xref:Microsoft.Quantum.Synthesis.ApplyPermutationUsingTransformation)