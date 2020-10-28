---
uid: Microsoft.Quantum.Canon.CControlledA
title: Ccontrolleda-Funktion
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: CControlledA
qsharp.summary: Given an operation op, returns a new operation which applies the op if a classical control bit is true. If `false`, nothing happens. The modifier `A` indicates that the operation is adjointable.
ms.openlocfilehash: 30b5e3408fa6e5a79b2f3d63cccc11899c0405ef
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704407"
---
# <a name="ccontrolleda-function"></a><span data-ttu-id="7c57b-102">Ccontrolleda-Funktion</span><span class="sxs-lookup"><span data-stu-id="7c57b-102">CControlledA function</span></span>

<span data-ttu-id="7c57b-103">Namespace: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7c57b-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7c57b-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="7c57b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="7c57b-105">Gibt bei einem Vorgang op einen neuen Vorgang zurück, der das OP anwendet, wenn ein klassisches Steuerelement "true" ist.</span><span class="sxs-lookup"><span data-stu-id="7c57b-105">Given an operation op, returns a new operation which applies the op if a classical control bit is true.</span></span> <span data-ttu-id="7c57b-106">Gibt an `false` , dass nichts passiert.</span><span class="sxs-lookup"><span data-stu-id="7c57b-106">If `false`, nothing happens.</span></span>
<span data-ttu-id="7c57b-107">Der-Modifizierer `A` gibt an, dass der Vorgang adjointable ist.</span><span class="sxs-lookup"><span data-stu-id="7c57b-107">The modifier `A` indicates that the operation is adjointable.</span></span>

```qsharp
function CControlledA<'T> (op : ('T => Unit is Adj)) : ((Bool, 'T) => Unit is Adj)
```


## <a name="input"></a><span data-ttu-id="7c57b-108">Eingabe</span><span class="sxs-lookup"><span data-stu-id="7c57b-108">Input</span></span>

### <a name="op--t--unit-adj"></a><span data-ttu-id="7c57b-109">OP: 't => [Unit](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="7c57b-109">op : 'T => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7c57b-110">Ein Vorgang, der bedingt angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c57b-110">An operation to be conditionally applied.</span></span>



## <a name="output--boolt--unit-adj"></a><span data-ttu-id="7c57b-111">Ausgabe: ([bool](xref:microsoft.quantum.lang-ref.bool), 't) => [Unit](xref:microsoft.quantum.lang-ref.unit) ADJ</span><span class="sxs-lookup"><span data-stu-id="7c57b-111">Output : ([Bool](xref:microsoft.quantum.lang-ref.bool),'T) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj</span></span>

<span data-ttu-id="7c57b-112">Ein neuer Vorgang, bei dem es sich um einen op-Vorgang handelt, wenn das klassische Steuerelement</span><span class="sxs-lookup"><span data-stu-id="7c57b-112">A new operation which is op if the classical control bit is true.</span></span>

## <a name="type-parameters"></a><span data-ttu-id="7c57b-113">Typparameter</span><span class="sxs-lookup"><span data-stu-id="7c57b-113">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="7c57b-114">GIF</span><span class="sxs-lookup"><span data-stu-id="7c57b-114">'T</span></span>

<span data-ttu-id="7c57b-115">Der Eingabetyp des Vorgangs, der bedingt angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c57b-115">The input type of the operation to be conditionally applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="7c57b-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7c57b-116">See Also</span></span>

- [<span data-ttu-id="7c57b-117">Microsoft. Quantum. Canon. ckontrollierten</span><span class="sxs-lookup"><span data-stu-id="7c57b-117">Microsoft.Quantum.Canon.CControlled</span></span>](xref:Microsoft.Quantum.Canon.CControlled)