---
uid: Microsoft.Quantum.Arithmetic.RippleCarryAdderTTK
title: Ripplecarryadderttk-Vorgang
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: RippleCarryAdderTTK
qsharp.summary: Reversible, in-place ripple-carry addition of two integers. Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.
ms.openlocfilehash: 5366ace36e63d361a439bfc5a1a78fdf9a353062
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92706239"
---
# <a name="ripplecarryadderttk-operation"></a><span data-ttu-id="bf7c7-102">Ripplecarryadderttk-Vorgang</span><span class="sxs-lookup"><span data-stu-id="bf7c7-102">RippleCarryAdderTTK operation</span></span>

<span data-ttu-id="bf7c7-103">Namespace: [Microsoft. Quantum. Arithmetik](xref:Microsoft.Quantum.Arithmetic)</span><span class="sxs-lookup"><span data-stu-id="bf7c7-103">Namespace: [Microsoft.Quantum.Arithmetic](xref:Microsoft.Quantum.Arithmetic)</span></span>

<span data-ttu-id="bf7c7-104">Paketen [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="bf7c7-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="bf7c7-105">Umkehrbarer, direkter Ripple-Carry-Wert: Addition von zwei Ganzzahlen.</span><span class="sxs-lookup"><span data-stu-id="bf7c7-105">Reversible, in-place ripple-carry addition of two integers.</span></span>
<span data-ttu-id="bf7c7-106">Bei zwei $n ganzen Zahlen mit ganzen Zahlen, die in den littleEndian `xs` -Registern und `ys` , und einem Qubit-Wert codiert sind, berechnet der-Vorgang die Summe der beiden ganzen Zahlen, bei denen die $n $ geringsten signifikanten Bits des Ergebnisses in gespeichert sind `ys` und der Wert für das Ausführen von XoReD zum Qubit ist `carry` .</span><span class="sxs-lookup"><span data-stu-id="bf7c7-106">Given two $n$-bit integers encoded in LittleEndian registers `xs` and `ys`, and a qubit carry, the operation computes the sum of the two integers where the $n$ least significant bits of the result are held in `ys` and the carry out bit is xored to the qubit `carry`.</span></span>

```qsharp
operation RippleCarryAdderTTK (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, carry : Qubit) : Unit
```


## <a name="input"></a><span data-ttu-id="bf7c7-107">Eingabe</span><span class="sxs-lookup"><span data-stu-id="bf7c7-107">Input</span></span>

### <a name="xs--littleendian"></a><span data-ttu-id="bf7c7-108">xs: [littleenddian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bf7c7-108">xs : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bf7c7-109">Der littleEndian-Qubit-Register Codierung der ersten ganzzahligen Summe.</span><span class="sxs-lookup"><span data-stu-id="bf7c7-109">LittleEndian qubit register encoding the first integer summand.</span></span>


### <a name="ys--littleendian"></a><span data-ttu-id="bf7c7-110">YS: [littleumdian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span><span class="sxs-lookup"><span data-stu-id="bf7c7-110">ys : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)</span></span>

<span data-ttu-id="bf7c7-111">Der littleEndian-Qubit-Registrierungs Codierungs Wert für die zweite Ganzzahl sumund wird so geändert, dass die $n minimalen signifikanten Bits der Summe enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="bf7c7-111">LittleEndian qubit register encoding the second integer summand, is modified to hold the $n$ least significant bits of the sum.</span></span>


### <a name="carry--qubit"></a><span data-ttu-id="bf7c7-112">Carry: [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span><span class="sxs-lookup"><span data-stu-id="bf7c7-112">carry : [Qubit](xref:microsoft.quantum.lang-ref.qubit)</span></span>

<span data-ttu-id="bf7c7-113">Carry Qubit, ist XoReD mit dem signifikantesten Bit der Summe.</span><span class="sxs-lookup"><span data-stu-id="bf7c7-113">Carry qubit, is xored with the most significant bit of the sum.</span></span>



## <a name="output--unit"></a><span data-ttu-id="bf7c7-114">Ausgabe: [Einheit](xref:microsoft.quantum.lang-ref.unit)</span><span class="sxs-lookup"><span data-stu-id="bf7c7-114">Output : [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span>



## <a name="remarks"></a><span data-ttu-id="bf7c7-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bf7c7-115">Remarks</span></span>

<span data-ttu-id="bf7c7-116">Dieser Vorgang verfügt über die gleiche Funktionalität wie "ripplecarryadderd" und "ripplecarryaddercdkm", verwendet jedoch keine "Ancilla Qubits".</span><span class="sxs-lookup"><span data-stu-id="bf7c7-116">This operation has the same functionality as RippleCarryAdderD and, RippleCarryAdderCDKM but does not use any ancilla qubits.</span></span>

## <a name="references"></a><span data-ttu-id="bf7c7-117">Referenzen</span><span class="sxs-lookup"><span data-stu-id="bf7c7-117">References</span></span>

- <span data-ttu-id="bf7c7-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Additions-und ungebundene Fan-Out", Quantum-Informationen und-Berechnung, Vol. 10, 2010.</span><span class="sxs-lookup"><span data-stu-id="bf7c7-118">Yasuhiro Takahashi, Seiichiro Tani, Noboru Kunihiro: "Quantum Addition Circuits and Unbounded Fan-Out", Quantum Information and Computation, Vol. 10, 2010.</span></span>
  https://arxiv.org/abs/0910.2530