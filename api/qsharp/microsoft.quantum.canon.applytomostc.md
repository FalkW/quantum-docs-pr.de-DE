---
uid: Microsoft.Quantum.Canon.ApplyToMostC
title: Applytomostc-Vorgang
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApplyToMostC
qsharp.summary: Applies an operation to all but the last element of an array.
ms.openlocfilehash: 14de9f367aa7d19f64f13186d402239ae1fef3c1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850558"
---
# <a name="applytomostc-operation"></a>Applytomostc-Vorgang

Namespace: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Paket: [Microsoft. Quantum. Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Wendet einen Vorgang auf alle bis auf das letzte Element eines Arrays an.

```qsharp
operation ApplyToMostC<'T> (op : ('T[] => Unit is Ctl), targets : 'T[]) : Unit is Ctl
```


## <a name="description"></a>Beschreibung

Bei einem Vorgang `op` und einem Array von Zielen `targets` gilt `op(Most(targets))` .

## <a name="input"></a>Eingabe

### <a name="op--t--unit--is-ctl"></a>OP: 't [] => [Einheit](xref:microsoft.quantum.lang-ref.unit)  ist CTL

Ein anzuwendende Vorgang.


### <a name="targets--t"></a>Ziele: 't []

Ein Array von Zielen, von denen alle außer der letzten angewendet werden `op` .



## <a name="output--unit"></a>Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)



## <a name="type-parameters"></a>Typparameter

### <a name="t"></a>GIF

Der Eingabetyp des Vorgangs, der angewendet werden soll.

## <a name="see-also"></a>Weitere Informationen

- [Microsoft. Quantum. Canon. applytomost](xref:Microsoft.Quantum.Canon.ApplyToMost)
- [Microsoft. Quantum. Canon. applytomosta](xref:Microsoft.Quantum.Canon.ApplyToMostA)
- [Microsoft. Quantum. Canon. applytomostca](xref:Microsoft.Quantum.Canon.ApplyToMostCA)