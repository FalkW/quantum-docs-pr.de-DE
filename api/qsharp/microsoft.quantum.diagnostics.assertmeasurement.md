---
uid: Microsoft.Quantum.Diagnostics.AssertMeasurement
title: Assertmeasurement-Vorgang
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertMeasurement
qsharp.summary: Asserts that measuring the given qubits in the given Pauli basis will always have the given result.
ms.openlocfilehash: 09024cd8cd6e713360dcf7f42f55941590f35883
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702780"
---
# <a name="assertmeasurement-operation"></a><span data-ttu-id="a38fa-102">Assertmeasurement-Vorgang</span><span class="sxs-lookup"><span data-stu-id="a38fa-102">AssertMeasurement operation</span></span>

<span data-ttu-id="a38fa-103">Namespace: [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span><span class="sxs-lookup"><span data-stu-id="a38fa-103">Namespace: [Microsoft.Quantum.Diagnostics](xref:Microsoft.Quantum.Diagnostics)</span></span>

<span data-ttu-id="a38fa-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="a38fa-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="a38fa-105">Bestätigt, dass das Messen der angegebenen Qubits in der angegebenen Pauli-Basis immer das angegebene Ergebnis hat.</span><span class="sxs-lookup"><span data-stu-id="a38fa-105">Asserts that measuring the given qubits in the given Pauli basis will always have the given result.</span></span>

```qsharp
operation AssertMeasurement (bases : Pauli[], qubits : Qubit[], result : Result, msg : String) : Unit
```


## <a name="input"></a><span data-ttu-id="a38fa-106">Eingabe</span><span class="sxs-lookup"><span data-stu-id="a38fa-106">Input</span></span>

### <a name="bases--pauli"></a><span data-ttu-id="a38fa-107">Basen: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span><span class="sxs-lookup"><span data-stu-id="a38fa-107">bases : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]</span></span>

<span data-ttu-id="a38fa-108">Ein Maßeffekt zur Bestätigung der Wahrscheinlichkeit von, ausgedrückt als Multi-Qubit-Pauli-Operator.</span><span class="sxs-lookup"><span data-stu-id="a38fa-108">A measurement effect to assert the probability of, expressed as a multi-qubit Pauli operator.</span></span>


### <a name="qubits--qubit"></a><span data-ttu-id="a38fa-109">Qubits: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span><span class="sxs-lookup"><span data-stu-id="a38fa-109">qubits : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]</span></span>

<span data-ttu-id="a38fa-110">Ein Register, für das die-Assertion durchführen werden soll.</span><span class="sxs-lookup"><span data-stu-id="a38fa-110">A register on which to make the assertion.</span></span>


### <a name="result--__invalidresult__"></a><span data-ttu-id="a38fa-111">Ergebnis: __ungültig <Result>__</span><span class="sxs-lookup"><span data-stu-id="a38fa-111">result : __invalid<Result>__</span></span>

<span data-ttu-id="a38fa-112">Das erwartete Ergebnis von `Measure(bases, qubits)` .</span><span class="sxs-lookup"><span data-stu-id="a38fa-112">The expected result of `Measure(bases, qubits)`.</span></span>


### <a name="msg--string"></a><span data-ttu-id="a38fa-113">msg: [Zeichenfolge](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="a38fa-113">msg : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="a38fa-114">Eine Meldung, die gemeldet werden soll, wenn die Übersetzung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="a38fa-114">A message to be reported if the assertion fails.</span></span>



## <a name="output--unit"></a><span data-ttu-id="a38fa-115">Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="a38fa-115">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="a38fa-116">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a38fa-116">Remarks</span></span>

<span data-ttu-id="a38fa-117">Beachten Sie, dass die unter-und kontrollierten Versionen dieses Vorgangs die Bedingung nicht überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a38fa-117">Note that the Adjoint and Controlled versions of this operation will not check the condition.</span></span>

## <a name="see-also"></a><span data-ttu-id="a38fa-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a38fa-118">See Also</span></span>

- [<span data-ttu-id="a38fa-119">Microsoft. Quantum. Diagnostics. assertmessrementwahrscheinlichkeits</span><span class="sxs-lookup"><span data-stu-id="a38fa-119">Microsoft.Quantum.Diagnostics.AssertMeasurementProbability</span></span>](xref:Microsoft.Quantum.Diagnostics.AssertMeasurementProbability)