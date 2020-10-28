---
uid: Microsoft.Quantum.Logical.LessThanOrEqualL
title: Lessthanorequall-Funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanOrEqualL
qsharp.summary: Returns true if and only if a number is less than or equal to another number.
ms.openlocfilehash: 333b76fc4885104e107dd25003a4e0dd5a9dd4af
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701447"
---
# <a name="lessthanorequall-function"></a><span data-ttu-id="06f03-102">Lessthanorequall-Funktion</span><span class="sxs-lookup"><span data-stu-id="06f03-102">LessThanOrEqualL function</span></span>

<span data-ttu-id="06f03-103">Namespace: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="06f03-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="06f03-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="06f03-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="06f03-105">Gibt nur dann true zurück, wenn eine Zahl kleiner oder gleich einer anderen Zahl ist.</span><span class="sxs-lookup"><span data-stu-id="06f03-105">Returns true if and only if a number is less than or equal to another number.</span></span>

```qsharp
function LessThanOrEqualL (a : BigInt, b : BigInt) : Bool
```


## <a name="input"></a><span data-ttu-id="06f03-106">Eingabe</span><span class="sxs-lookup"><span data-stu-id="06f03-106">Input</span></span>

### <a name="a--bigint"></a><span data-ttu-id="06f03-107">a: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="06f03-107">a : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="06f03-108">Der erste zu vergleichende Wert.</span><span class="sxs-lookup"><span data-stu-id="06f03-108">The first value to be compared.</span></span>


### <a name="b--bigint"></a><span data-ttu-id="06f03-109">b: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="06f03-109">b : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>

<span data-ttu-id="06f03-110">Der zweite zu vergleichende Wert.</span><span class="sxs-lookup"><span data-stu-id="06f03-110">The second value to be compared.</span></span>



## <a name="output--bool"></a><span data-ttu-id="06f03-111">Ausgabe: [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="06f03-111">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>

<span data-ttu-id="06f03-112">`true``a`, wenn kleiner oder gleich ist `b` .</span><span class="sxs-lookup"><span data-stu-id="06f03-112">`true` if and only if `a` is less than or equal to `b`.</span></span>

## <a name="remarks"></a><span data-ttu-id="06f03-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="06f03-113">Remarks</span></span>

<span data-ttu-id="06f03-114">Die folgenden sind gleichwertig:</span><span class="sxs-lookup"><span data-stu-id="06f03-114">The following are equivalent:</span></span>

```Q#
let cond = a <= b;
let cond = LessThanOrEqualL(a, b);
```