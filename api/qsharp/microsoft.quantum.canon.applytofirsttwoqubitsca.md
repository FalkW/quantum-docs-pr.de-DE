---
uid: Microsoft.Quantum.Canon.ApplyToFirstTwoQubitsCA
title: Applydefirsttwoqubitsca-Vorgang
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToFirstTwoQubitsCA
qsharp.summary: Applies an operation to the first two qubits in the register. The modifier `CA` indicates that the operation is controllable and adjointable.
ms.openlocfilehash: 5bea9ec1be1fc379823877684c81e99f86807d89
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850660"
---
# <a name="applytofirsttwoqubitsca-operation"></a>Applydefirsttwoqubitsca-Vorgang

Namespace: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wendet einen Vorgang auf die ersten beiden Qubits im Register an.
Der-Modifizierer `CA` gibt an, dass der Vorgang steuerbar und adjointable ist.

```qsharp
operation ApplyToFirstTwoQubitsCA (op : ((Qubit, Qubit) => Unit is Adj + Ctl), register : Qubit[]) : Unit is Adj + Ctl
```


## <a name="input"></a>Eingabe

### <a name="op--qubitqubit--unit--is-adj--ctl"></a>OP: ([Qubit](xref:microsoft.quantum.lang-ref.qubit),[Qubit](xref:microsoft.quantum.lang-ref.qubit)) => [Einheit](xref:microsoft.quantum.lang-ref.unit)  ist ADJ + CTL

Ein Vorgang, der auf die ersten beiden Qubits angewendet werden soll.


### <a name="register--qubit"></a>Register: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Qubit-Array zu den ersten zwei Qubits, auf die der Vorgang angewendet wird.



## <a name="output--unit"></a>Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Bemerkungen

Das entspricht:

```qsharp
op(register[0], register[1]);
```

## <a name="see-also"></a>Weitere Informationen

- [Microsoft. Quantum. Canon. applyjefirsttwoqubits](xref:Microsoft.Quantum.Canon.ApplyToFirstTwoQubits)