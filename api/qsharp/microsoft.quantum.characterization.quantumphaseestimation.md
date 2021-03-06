---
uid: Microsoft.Quantum.Characterization.QuantumPhaseEstimation
title: Quantrephaseschätzungsvorgang
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: QuantumPhaseEstimation
qsharp.summary: Performs the quantum phase estimation algorithm for a given oracle `U` and `targetState`, reading the phase into a big-endian quantum register.
ms.openlocfilehash: 4bdf3de9dab20fa97ba47f15efec4b41a10709f3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839662"
---
# <a name="quantumphaseestimation-operation"></a>Quantrephaseschätzungsvorgang

Namespace: [Microsoft. Quantum. Charakterisierung](xref:Microsoft.Quantum.Characterization)

Paket: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Führt den Algorithmus für die Quantum-Phasen Schätzung für ein bestimmtes Oracle `U` und aus `targetState` , wobei die Phase in ein Big-in-Quantum-Quantum-Register gelesen wird.

```qsharp
operation QuantumPhaseEstimation (oracle : Microsoft.Quantum.Oracles.DiscreteOracle, targetState : Qubit[], controlRegister : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Eingabe

### <a name="oracle--discreteoracle"></a>Oracle: [diskreteoracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Ein Vorgang, der $U ^ m $ für die angegebenen ganzzahligen Kräfte m implementiert.


### <a name="targetstate--qubit"></a>targetState: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Ein Quantum-Register, das den Status $ \ket{\phi} $ darstellt, der durch $U $ bearbeitet wurde. Wenn $ \ket{\phi} $ ein eigen Status von $U $ ist, $U \ket{\phi} = e ^ {i\phi} \ket{\phi} $ für $ \phi \in [0,0 \ PI) $ eine unbekannte Phase.


### <a name="controlregister--bigendian"></a>controlregister: [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Ein ganzzahliges Register für eine Big-Endian-Darstellung, das verwendet werden kann, um das angegebene Oracle zu steuern, und das eine Darstellung von $ \phi $ nach der Anwendung dieses Vorgangs enthält. Es wird davon ausgegangen, dass das controlregister im ursprünglichen Zustand $ \ket{00\cdots 0} $ beginnt, wobei die Länge des Registers die gewünschte Genauigkeit angibt.



## <a name="output--unit"></a>Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)

