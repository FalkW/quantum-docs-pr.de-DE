---
uid: Microsoft.Quantum.AmplitudeAmplification.StandardAmplitudeAmplification
title: Standardamplituentverstärkungsfunktion
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: StandardAmplitudeAmplification
qsharp.summary: Standard Amplitude Amplification algorithm
ms.openlocfilehash: 984bfee89b6d79750228b8ca6aaf404f58aecd41
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98843928"
---
# <a name="standardamplitudeamplification-function"></a>Standardamplituentverstärkungsfunktion

Namespace: [Microsoft. Quantum. Verstärkungs Verstärkung](xref:Microsoft.Quantum.AmplitudeAmplification)

Paket: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Standard mäßiger Amplitude-Verstärkungs Algorithmus

```qsharp
function StandardAmplitudeAmplification (nIterations : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle, idxFlagQubit : Int) : (Qubit[] => Unit is Adj + Ctl)
```


## <a name="input"></a>Eingabe

### <a name="niterations--int"></a>niterationen: [int](xref:microsoft.quantum.lang-ref.int)

Anzahl der Iterationen $n $ der Amplitude-Verstärkung


### <a name="stateoracle--stateoracle"></a>stateoracle: [stateoracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Einheitlicher Oracle-$A $, der den Startstatus vorbereitet


### <a name="idxflagqubit--int"></a>idxflagqubit: [int](xref:microsoft.quantum.lang-ref.int)

Index zum Markieren von Qubit



## <a name="output--qubit--unit--is-adj--ctl"></a>Ausgabe: [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Einheit](xref:microsoft.quantum.lang-ref.unit)  ist ADJ + CTL

Ein Vorgang, der den standardmäßigen Amplitude-Verstärkungs Algorithmus implementiert.

## <a name="remarks"></a>Bemerkungen

Dies ist der standardmäßige Amplitude-Verstärkungs Algorithmus, der durch eine Auswahl von Reflexionsphasen erzielt wird, die durch `AmpAmpPhasesStandard` die Annahme berechnet werden, dass "\begin{align} a\ket {0} \_ {f} \ket {0} \_ s = \lambda\ket {1} \_ f \ket {\ Text {Target}} \_ s + \sqrt{1-| \lambda | ^ 2} \ket- {0} \_ \end{align} dieser Vorgang bereitet den Status" \begin{align} \operatorname{AmpAmpByOracle}\ket {0} \_ {f} \ket {0} \_ s = \sin ((2n + 1) \sin ^ {-1} (\lambda)) \ket {1} \_ f \ket {\ Text {Target}} \_ s + \cdoz\ket {0} \_ f \end{align} "in den meisten Fällen vor. `flagQubit` und werden `auxiliaryRegister` im Zustand" $ \ket {0} \_ f \ket {0} \_ a $ "initialisiert.

## <a name="references"></a>References

- [*G. Brassard, P. Hoyer, M. Musca, A. Tapp*](https://arxiv.org/abs/quant-ph/0005055)