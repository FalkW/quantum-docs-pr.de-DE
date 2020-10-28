---
uid: Microsoft.Quantum.Convert.BoolArrayAsBigInt
title: Boolarrayasbigint-Funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: BoolArrayAsBigInt
qsharp.summary: Converts a given array of Booleans to an equivalent big integer. The 0 element of the array is the least significant bit of the big integer.
ms.openlocfilehash: 75656ba188a1b822eb42e98412365bf5873bf46e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703031"
---
# <a name="boolarrayasbigint-function"></a><span data-ttu-id="2b148-102">Boolarrayasbigint-Funktion</span><span class="sxs-lookup"><span data-stu-id="2b148-102">BoolArrayAsBigInt function</span></span>

<span data-ttu-id="2b148-103">Namespace: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)</span><span class="sxs-lookup"><span data-stu-id="2b148-103">Namespace: [Microsoft.Quantum.Convert](xref:Microsoft.Quantum.Convert)</span></span>

<span data-ttu-id="2b148-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="2b148-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="2b148-105">Konvertiert ein angegebenes Array von booleschen Werten in eine entsprechende große Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="2b148-105">Converts a given array of Booleans to an equivalent big integer.</span></span>
<span data-ttu-id="2b148-106">Das 0-Element des Arrays ist das am wenigsten bedeutende Bit der großen Ganzzahl.</span><span class="sxs-lookup"><span data-stu-id="2b148-106">The 0 element of the array is the least significant bit of the big integer.</span></span>

```qsharp
function BoolArrayAsBigInt (a : Bool[]) : BigInt
```


## <a name="input"></a><span data-ttu-id="2b148-107">Eingabe</span><span class="sxs-lookup"><span data-stu-id="2b148-107">Input</span></span>

### <a name="a--bool"></a><span data-ttu-id="2b148-108">a: [bool](xref:microsoft.quantum.lang-ref.bool)[]</span><span class="sxs-lookup"><span data-stu-id="2b148-108">a : [Bool](xref:microsoft.quantum.lang-ref.bool)[]</span></span>





## <a name="output--bigint"></a><span data-ttu-id="2b148-109">Ausgabe: [bigint](xref:microsoft.quantum.lang-ref.bigint)</span><span class="sxs-lookup"><span data-stu-id="2b148-109">Output : [BigInt](xref:microsoft.quantum.lang-ref.bigint)</span></span>



## <a name="remarks"></a><span data-ttu-id="2b148-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="2b148-110">Remarks</span></span>

<span data-ttu-id="2b148-111">Weitere Informationen finden Sie unter [c# BigInteger-Konstruktor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) .</span><span class="sxs-lookup"><span data-stu-id="2b148-111">See [C# BigInteger constructor](https://docs.microsoft.com/dotnet/api/system.numerics.biginteger.-ctor?view=netframework-4.7.2#System_Numerics_BigInteger__ctor_System_Int64_) for more details.</span></span>