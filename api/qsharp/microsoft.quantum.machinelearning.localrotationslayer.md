---
uid: Microsoft.Quantum.MachineLearning.LocalRotationsLayer
title: Localrotationslayer-Funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: LocalRotationsLayer
qsharp.summary: Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.
ms.openlocfilehash: 8a3557f76d5d7a7b6375e5640cf6d11172cd38a6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723466"
---
# <a name="localrotationslayer-function"></a><span data-ttu-id="08086-102">Localrotationslayer-Funktion</span><span class="sxs-lookup"><span data-stu-id="08086-102">LocalRotationsLayer function</span></span>

<span data-ttu-id="08086-103">Namespace: [Microsoft. Quantum. machinelearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="08086-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="08086-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="08086-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="08086-105">Gibt ein Array von unkontrollierten Rotationen (Single-Qubit) entlang einer angegebenen Achse zurück, wobei für jedes Qubit in einem Register eine Drehung durch unterschiedliche Modellparameter parametrisiert ist.</span><span class="sxs-lookup"><span data-stu-id="08086-105">Returns an array of uncontrolled (single-qubit) rotations along a given axis, with one rotation for each qubit in a register, parameterized by distinct model parameters.</span></span>

```qsharp
function LocalRotationsLayer (nQubits : Int, axis : Pauli) : Microsoft.Quantum.MachineLearning.ControlledRotation[]
```


## <a name="input"></a><span data-ttu-id="08086-106">Eingabe</span><span class="sxs-lookup"><span data-stu-id="08086-106">Input</span></span>

### <a name="nqubits--int"></a><span data-ttu-id="08086-107">nqubits: [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="08086-107">nQubits : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="08086-108">Die Anzahl der Qubits, die durch die angegebene Ebene bearbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="08086-108">The number of qubits acted on by the given layer.</span></span>


### <a name="axis--pauli"></a><span data-ttu-id="08086-109">Achse: [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="08086-109">axis : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="08086-110">Die Drehungs Achse für jede Drehung in der angegebenen Ebene.</span><span class="sxs-lookup"><span data-stu-id="08086-110">The rotation axis for each rotation in the given layer.</span></span>



## <a name="output--controlledrotation"></a><span data-ttu-id="08086-111">Ausgabe: [controlledrotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span><span class="sxs-lookup"><span data-stu-id="08086-111">Output : [ControlledRotation](xref:Microsoft.Quantum.MachineLearning.ControlledRotation)[]</span></span>

<span data-ttu-id="08086-112">Ein Array von kontrollierten Rotationen für die angegebene Achse, eines auf jedem der `nQubits` Qubits.</span><span class="sxs-lookup"><span data-stu-id="08086-112">An array of controlled rotations about the given axis, one on each of `nQubits` qubits.</span></span>