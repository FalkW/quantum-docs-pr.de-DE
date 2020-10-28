---
uid: Microsoft.Quantum.ErrorCorrection.FiveQubitCodeRecoveryFn
title: "\"Fvequbitcoderecoveryfn\"-Funktion"
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: FiveQubitCodeRecoveryFn
qsharp.summary: Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.
ms.openlocfilehash: 5b8afe222d197eb7d342ac45f027f2de9130b61a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702479"
---
# <a name="fivequbitcoderecoveryfn-function"></a><span data-ttu-id="25287-102">"Fvequbitcoderecoveryfn"-Funktion</span><span class="sxs-lookup"><span data-stu-id="25287-102">FiveQubitCodeRecoveryFn function</span></span>

<span data-ttu-id="25287-103">Namespace: [Microsoft. Quantum. errorcorrection](xref:Microsoft.Quantum.ErrorCorrection)</span><span class="sxs-lookup"><span data-stu-id="25287-103">Namespace: [Microsoft.Quantum.ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)</span></span>

<span data-ttu-id="25287-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="25287-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="25287-105">Gibt eine Funktion zurück, die Fehler-Syndrom-Messungen den entsprechenden Fehler Behebungs-Pauli-Operatoren durch die Tabellen Suche für den ⟦ 5, 1, 3 ⟧ Quantum-Code zuordnet.</span><span class="sxs-lookup"><span data-stu-id="25287-105">Returns function that maps error syndrome measurements to the appropriate error-correcting Pauli operators by table lookup for the ⟦5, 1, 3⟧ quantum code.</span></span>

```qsharp
function FiveQubitCodeRecoveryFn () : Microsoft.Quantum.ErrorCorrection.RecoveryFn
```


## <a name="output--recoveryfn"></a><span data-ttu-id="25287-106">Ausgabe: [Wiederherstellbarkeits-FN](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span><span class="sxs-lookup"><span data-stu-id="25287-106">Output : [RecoveryFn](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)</span></span>

<span data-ttu-id="25287-107">Funktion des Typs `RecoveryFn` , die eine Messungs Messung annimmt `Result[]` und die `Pauli[]` Operatoren zurückgibt, die den erkannten Fehler korrigieren.</span><span class="sxs-lookup"><span data-stu-id="25287-107">Function of type `RecoveryFn` that takes a syndrome measurement `Result[]` and returns the `Pauli[]` operators that corrects the detected error.</span></span>

## <a name="remarks"></a><span data-ttu-id="25287-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="25287-108">Remarks</span></span>

<span data-ttu-id="25287-109">Durch das Durchlaufen aller Fehler der Gewichtung $1 $ erhalten wir eine Summe von insgesamt $3 \ mal 5 = 15 $ möglichen nicht trivialen syndromes.</span><span class="sxs-lookup"><span data-stu-id="25287-109">By iterating over all errors of weight $1$, we obtain a total of $3\times 5=15$ possible non-trivial syndromes.</span></span>
<span data-ttu-id="25287-110">In Verbindung mit der Identität wird eine Fehler Tabelle und ein entsprechendes-Syndrom erstellt.</span><span class="sxs-lookup"><span data-stu-id="25287-110">Together with the identity, a table of error and corresponding syndrome is built up.</span></span> <span data-ttu-id="25287-111">Für den 5-Qubit-Code, der für diese Tabelle angegeben ist: $X \_ 1: (0, 0, 0, 1); X \_ 2: (1, 0, 0, 0); X \_ 3: (1, 1, 0, 0); X \_ 4: (0, 1, 1, 0); X \_ 5: (0,0, 1, 1) $, $Z \_ 1: (1, 0, 1, 0); Z \_ 2: (0, 1, 0, 1); Z \_ 3: (0,0, 1, 0); Z \_ 4: (1, 0, 0, 1); Z \_ 5: (0, 1, 0, 0) $ mit $Y _I $ durch Hinzufügen der $X _I $ und $Z _I $-Syndrome abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="25287-111">For the 5 qubit code this table is given by: $X\_1: (0,0,0,1); X\_2: (1,0,0,0); X\_3: (1,1,0,0); X\_4: (0,1,1,0); X\_5: (0,0,1,1)$, $Z\_1: (1,0,1,0); Z\_2: (0,1,0,1); Z\_3: (0,0,1,0); Z\_4: (1,0,0,1); Z\_5: (0,1,0,0)$ with $Y_i$ obtained by adding the $X_i$ and $Z_i$ syndromes.</span></span> <span data-ttu-id="25287-112">Beachten Sie, dass die Reihenfolge in der Wiederherstellung der Tabellen Suche angegeben wird, indem die bitvektoren in ganze Zahlen (mit Little Endian) umgerechnet werden.</span><span class="sxs-lookup"><span data-stu-id="25287-112">Note that the ordering in the table lookup recovery is given by converting the bitvectors to integers (using little endian).</span></span>

## <a name="see-also"></a><span data-ttu-id="25287-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="25287-113">See Also</span></span>

- [<span data-ttu-id="25287-114">Microsoft. Quantum. errorcorrection. wiederherstellungfn</span><span class="sxs-lookup"><span data-stu-id="25287-114">Microsoft.Quantum.ErrorCorrection.RecoveryFn</span></span>](xref:Microsoft.Quantum.ErrorCorrection.RecoveryFn)