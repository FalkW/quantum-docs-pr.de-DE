---
uid: Microsoft.Quantum.Math.Fraction
title: Benutzerdefinierter Bruchteil-Typ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: Fraction
qsharp.summary: Represents a rational number of the form `p/q`. Integer `p` is the first element of the tuple and `q` is the second element of the tuple.
ms.openlocfilehash: 350d470c374fc8e0a3f4c4a9a68ad8566ab88727
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723661"
---
# <a name="fraction-user-defined-type"></a><span data-ttu-id="fbf22-102">Benutzerdefinierter Bruchteil-Typ</span><span class="sxs-lookup"><span data-stu-id="fbf22-102">Fraction user defined type</span></span>

<span data-ttu-id="fbf22-103">Namespace: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)</span><span class="sxs-lookup"><span data-stu-id="fbf22-103">Namespace: [Microsoft.Quantum.Math](xref:Microsoft.Quantum.Math)</span></span>

<span data-ttu-id="fbf22-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="fbf22-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="fbf22-105">Stellt eine rationale Zahl der Form dar `p/q` .</span><span class="sxs-lookup"><span data-stu-id="fbf22-105">Represents a rational number of the form `p/q`.</span></span> <span data-ttu-id="fbf22-106">"Integer" `p` ist das erste Element des Tupels und `q` ist das zweite Element des Tupels.</span><span class="sxs-lookup"><span data-stu-id="fbf22-106">Integer `p` is the first element of the tuple and `q` is the second element of the tuple.</span></span>

```qsharp

newtype Fraction = (Numerator : Int, Denominator : Int);
```



## <a name="named-items"></a><span data-ttu-id="fbf22-107">Benannte Elemente</span><span class="sxs-lookup"><span data-stu-id="fbf22-107">Named Items</span></span>

### <a name="numerator--int"></a><span data-ttu-id="fbf22-108">Zähler: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbf22-108">Numerator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbf22-109">Zähler des Bruchteils.</span><span class="sxs-lookup"><span data-stu-id="fbf22-109">Numerator of the fraction.</span></span>
### <a name="denominator--int"></a><span data-ttu-id="fbf22-110">Nenner: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="fbf22-110">Denominator : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="fbf22-111">Nenner des Bruchteils/</span><span class="sxs-lookup"><span data-stu-id="fbf22-111">Denominator of the fraction/</span></span>