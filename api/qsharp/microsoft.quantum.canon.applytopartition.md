---
uid: Microsoft.Quantum.Canon.ApplyToPartition
title: Applytopartition-Vorgang
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToPartition
qsharp.summary: Applies a pair of operations to a given partition of a register into two parts.
ms.openlocfilehash: a0dc3453e7501816132569869e858418d5f3f4e5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850539"
---
# <a name="applytopartition-operation"></a>Applytopartition-Vorgang

Namespace: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wendet ein paar von Vorgängen auf eine bestimmte Partition eines Registers in zwei Teilen an.

```qsharp
operation ApplyToPartition (op : ((Qubit[], Qubit[]) => Unit), numberOfQubitsToFirstArgument : Int, target : Qubit[]) : Unit
```


## <a name="input"></a>Eingabe

### <a name="op--qubitqubit--unit"></a>OP: ([Qubit](xref:microsoft.quantum.lang-ref.qubit)[],[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Einheit](xref:microsoft.quantum.lang-ref.unit) 

Das auf die angegebene Partition anzuwendende paar von Vorgängen.


### <a name="numberofqubitstofirstargument--int"></a>numofqubitstofirstargument: [int](xref:microsoft.quantum.lang-ref.int)

Anzahl der Qubits aus dem Ziel, die in den ersten Teil der Partition eingefügt werden sollen.
Die restlichen Qubits bilden den zweiten Teil der Partition.


### <a name="target--qubit"></a>Ziel: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ein Register von Qubits, die durch den angegebenen zwei Vorgang partitioniert und verarbeitet werden.



## <a name="output--unit"></a>Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Weitere Informationen

- [Microsoft. Quantum. Canon. applytopartitiona](xref:Microsoft.Quantum.Canon.ApplyToPartitionA)
- [Microsoft. Quantum. Canon. applytopartitionc](xref:Microsoft.Quantum.Canon.ApplyToPartitionC)
- [Microsoft. Quantum. Canon. applytopartitionca](xref:Microsoft.Quantum.Canon.ApplyToPartitionCA)