---
uid: Microsoft.Quantum.Arrays.Zip3
title: Zip3-Funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Zip3
qsharp.summary: >-
  > [!WARNING]

  > Zip3 has been deprecated. Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.


  Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.
ms.openlocfilehash: f4b1a769614ee9434b2141b8fcb91f34cd071bdb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705679"
---
# <a name="zip3-function"></a><span data-ttu-id="bc038-102">Zip3-Funktion</span><span class="sxs-lookup"><span data-stu-id="bc038-102">Zip3 function</span></span>

<span data-ttu-id="bc038-103">Namespace: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)</span><span class="sxs-lookup"><span data-stu-id="bc038-103">Namespace: [Microsoft.Quantum.Arrays](xref:Microsoft.Quantum.Arrays)</span></span>

<span data-ttu-id="bc038-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bc038-104">Package: [](https://nuget.org/packages/)</span></span>


> [!WARNING]
> <span data-ttu-id="bc038-105">Zip3 wurde als veraltet markiert.</span><span class="sxs-lookup"><span data-stu-id="bc038-105">Zip3 has been deprecated.</span></span> <span data-ttu-id="bc038-106">Verwenden Sie stattdessen <xref:Microsoft.Quantum.Arrays.Zipped3>.</span><span class="sxs-lookup"><span data-stu-id="bc038-106">Please use <xref:Microsoft.Quantum.Arrays.Zipped3> instead.</span></span>

<span data-ttu-id="bc038-107">Bei drei Arrays gibt ein neues Array von 3-Tupeln zurück, sodass jedes 3-Tupel ein Element aus jedem ursprünglichen Array enthält.</span><span class="sxs-lookup"><span data-stu-id="bc038-107">Given three arrays, returns a new array of 3-tuples such that each 3-tuple contains an element from each original array.</span></span>

```qsharp
function Zip3<'T1, 'T2, 'T3> (first : 'T1[], second : 'T2[], third : 'T3[]) : ('T1, 'T2, 'T3)[]
```


## <a name="input"></a><span data-ttu-id="bc038-108">Eingabe</span><span class="sxs-lookup"><span data-stu-id="bc038-108">Input</span></span>

### <a name="first--t1"></a><span data-ttu-id="bc038-109">zuerst: 't 1 []</span><span class="sxs-lookup"><span data-stu-id="bc038-109">first : 'T1[]</span></span>

<span data-ttu-id="bc038-110">Ein Array, das Werte für das erste Element jedes Tupels enthält.</span><span class="sxs-lookup"><span data-stu-id="bc038-110">An array containing values for the first element of each tuple.</span></span>


### <a name="second--t2"></a><span data-ttu-id="bc038-111">Zweitens: 't 2 []</span><span class="sxs-lookup"><span data-stu-id="bc038-111">second : 'T2[]</span></span>

<span data-ttu-id="bc038-112">Ein Array, das Werte für das zweite Element jedes Tupels enthält.</span><span class="sxs-lookup"><span data-stu-id="bc038-112">An array containing values for the second element of each tuple.</span></span>


### <a name="third--t3"></a><span data-ttu-id="bc038-113">Drittens: 't 3 []</span><span class="sxs-lookup"><span data-stu-id="bc038-113">third : 'T3[]</span></span>

<span data-ttu-id="bc038-114">Ein Array, das Werte für das dritte Element jedes Tupels enthält.</span><span class="sxs-lookup"><span data-stu-id="bc038-114">An array containing values for the third element of each tuple.</span></span>



## <a name="output--t1t2t3"></a><span data-ttu-id="bc038-115">Ausgabe: ('t 1, 't 2, 't 3) []</span><span class="sxs-lookup"><span data-stu-id="bc038-115">Output : ('T1,'T2,'T3)[]</span></span>

<span data-ttu-id="bc038-116">Ein Array, das jeweils 3 Tupel des Formulars enthält `(first[idx], second[idx], third[idx])` `idx` .</span><span class="sxs-lookup"><span data-stu-id="bc038-116">An array containing 3-tuples of the form `(first[idx], second[idx], third[idx])` for each `idx`.</span></span> <span data-ttu-id="bc038-117">Wenn die drei Arrays nicht die gleiche Länge aufweisen, ist die Ausgabe so lang wie die kürzere der Eingaben.</span><span class="sxs-lookup"><span data-stu-id="bc038-117">If the three arrays are not of equal length, the output will be as long as the shorter of the inputs.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="bc038-118">Typparameter</span><span class="sxs-lookup"><span data-stu-id="bc038-118">Type Parameters</span></span>

### <a name="t1"></a><span data-ttu-id="bc038-119">Nicht 1</span><span class="sxs-lookup"><span data-stu-id="bc038-119">'T1</span></span>

<span data-ttu-id="bc038-120">Der Typ der ersten Array Elemente.</span><span class="sxs-lookup"><span data-stu-id="bc038-120">The type of the first array elements.</span></span>
### <a name="t2"></a><span data-ttu-id="bc038-121">Nicht 2</span><span class="sxs-lookup"><span data-stu-id="bc038-121">'T2</span></span>

<span data-ttu-id="bc038-122">Der Typ der zweiten Array Elemente.</span><span class="sxs-lookup"><span data-stu-id="bc038-122">The type of the second array elements.</span></span>
### <a name="t3"></a><span data-ttu-id="bc038-123">Nicht 3</span><span class="sxs-lookup"><span data-stu-id="bc038-123">'T3</span></span>

<span data-ttu-id="bc038-124">Der Typ der dritten Array Elemente.</span><span class="sxs-lookup"><span data-stu-id="bc038-124">The type of the third array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc038-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc038-125">See Also</span></span>

- [<span data-ttu-id="bc038-126">Microsoft.Quantum.Arrays.Zip</span><span class="sxs-lookup"><span data-stu-id="bc038-126">Microsoft.Quantum.Arrays.Zip</span></span>](xref:Microsoft.Quantum.Arrays.Zip)
- [<span data-ttu-id="bc038-127">Microsoft.Quantum.Arrays.Zip4</span><span class="sxs-lookup"><span data-stu-id="bc038-127">Microsoft.Quantum.Arrays.Zip4</span></span>](xref:Microsoft.Quantum.Arrays.Zip4)