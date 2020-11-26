---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: Purifedmixedstatewithdata-Funktion
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229952"
---
# <a name="purifiedmixedstatewithdata-function"></a><span data-ttu-id="359e7-102">Purifedmixedstatewithdata-Funktion</span><span class="sxs-lookup"><span data-stu-id="359e7-102">PurifiedMixedStateWithData function</span></span>

<span data-ttu-id="359e7-103">Namespace: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="359e7-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="359e7-104">Paket: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="359e7-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="359e7-105">Gibt einen Vorgang zurück, der eine Bereinigung eines gegebenen gemischten Zustands vorbereitet, der durch ein Register entkoppelt ist, das eine angegebene Auflistung von Daten darstellt.</span><span class="sxs-lookup"><span data-stu-id="359e7-105">Returns an operation that prepares a a purification of a given mixed state, entangled with a register representing a given collection of data.</span></span>
<span data-ttu-id="359e7-106">Ein "gereinigter gemischter Zustand mit Daten" bezieht sich auf den Zustand "", "", "", "", "⟩" | "⟩" | "garbagei ⟩", wobei jede XI-Datei eine Bitzeichenfolge ist</span><span class="sxs-lookup"><span data-stu-id="359e7-106">A "purified mixed state with data" refers to a state of the form Σᵢ √𝑝ᵢ |𝑖⟩ |𝑥ᵢ⟩ |garbageᵢ⟩, where each 𝑥ᵢ is a bitstring encoding additional data associated with the register |𝑖⟩.</span></span>

<span data-ttu-id="359e7-107">Weitere Erläuterungen finden Sie unter https://arxiv.org/pdf/1805.03662.pdf?page=15 .</span><span class="sxs-lookup"><span data-stu-id="359e7-107">See https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion.</span></span>

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a><span data-ttu-id="359e7-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="359e7-108">Description</span></span>

<span data-ttu-id="359e7-109">Verwendet die Quantum-Rom-Technik, um eine gegebene Dichte Matrix darzustellen, und gibt diese Darstellung als Zustands Vorbereitungs Vorgang zurück.</span><span class="sxs-lookup"><span data-stu-id="359e7-109">Uses the Quantum ROM technique to represent a given density matrix, returning that representation as a state preparation operation.</span></span>

<span data-ttu-id="359e7-110">Insbesondere, wenn eine Liste mit $N $ Koeffizienten $ \ alpha_j $,_Diese Funktion gibt einen Vorgang zurück, der die Quantum-Rom-Technik zum Vorbereiten einer Näherung von $ $ verwendet. \begin{align} \tilde \rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ des gemischten Zustands $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ Frac {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x} _J}, \end{align} $ $, wobei jeder $p _J $ eine Näherung zum gegebenen Koeffizienten $ \ alpha_j $ darstellt, sodass $ $ \begin{align} \left | p_j-\bruch{| \ alpha_j |} {\ sum_k | \ alpha_k |} \le \frac{\epsilon}{N} \end{align} $ $ für jede $j $.</span><span class="sxs-lookup"><span data-stu-id="359e7-110">In particular, given a list of $N$ coefficients $\alpha_j$, and a bitstring $\vec{x}_j$ associated with each coefficient, this function returns an operation that uses the Quantum ROM technique to prepare an approximation $$ \begin{align} \tilde\rho = \sum_{j = 0}^{N - 1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j} \end{align} $$ of the mixed state $$ \begin{align} \rho = \sum_{j = 0}^{N-1}\ frac{|alpha_j|}{\sum_k |\alpha_k|} \ket{j}\bra{j} \otimes \ket{\vec{x}_j}\bra{\vec{x}_j}, \end{align} $$ where each $p_j$ is an approximation to the given coefficient $\alpha_j$ such that $$ \begin{align} \left| p_j - \frac{ |\alpha_j| }{ \sum_k |\alpha_k| } \le \frac{\epsilon}{N} \end{align} $$ for each $j$.</span></span>

<span data-ttu-id="359e7-111">Wenn ein Indexregister und ein Register von Garbage Qubits, anfänglich im Status $ \ket {0} \ket{00\cdots 0}, übergeben werden, bereitet der zurückgegebene Vorgang beide Register bei der Bereinigung von $ \tilde \rho $ vor. $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{Garbage} _J}, \end{align} $ $, damit das Zurücksetzen und Aufheben der Zuordnung des Garbage Registers die gewünschte Vorbereitung für innerhalb des Ziel Fehlers $ \epsilon $ aufsetzt.</span><span class="sxs-lookup"><span data-stu-id="359e7-111">When passed an index register and a register of garbage qubits, initially in the state $\ket{0} \ket{00\cdots 0}, the returned operation prepares both registers into the purification of $\tilde \rho$, $$ \begin{align} \sum_{j=0}^{N-1} \sqrt{p_j} \ket{j} \ket{\vec{x}_j} \ket{\text{garbage}_j}, \end{align} $$ such that resetting and deallocating the garbage register enacts the desired preparation to within the target error $\epsilon$.</span></span>

## <a name="input"></a><span data-ttu-id="359e7-112">Eingabe</span><span class="sxs-lookup"><span data-stu-id="359e7-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="359e7-113">targeterror: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="359e7-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="359e7-114">Der Ziel Fehler $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="359e7-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--doublebool"></a><span data-ttu-id="359e7-115">Koeffizienten: ([Double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []</span><span class="sxs-lookup"><span data-stu-id="359e7-115">coefficients : ([Double](xref:microsoft.quantum.lang-ref.double),[Bool](xref:microsoft.quantum.lang-ref.bool)[])[]</span></span>

<span data-ttu-id="359e7-116">Ein Array von $N $ Koeffizienten, das die Wahrscheinlichkeit der Basiszustände zusammen mit der bitstring $ \vec{x} _J $ angibt, die mit jedem Koeffizienten verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="359e7-116">Array of $N$ coefficients specifying the probability of basis states, along with the bitstring $\vec{x}_j$ associated with each coefficient.</span></span>
<span data-ttu-id="359e7-117">Negative Zahlen $-\ alpha_j $ werden als positiv $ | \ alpha_j | $ behandelt.</span><span class="sxs-lookup"><span data-stu-id="359e7-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--mixedstatepreparation"></a><span data-ttu-id="359e7-118">Ausgabe: [mixedstatepreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span><span class="sxs-lookup"><span data-stu-id="359e7-118">Output : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)</span></span>

<span data-ttu-id="359e7-119">Ein Vorgang, bei dem $ \tilde \rho $ als Bereinigung auf einen gemeinsamen Index und ein Garbage Register vorbereitet wird.</span><span class="sxs-lookup"><span data-stu-id="359e7-119">An operation that prepares $\tilde \rho$ as a purification onto a joint index and garbage register.</span></span>

## <a name="remarks"></a><span data-ttu-id="359e7-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="359e7-120">Remarks</span></span>

<span data-ttu-id="359e7-121">Die Koeffizienten, die für diesen Vorgang bereitgestellt werden, werden nach der Norm 1 normalisiert, sodass die Koeffizienten immer als eine gültige kategorische Wahrscheinlichkeitsverteilung bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="359e7-121">The coefficients provided to this operation are normalized following the 1-norm, such that the coefficients are always considered to describe a valid categorical probability distribution.</span></span>

## <a name="references"></a><span data-ttu-id="359e7-122">Referenzen</span><span class="sxs-lookup"><span data-stu-id="359e7-122">References</span></span>

- <span data-ttu-id="359e7-123">Encoding Electronic Spectra in Quantum-Verbindungen mit linearer T-Komplexität Ryan babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru paler, Austin Fowler, Hartmut netven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="359e7-123">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>

## <a name="see-also"></a><span data-ttu-id="359e7-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="359e7-124">See Also</span></span>

- [<span data-ttu-id="359e7-125">Microsoft. Quantum. Preparation. purifedmixedstate</span><span class="sxs-lookup"><span data-stu-id="359e7-125">Microsoft.Quantum.Preparation.PurifiedMixedState</span></span>](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)