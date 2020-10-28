---
uid: Microsoft.Quantum.Random.SampleTransformedContinuousDistribution
title: Sampletransformedcontinuousdistribution-Vorgang
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: SampleTransformedContinuousDistribution
qsharp.summary: Internal-only operation for sampling from transformed distributions. Should only be used via partial application.
ms.openlocfilehash: dc93022e53199cd8ef794da9c1590d6997a0fda1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723970"
---
# <a name="sampletransformedcontinuousdistribution-operation"></a><span data-ttu-id="e8a2b-102">Sampletransformedcontinuousdistribution-Vorgang</span><span class="sxs-lookup"><span data-stu-id="e8a2b-102">SampleTransformedContinuousDistribution operation</span></span>

<span data-ttu-id="e8a2b-103">Namespace: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)</span><span class="sxs-lookup"><span data-stu-id="e8a2b-103">Namespace: [Microsoft.Quantum.Random](xref:Microsoft.Quantum.Random)</span></span>

<span data-ttu-id="e8a2b-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="e8a2b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="e8a2b-105">Interner Vorgang für die Stichprobenentnahme aus transformierten Verteilungen.</span><span class="sxs-lookup"><span data-stu-id="e8a2b-105">Internal-only operation for sampling from transformed distributions.</span></span>
<span data-ttu-id="e8a2b-106">Sollte nur über eine partielle Anwendung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e8a2b-106">Should only be used via partial application.</span></span>

```qsharp
operation SampleTransformedContinuousDistribution (transform : (Double -> Double), distribution : Microsoft.Quantum.Random.ContinuousDistribution) : Double
```


## <a name="input"></a><span data-ttu-id="e8a2b-107">Eingabe</span><span class="sxs-lookup"><span data-stu-id="e8a2b-107">Input</span></span>

### <a name="transform--double---double"></a><span data-ttu-id="e8a2b-108">Transformation: [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8a2b-108">transform : [Double](xref:microsoft.quantum.lang-ref.double) -> [Double](xref:microsoft.quantum.lang-ref.double)</span></span>




### <a name="distribution--continuousdistribution"></a><span data-ttu-id="e8a2b-109">Verteilung: [continuousdistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span><span class="sxs-lookup"><span data-stu-id="e8a2b-109">distribution : [ContinuousDistribution](xref:Microsoft.Quantum.Random.ContinuousDistribution)</span></span>





## <a name="output--double"></a><span data-ttu-id="e8a2b-110">Ausgabe: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="e8a2b-110">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>
