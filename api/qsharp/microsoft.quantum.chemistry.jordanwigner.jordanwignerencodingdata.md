---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData
title: Benutzerdefinierter Typ "jordanwignerencodingdata"
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerEncodingData
qsharp.summary: Format of data passed from C# to Q# to represent all information for Hamiltonian simulation. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 5a0d886b5c868de5a8bb435a88f30739288ff69e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98838989"
---
# <a name="jordanwignerencodingdata-user-defined-type"></a>Benutzerdefinierter Typ "jordanwignerencodingdata"

Namespace: [Microsoft. Quantum. Chemistry. jordanwigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Paket: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format der Daten, die von c# an Q # übergeben werden, um alle Informationen für die hamiltonan-Simulation darzustellen.
Die Bedeutung der dargestellten Daten wird durch den Algorithmus bestimmt, der Sie empfängt.

```qsharp

newtype JordanWignerEncodingData = (Int, Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms, (Int, Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]), Double);
```

