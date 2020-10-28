---
uid: Microsoft.Quantum.Intrinsic.R1
title: R1-Vorgang
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: R1
qsharp.summary: >-
  Applies a rotation about the $\ket{1}$ state by a given angle.

  \begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}). \end{align}
ms.openlocfilehash: 87302a4338af144ee6a8cec83ed1803581597482
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92707143"
---
# <a name="r1-operation"></a><span data-ttu-id="55183-102">R1-Vorgang</span><span class="sxs-lookup"><span data-stu-id="55183-102">R1 operation</span></span>

<span data-ttu-id="55183-103">Namespace: [Microsoft. Quantum. intrinsisch](xref:Microsoft.Quantum.Intrinsic)</span><span class="sxs-lookup"><span data-stu-id="55183-103">Namespace: [Microsoft.Quantum.Intrinsic](xref:Microsoft.Quantum.Intrinsic)</span></span>

<span data-ttu-id="55183-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="55183-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="55183-105">Wendet eine Drehung um den $ \ket {1} $-Zustand um einen angegebenen Winkel an.</span><span class="sxs-lookup"><span data-stu-id="55183-105">Applies a rotation about the $\ket{1}$ state by a given angle.</span></span>

<span data-ttu-id="55183-106">\begin{align} R_1 (\orta) \mathrel{: =} \operatorname{Diag} (1, e ^ {i\der TA}).</span><span class="sxs-lookup"><span data-stu-id="55183-106">\begin{align} R_1(\theta) \mathrel{:=} \operatorname{diag}(1, e^{i\theta}).</span></span>
<span data-ttu-id="55183-107">\end{align}</span><span class="sxs-lookup"><span data-stu-id="55183-107">\end{align}</span></span>

```qsharp
operation R1 (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="55183-108">Eingabe</span><span class="sxs-lookup"><span data-stu-id="55183-108">Input</span></span>

### <a name="theta--double"></a><span data-ttu-id="55183-109">-Ta: [Double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="55183-109">theta : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="55183-110">Der Winkel, um den das Qubit gedreht werden soll.</span><span class="sxs-lookup"><span data-stu-id="55183-110">Angle about which the qubit is to be rotated.</span></span>


### <a name="qubit--qubit"></a><span data-ttu-id="55183-111">Qubit: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="55183-111">qubit : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="55183-112">Das Qubit, auf das das Gate angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="55183-112">Qubit to which the gate should be applied.</span></span>



## <a name="output--unit"></a><span data-ttu-id="55183-113">Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="55183-113">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="55183-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="55183-114">Remarks</span></span>

<span data-ttu-id="55183-115">Äquivalent zu:</span><span class="sxs-lookup"><span data-stu-id="55183-115">Equivalent to:</span></span>

```qsharp
R(PauliZ, theta, qubit);
R(PauliI, -theta, qubit);
```