---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Addfxp-Vorgang
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707663"
---
# <a name="addfxp-operation"></a><span data-ttu-id="c4b8a-102">Addfxp-Vorgang</span><span class="sxs-lookup"><span data-stu-id="c4b8a-102">AddFxP operation</span></span>

<span data-ttu-id="c4b8a-103">Namespace: [Microsoft. Quantum. Arithmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="c4b8a-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="c4b8a-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c4b8a-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c4b8a-105">Addiert zwei in quantenregistern gespeicherte Fixed-Point-Nummern.</span><span class="sxs-lookup"><span data-stu-id="c4b8a-105">Adds two fixed-point numbers stored in quantum registers.</span></span>

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a><span data-ttu-id="c4b8a-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c4b8a-106">Description</span></span>

<span data-ttu-id="c4b8a-107">Bei Angabe von zwei fixpointregistern in den Zuständen $ \ket{f_1} $ und $ \ket{f_2} $ wird der Vorgang "$ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $" durchführt.</span><span class="sxs-lookup"><span data-stu-id="c4b8a-107">Given two fixed-point registers respectively in states $\ket{f_1}$ and $\ket{f_2}$, performs the operation $\ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2}$.</span></span>

## <a name="input"></a><span data-ttu-id="c4b8a-108">Eingabe</span><span class="sxs-lookup"><span data-stu-id="c4b8a-108">Input</span></span>

### <a name="fp1--fixedpoint"></a><span data-ttu-id="c4b8a-109">Fp1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c4b8a-109">fp1 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c4b8a-110">Erste festpunktzahl</span><span class="sxs-lookup"><span data-stu-id="c4b8a-110">First fixed-point number</span></span>


### <a name="fp2--fixedpoint"></a><span data-ttu-id="c4b8a-111">FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span><span class="sxs-lookup"><span data-stu-id="c4b8a-111">fp2 : [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)</span></span>

<span data-ttu-id="c4b8a-112">Die zweite festpunktzahl wird aktualisiert und enthält nun die Summe der beiden Eingaben.</span><span class="sxs-lookup"><span data-stu-id="c4b8a-112">Second fixed-point number, will be updated to contain the sum of the two inputs.</span></span>



## <a name="output--unit"></a><span data-ttu-id="c4b8a-113">Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="c4b8a-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="c4b8a-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4b8a-114">Remarks</span></span>

<span data-ttu-id="c4b8a-115">Die aktuelle-Implementierung erfordert, dass die zwei fest Komma Zahlen die gleiche Punktposition aufweisen, die vom unbedeutenden Bit gezählt wird, d. h. $n _I $ und $p, dass _I $ gleich sein muss.</span><span class="sxs-lookup"><span data-stu-id="c4b8a-115">The current implementation requires the two fixed-point numbers to have the same point position counting from the least-significant bit, i.e., $n_i$ and $p_i$ must be equal.</span></span>