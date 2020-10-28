---
uid: Microsoft.Quantum.Canon.ApplyControlledOnInt
title: Applycontrolledonint-Vorgang
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyControlledOnInt
qsharp.summary: Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.
ms.openlocfilehash: c8ea76946143967de4b6ac65986a1c4407ecb633
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705431"
---
# <a name="applycontrolledonint-operation"></a><span data-ttu-id="f4595-102">Applycontrolledonint-Vorgang</span><span class="sxs-lookup"><span data-stu-id="f4595-102">ApplyControlledOnInt operation</span></span>

<span data-ttu-id="f4595-103">Namespace: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="f4595-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="f4595-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="f4595-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="f4595-105">Wendet einen einheitlichen Vorgang auf das Ziel Register an, wenn der Steuerelement Registrierungs Zustand einer angegebenen positiven ganzen Zahl entspricht.</span><span class="sxs-lookup"><span data-stu-id="f4595-105">Applies a unitary operation on the target register if the control register state corresponds to a specified positive integer.</span></span>

```qsharp
operation ApplyControlledOnInt<'T> (numberState : Int, oracle : ('T => Unit is Adj + Ctl), controlRegister : Qubit[], targetRegister : 'T) : Unit
```


## <a name="input"></a><span data-ttu-id="f4595-106">Eingabe</span><span class="sxs-lookup"><span data-stu-id="f4595-106">Input</span></span>

### <a name="numberstate--int"></a><span data-ttu-id="f4595-107">numstate: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="f4595-107">numberState : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="f4595-108">Eine nicht negative ganze Zahl, für die der Vorgang `oracle` gesteuert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4595-108">A nonnegative integer on which the operation `oracle` should be controlled.</span></span>


### <a name="oracle--t--unit-adj--ctl"></a><span data-ttu-id="f4595-109">Oracle: 't => [Unit](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL</span><span class="sxs-lookup"><span data-stu-id="f4595-109">oracle : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="f4595-110">Ein einheitlicher Vorgang, der gesteuert werden soll.</span><span class="sxs-lookup"><span data-stu-id="f4595-110">A unitary operation to be controlled.</span></span>


### <a name="controlregister--qubit"></a><span data-ttu-id="f4595-111">controlregister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="f4595-111">controlRegister : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="f4595-112">Ein Quantum-Register, das die Anwendung von steuert `oracle` .</span><span class="sxs-lookup"><span data-stu-id="f4595-112">A quantum register that controls application of `oracle`.</span></span>


### <a name="targetregister--t"></a><span data-ttu-id="f4595-113">targetregiester: 't</span><span class="sxs-lookup"><span data-stu-id="f4595-113">targetRegister : 'T</span></span>

<span data-ttu-id="f4595-114">Ein Register, das angewendet werden soll `oracle` .</span><span class="sxs-lookup"><span data-stu-id="f4595-114">A register on which to apply `oracle`.</span></span>



## <a name="output--unit"></a><span data-ttu-id="f4595-115">Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="f4595-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="f4595-116">Typparameter</span><span class="sxs-lookup"><span data-stu-id="f4595-116">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="f4595-117">GIF</span><span class="sxs-lookup"><span data-stu-id="f4595-117">'T</span></span>



## <a name="remarks"></a><span data-ttu-id="f4595-118">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f4595-118">Remarks</span></span>

<span data-ttu-id="f4595-119">Der Wert von `numberState` wird mithilfe einer Little-enumdian-Codierung interpretiert.</span><span class="sxs-lookup"><span data-stu-id="f4595-119">The value of `numberState` is interpreted using a little-endian encoding.</span></span>

<span data-ttu-id="f4595-120">`numberState` muss höchstens $2 ^ \texttt{length (controlregister)}-$1.</span><span class="sxs-lookup"><span data-stu-id="f4595-120">`numberState` must be at most $2^\texttt{Length(controlRegister)} - 1$.</span></span>
<span data-ttu-id="f4595-121">Beispielsweise `numberState = 537` bedeutet, dass `oracle` nur dann angewendet wird, wenn `controlRegister` sich im Zustand $ \ket {537} $ befindet.</span><span class="sxs-lookup"><span data-stu-id="f4595-121">For example, `numberState = 537` means that `oracle` is applied if and only if `controlRegister` is in the state $\ket{537}$.</span></span>