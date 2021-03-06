---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable
title: Applyxcontrolledontruthtable-Vorgang
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTable
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: 6e956038f7cd15db7348ff830da8bc9eae53aa61
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855560"
---
# <a name="applyxcontrolledontruthtable-operation"></a>Applyxcontrolledontruthtable-Vorgang

Namespace: [Microsoft. Quantum. Synthese](xref:Microsoft.Quantum.Synthesis)

Paket: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wendet den @"microsoft.quantum.intrinsic.x" Vorgang auf an `target` , wenn die boolesche Funktion `func` für die klassische Zuweisung in als true ausgewertet wird `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTable (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit is Adj + Ctl
```


## <a name="description"></a>Beschreibung

Der Vorgang implementiert den einheitlichen Vorgang \begin{align} u\ket {x} \ Ket {y} = \ket{x}\ket{y \oplus f (x)} \end{align}, wobei $x $ und $y $ `controlRegister` `target` bzw. darstellen.

Die boolesche Funktion $f $ wird als Wahrheitstabelle in Bezug auf eine große ganze Zahl dargestellt.
Beispielsweise wird die Mehrheits Funktion für drei Eingaben durch das bitstring dargestellt `11101000` , wobei das signifikanteste Bit `1` der Eingabe Zuweisung entspricht `(1, 1, 1)` , und das am wenigsten bedeutende Bit `0` entspricht der Eingabe Zuweisung `(0, 0, 0)` .
Sie kann durch die große ganze Zahl `0xE8L` in Hexadezimal Schreibweise oder als Dezimal Schreibweise dargestellt werden `232L` .  Das- `L` Suffix gibt an, dass die Konstante vom Typ ist `BigInt` .
Weitere Informationen zu dieser Darstellung finden Sie auch in den [Wahrheitstabellen Kata](https://github.com/microsoft/QuantumKatas/tree/main/TruthTables).

Die-Implementierung nutzt @"microsoft.quantum.intrinsic.cnot" und @"microsoft.quantum.intrinsic.r1" Gates.

## <a name="input"></a>Eingabe

### <a name="func--bigint"></a>Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Boolesche Wahrheitstabelle, dargestellt als große ganze Zahl


### <a name="controlregister--qubit"></a>controlregister: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Register von Steuerungs Qubits


### <a name="target--qubit"></a>Ziel: [Qubit](xref:microsoft.quantum.lang-ref.qubit)

Ziel-Qubit



## <a name="output--unit"></a>Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>References

- [*N. Schuch*, *J. Siewert*, PRL 91, No. 027902, 2003, arXiv: quant-ph/0303063](https://arxiv.org/abs/quant-ph/0303063)
- [*Mathias soeken*, *Martin roetteler*, arXiv: 2005.12310](https://arxiv.org/abs/2005.12310)

## <a name="see-also"></a>Weitere Informationen

- [Microsoft. Quantum. Synthese. applyxcontrolledontruthtablewithcleantarget](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget)