---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Standardamplituentverstärkungsfunktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 18228d45c4df280b004c595a7b0f1e2a607b8b2c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721744"
---
# <a name="standardamplitudeamplification-function"></a><span data-ttu-id="a3459-102">Standardamplituentverstärkungsfunktion</span><span class="sxs-lookup"><span data-stu-id="a3459-102">StandardAmplitudeAmplification function</span></span>

<span data-ttu-id="a3459-103">Namespace: [Microsoft. Quantum. Verstärkungs Verstärkung](xref:Microsoft.Quantum.AmplitudeAmplification)</span><span class="sxs-lookup"><span data-stu-id="a3459-103">Namespace: [Microsoft.Quantum.AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)</span></span>

<span data-ttu-id="a3459-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a3459-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a3459-105">Standard mäßiger Amplitude-Verstärkungs Algorithmus</span><span class="sxs-lookup"><span data-stu-id="a3459-105">Standard Amplitude Amplification algorithm</span></span>

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a><span data-ttu-id="a3459-106">Eingabe</span><span class="sxs-lookup"><span data-stu-id="a3459-106">Input</span></span>

### <a name="niterations--int"></a><span data-ttu-id="a3459-107">niterationen: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3459-107">nIterations : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3459-108">Anzahl der Iterationen $n $ der Amplitude-Verstärkung</span><span class="sxs-lookup"><span data-stu-id="a3459-108">Number of iterations $n$ of amplitude amplification</span></span>


### <a name="stateoracle--stateoracle"></a><span data-ttu-id="a3459-109">stateoracle: [stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span><span class="sxs-lookup"><span data-stu-id="a3459-109">stateOracle : [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)</span></span>

<span data-ttu-id="a3459-110">Einheitlicher Oracle-$A $, der den Startstatus vorbereitet</span><span class="sxs-lookup"><span data-stu-id="a3459-110">Unitary oracle $A$ that prepares start state</span></span>


### <a name="idxflagqubit--int"></a><span data-ttu-id="a3459-111">idxflagqubit: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="a3459-111">idxFlagQubit : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="a3459-112">Index zum Markieren von Qubit</span><span class="sxs-lookup"><span data-stu-id="a3459-112">Index to flag qubit</span></span>



## <a name="output--qubit--unit-adj--ctl"></a><span data-ttu-id="a3459-113">Ausgabe: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="a3459-113">Output : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="a3459-114">Ein Vorgang, der den standardmäßigen Amplitude-Verstärkungs Algorithmus implementiert.</span><span class="sxs-lookup"><span data-stu-id="a3459-114">An operation that implements the standard amplitude amplification quantum algorithm</span></span>

## <a name="remarks"></a><span data-ttu-id="a3459-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3459-115">Remarks</span></span>

<span data-ttu-id="a3459-116">Dies ist der standardmäßige Amplitude-Verstärkungs Algorithmus, der durch eine Auswahl von Reflexionsphasen erzielt wird, die durch `AmpAmpPhasesStandard` die Annahme berechnet werden, dass "\begin{align} a\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f \ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket- {0} \_ \end{align} dieser Vorgang bereitet den Status" \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket {1} \_ f \ket {\ Text {Target}} \_ s + \cdoz\ket {0} \_ f \end{align} "in den meisten Fällen vor. `flagQubit` und werden `auxiliaryRegister` im Zustand" $ \ket {0} \_ f \ket {0} \_ a $ "initialisiert.</span><span class="sxs-lookup"><span data-stu-id="a3459-116">This is the standard amplitude amplification algorithm obtained by a choice of reflection phases computed by `AmpAmpPhasesStandard` Assuming that \begin{align} A\ket{0}\_{f}\ket{0}\_s= \lambda\ket{1}\_f\ket{\text{target}}\_s + \sqrt{1-|\lambda|^2}\ket{0}\_f\cdots, \end{align} this operation prepares the state \begin{align} \operatorname{AmpAmpByOracle}\ket{0}\_{f}\ket{0}\_s= \sin((2n+1)\sin^{-1}(\lambda))\ket{1}\_f\ket{\text{target}}\_s + \cdots\ket{0}\_f \end{align} In most cases, `flagQubit` and `auxiliaryRegister` is initialized in the state $\ket{0}\_f\ket{0}\_a$.</span></span>

## <a name="references"></a><span data-ttu-id="a3459-117">Referenzen</span><span class="sxs-lookup"><span data-stu-id="a3459-117">References</span></span>

- [<span data-ttu-id="a3459-118">*G. Brassard, P. Hoyer, M. Musca, A. Tapp*</span><span class="sxs-lookup"><span data-stu-id="a3459-118"> *G. Brassard, P. Hoyer, M. Mosca, A. Tapp* </span></span>](https://arxiv.org/abs/quant-ph/0005055)