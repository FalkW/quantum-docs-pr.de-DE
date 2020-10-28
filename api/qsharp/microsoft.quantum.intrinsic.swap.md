---
uid: Microsoft.Quantum.Intrinsic.SWAP
title: Austausch Vorgang
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: SWAP
qsharp.summary: >-
  Applies the SWAP gate to a pair of qubits.

  \begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}

  where rows and columns are ordered as in the quantum concepts guide.
ms.openlocfilehash: 18b910741e9d0883fc5fcd025eb647407c823269
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706527"
---
# <a name="swap-operation"></a><span data-ttu-id="964d3-102">Austausch Vorgang</span><span class="sxs-lookup"><span data-stu-id="964d3-102">SWAP operation</span></span>

<span data-ttu-id="964d3-103">Namespace: [Microsoft. Quantum. intrinsisch](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="964d3-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="964d3-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="964d3-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="964d3-105">Wendet das Auslagerungs Gate auf ein paar von Qubits an.</span><span class="sxs-lookup"><span data-stu-id="964d3-105">Applies the SWAP gate to a pair of qubits.</span></span>

<span data-ttu-id="964d3-106">\begin{align} \operatorname{tauap} \mathrel{: =} \begin{bmatrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}</span><span class="sxs-lookup"><span data-stu-id="964d3-106">\begin{align} \operatorname{SWAP} \mathrel{:=} \begin{bmatrix} 1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{bmatrix}, \end{align}</span></span>

<span data-ttu-id="964d3-107">Dabei werden Zeilen und Spalten im Quantum-Konzept Handbuch als geordnet angezeigt.</span><span class="sxs-lookup"><span data-stu-id="964d3-107">where rows and columns are ordered as in the quantum concepts guide.</span></span>

```qsharp
operation SWAP (qubit1 : Qubit, qubit2 : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="964d3-108">Eingabe</span><span class="sxs-lookup"><span data-stu-id="964d3-108">Input</span></span>

### <a name="qubit1--qubit"></a><span data-ttu-id="964d3-109">qubit1: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="964d3-109">qubit1 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="964d3-110">Das erste Qubit, das ausgetauscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="964d3-110">First qubit to be swapped.</span></span>


### <a name="qubit2--qubit"></a><span data-ttu-id="964d3-111">qubit2: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="964d3-111">qubit2 : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="964d3-112">Zweites Qubit, das ausgetauscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="964d3-112">Second qubit to be swapped.</span></span>



## <a name="output--unit"></a><span data-ttu-id="964d3-113">Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="964d3-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="964d3-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="964d3-114">Remarks</span></span>

<span data-ttu-id="964d3-115">Äquivalent zu:</span><span class="sxs-lookup"><span data-stu-id="964d3-115">Equivalent to:</span></span>

```qsharp
CNOT(qubit1, qubit2);
CNOT(qubit2, qubit1);
CNOT(qubit1, qubit2);
```