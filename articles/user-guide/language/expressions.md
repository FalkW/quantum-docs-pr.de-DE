---
title: 'Typausdrücke in Q #'
description: 'Erfahren Sie, wie Konstanten, Variablen, Operatoren, Vorgänge und Funktionen als Ausdrücke in Q # angegeben, referenziert und kombiniert werden.'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
ms.topic: article
uid: microsoft.quantum.guide.expressions
ms.openlocfilehash: 93432cef9711b6780192cd59e92b09647a264b5c
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431205"
---
# <a name="type-expressions-in-q"></a><span data-ttu-id="39958-103">Typausdrücke in Q #</span><span class="sxs-lookup"><span data-stu-id="39958-103">Type Expressions in Q#</span></span>

## <a name="numeric-expressions"></a><span data-ttu-id="39958-104">Numerische Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-104">Numeric Expressions</span></span>

<span data-ttu-id="39958-105">Numerische Ausdrücke sind Ausdrücke vom Typ `Int` , `BigInt` oder `Double` .</span><span class="sxs-lookup"><span data-stu-id="39958-105">Numeric expressions are expressions of type `Int`, `BigInt`, or `Double`.</span></span>
<span data-ttu-id="39958-106">Das heißt, Sie sind entweder ganzzahlige oder Gleit Komma Zahlen.</span><span class="sxs-lookup"><span data-stu-id="39958-106">That is, they are either integer or floating-point numbers.</span></span>

<span data-ttu-id="39958-107">`Int`Literale in Q # werden einfach als Sequenz von Ziffern geschrieben.</span><span class="sxs-lookup"><span data-stu-id="39958-107">`Int` literals in Q# are written simply as a sequence of digits.</span></span>
<span data-ttu-id="39958-108">Hexadezimale und binäre ganze Zahlen werden mit dem `0x` `0b` Präfix und bzw. unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39958-108">Hexadecimal and binary integers are supported with a `0x` and `0b` prefix, respectively.</span></span>

<span data-ttu-id="39958-109">`BigInt`Literale in Q # werden mit einem nachfolgenden- `l` oder- `L` Suffix geschrieben.</span><span class="sxs-lookup"><span data-stu-id="39958-109">`BigInt` literals in Q# are written with a trailing `l` or `L` suffix.</span></span>
<span data-ttu-id="39958-110">Hexadezimale große ganze Zahlen werden mit dem Präfix "0x" unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39958-110">Hexadecimal big integers are supported with a "0x" prefix.</span></span>
<span data-ttu-id="39958-111">Daher sind die folgenden alle gültigen Verwendungsmöglichkeiten von `BigInt` Literalen:</span><span class="sxs-lookup"><span data-stu-id="39958-111">Thus, the following are all valid uses of `BigInt` literals:</span></span>

```qsharp
let bigZero = 0L;
let bigHex = 0x123456789abcdef123456789abcdefL;
let bigOne = bigZero + 1L;
```

<span data-ttu-id="39958-112">`Double`Literale in Q # sind Gleit Komma Zahlen, die mithilfe von Dezimalziffern geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="39958-112">`Double` literals in Q# are floating-point numbers written using decimal digits.</span></span>
<span data-ttu-id="39958-113">Sie können mit einem Dezimaltrennzeichen () `.` und/oder einem exponentiellen Teil geschrieben werden, der mit "e" oder "e" angegeben wird (nach dem nur ein mögliches negatives Vorzeichen und Dezimalziffern gültig sind).</span><span class="sxs-lookup"><span data-stu-id="39958-113">They can be written with a decimal point, `.`, and/or an exponential part indicated with 'e' or 'E' (after which only a possible negative sign and decimal digits are valid).</span></span>
<span data-ttu-id="39958-114">Die folgenden `Double` Literale sind gültig: `0.0` , `1.2e5` , `1e-5` .</span><span class="sxs-lookup"><span data-stu-id="39958-114">The following are valid `Double` literals: `0.0`, `1.2e5`, `1e-5`.</span></span>

<span data-ttu-id="39958-115">Wenn ein Array Ausdruck eines beliebigen Elementtyps vorhanden ist, `Int` kann ein Ausdruck mithilfe der [`Length`](xref:microsoft.quantum.core.length) integrierten Funktion gebildet werden, wobei der Array Ausdruck in Klammern eingeschlossen ist, `(` und `)` .</span><span class="sxs-lookup"><span data-stu-id="39958-115">Given an array expression of any element type, an `Int` expression may be formed using the [`Length`](xref:microsoft.quantum.core.length) built-in function, with the array expression enclosed in parentheses, `(` and `)`.</span></span>
<span data-ttu-id="39958-116">Wenn beispielsweise `a` an ein Array gebunden ist, dann `Length(a)` ist ein ganzzahliger Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="39958-116">For instance, if `a` is bound to an array, then `Length(a)` is an integer expression.</span></span>
<span data-ttu-id="39958-117">Wenn `b` ein Array von Arrays ganzer Zahlen ist, `Int[][]` dann `Length(b)` ist die Anzahl der Unterarrays in `b` , und `Length(b[1])` die Anzahl von ganzen Zahlen im zweiten Unterarray in `b` .</span><span class="sxs-lookup"><span data-stu-id="39958-117">If `b` is an array of arrays of integers, `Int[][]`, then `Length(b)` is the number of sub-arrays in `b`, and `Length(b[1])` is the number of integers in the second sub-array in `b`.</span></span>

<span data-ttu-id="39958-118">Bei zwei numerischen Ausdrücken desselben Typs können die binären Operatoren, `+` , `-` `*` und `/` verwendet werden, um einen neuen numerischen Ausdruck zu bilden.</span><span class="sxs-lookup"><span data-stu-id="39958-118">Given two numeric expressions of the same type, the binary operators `+`, `-`, `*`, and `/` may be used to form a new numeric expression.</span></span>
<span data-ttu-id="39958-119">Der Typ des neuen Ausdrucks ist mit den Typen der einzelnen Ausdrücke identisch.</span><span class="sxs-lookup"><span data-stu-id="39958-119">The type of the new expression will be the same as the types of the constituent expressions.</span></span>

<span data-ttu-id="39958-120">Bei zwei ganzzahligen Ausdrücken kann der binäre Operator `^` (Power) verwendet werden, um einen neuen ganzzahligen Ausdruck zu bilden.</span><span class="sxs-lookup"><span data-stu-id="39958-120">Given two integer expressions, the binary operator `^` (power) may be used to form a new integer expression.</span></span>
<span data-ttu-id="39958-121">Auf ähnliche Weise `^` kann mit zwei doppelten Ausdrücken verwendet werden, um einen neuen doppelten Ausdruck zu bilden.</span><span class="sxs-lookup"><span data-stu-id="39958-121">Similarly, `^` may be used with two double expressions to form a new double expression.</span></span>
<span data-ttu-id="39958-122">Schließlich `^` kann mit einer großen Ganzzahl auf der linken Seite und einer Ganzzahl auf der rechten Seite verwendet werden, um einen neuen großen ganzzahligen Ausdruck zu bilden.</span><span class="sxs-lookup"><span data-stu-id="39958-122">Finally, `^` may be used with a big integer on the left and an integer on the right to form a new big integer expression.</span></span>
<span data-ttu-id="39958-123">In diesem Fall muss der zweite Parameter in 32 Bits passen. Wenn dies nicht der Fall ist, wird ein Laufzeitfehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="39958-123">In this case, the second parameter must fit into 32 bits; if not, a runtime error will be raised.</span></span>

<span data-ttu-id="39958-124">Bei zwei ganzzahligen oder großen ganzzahligen Ausdrücken kann ein neuer Integer-Ausdruck oder ein großer ganzzahliger Ausdruck mit den `%` Operatoren (Modulus), (bitweiser `&&&` and), `|||` (bitweiser or) oder `^^^` (Bitweiser XOR) gebildet werden.</span><span class="sxs-lookup"><span data-stu-id="39958-124">Given two integer or big integer expressions, a new integer or big integer expression may be formed using the `%` (modulus), `&&&` (bitwise AND), `|||` (bitwise OR), or `^^^` (bitwise XOR) operators.</span></span>

<span data-ttu-id="39958-125">Beim Ausdruck "Integer" oder "Big Integer" auf der linken Seite und einem ganzzahligen Ausdruck auf der rechten Seite `<<<` können die Operatoren (arithmetischer Left Shift) oder `>>>` (arithmetischer rechts Schiebe Operator) zum Erstellen eines neuen Ausdrucks mit dem gleichen Typ wie der linke Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39958-125">Given either an integer or big integer expression on the left, and an integer expression on the right, the `<<<` (arithmetic left shift) or `>>>` (arithmetic right shift) operators may be used to create a new expression with the same type as the left-hand expression.</span></span>

<span data-ttu-id="39958-126">Der zweite Parameter (die UMSCHALT Menge) in einen Verschiebungs Vorgang muss größer oder gleich 0 (null) sein. das Verhalten für negative Verschiebungs Beträge ist nicht definiert.</span><span class="sxs-lookup"><span data-stu-id="39958-126">The second parameter (the shift amount) to either shift operation must be greater than or equal to zero; the behavior for negative shift amounts is undefined.</span></span>
<span data-ttu-id="39958-127">Der Verschiebungs Betrag für einen der Verschiebungs Vorgänge muss ebenfalls in 32 Bits passen. Wenn dies nicht der Fall ist, wird ein Laufzeitfehler ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="39958-127">The shift amount for either shift operation must also fit into 32 bits; if not, a runtime error will be raised.</span></span>
<span data-ttu-id="39958-128">Wenn die zu Verschiebe Zahl eine ganze Zahl ist, wird der Verschiebungs Betrag interpretiert, d `mod 64` . h. eine Verschiebung von 1 und eine Schicht von 65 haben dieselbe Wirkung.</span><span class="sxs-lookup"><span data-stu-id="39958-128">If the number to be shifted is an integer, then the shift amount is interpreted `mod 64`; that is, a shift of 1 and a shift of 65 have the same effect.</span></span>

<span data-ttu-id="39958-129">Bei ganzzahligen und großen ganzzahligen Werten sind Verschiebungen arithmetisch.</span><span class="sxs-lookup"><span data-stu-id="39958-129">For both integer and big integer values, shifts are arithmetic.</span></span>
<span data-ttu-id="39958-130">Wenn Sie einen negativen Wert entweder nach links oder rechts verschieben, ergibt dies eine negative Zahl.</span><span class="sxs-lookup"><span data-stu-id="39958-130">Shifting a negative value either left or right will result in a negative number.</span></span>
<span data-ttu-id="39958-131">Das heißt, die Verschiebung eines Schritts nach links oder rechts ist identisch mit der Multiplikation bzw. Division durch 2.</span><span class="sxs-lookup"><span data-stu-id="39958-131">That is, shifting one step to the left or right is exactly the same as multiplying or dividing by 2, respectively.</span></span>

<span data-ttu-id="39958-132">Die ganzzahlige Division und der ganzzahlige Modulo folgen dem Verhalten für negative Zahlen wie c#.</span><span class="sxs-lookup"><span data-stu-id="39958-132">Integer division and integer modulus follow the same behavior for negative numbers as C#.</span></span>
<span data-ttu-id="39958-133">Das heißt, dass `a % b` immer dasselbe Vorzeichen wie hat `a` und `b * (a / b) + a % b` immer gleich ist `a` .</span><span class="sxs-lookup"><span data-stu-id="39958-133">That is, `a % b` will always have the same sign as `a`, and `b * (a / b) + a % b` will always equal `a`.</span></span>
<span data-ttu-id="39958-134">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39958-134">For example:</span></span>

 `A` | `B` | `A / B` | `A % B`
---------|----------|---------|---------
 <span data-ttu-id="39958-135">5</span><span class="sxs-lookup"><span data-stu-id="39958-135">5</span></span> | <span data-ttu-id="39958-136">2</span><span class="sxs-lookup"><span data-stu-id="39958-136">2</span></span> | <span data-ttu-id="39958-137">2</span><span class="sxs-lookup"><span data-stu-id="39958-137">2</span></span> | <span data-ttu-id="39958-138">1</span><span class="sxs-lookup"><span data-stu-id="39958-138">1</span></span>
 <span data-ttu-id="39958-139">5</span><span class="sxs-lookup"><span data-stu-id="39958-139">5</span></span> | <span data-ttu-id="39958-140">-2</span><span class="sxs-lookup"><span data-stu-id="39958-140">-2</span></span> | <span data-ttu-id="39958-141">-2</span><span class="sxs-lookup"><span data-stu-id="39958-141">-2</span></span> | <span data-ttu-id="39958-142">1</span><span class="sxs-lookup"><span data-stu-id="39958-142">1</span></span>
 <span data-ttu-id="39958-143">-5</span><span class="sxs-lookup"><span data-stu-id="39958-143">-5</span></span> | <span data-ttu-id="39958-144">2</span><span class="sxs-lookup"><span data-stu-id="39958-144">2</span></span> | <span data-ttu-id="39958-145">-2</span><span class="sxs-lookup"><span data-stu-id="39958-145">-2</span></span> | <span data-ttu-id="39958-146">-1</span><span class="sxs-lookup"><span data-stu-id="39958-146">-1</span></span>
 <span data-ttu-id="39958-147">-5</span><span class="sxs-lookup"><span data-stu-id="39958-147">-5</span></span> | <span data-ttu-id="39958-148">-2</span><span class="sxs-lookup"><span data-stu-id="39958-148">-2</span></span> | <span data-ttu-id="39958-149">2</span><span class="sxs-lookup"><span data-stu-id="39958-149">2</span></span> | <span data-ttu-id="39958-150">-1</span><span class="sxs-lookup"><span data-stu-id="39958-150">-1</span></span>

<span data-ttu-id="39958-151">Große ganzzahlige Division und Modulo funktionieren auf dieselbe Weise.</span><span class="sxs-lookup"><span data-stu-id="39958-151">Big integer division and modulus works the same way.</span></span>

<span data-ttu-id="39958-152">Wenn ein beliebiger numerischer Ausdruck vorhanden ist, kann ein neuer Ausdruck mit dem `-` unären Operator gebildet werden.</span><span class="sxs-lookup"><span data-stu-id="39958-152">Given any numeric expression, a new expression may be formed using the `-` unary operator.</span></span>
<span data-ttu-id="39958-153">Der neue Ausdruck hat denselben Typ wie der konstituierende Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="39958-153">The new expression will be the same type as the constituent expression.</span></span>

<span data-ttu-id="39958-154">Bei allen ganzzahligen oder großen ganzzahligen Ausdrücken kann ein neuer Ausdruck desselben Typs mit dem `~~~` unären Operator (bitweiser Komplement) gebildet werden.</span><span class="sxs-lookup"><span data-stu-id="39958-154">Given any integer or big integer expression, a new expression of the same type may be formed using the `~~~` (bitwise complement) unary operator.</span></span>

## <a name="boolean-expressions"></a><span data-ttu-id="39958-155">Boolesche Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-155">Boolean Expressions</span></span>

<span data-ttu-id="39958-156">Die beiden `Bool` Literalwerte sind `true` und `false` .</span><span class="sxs-lookup"><span data-stu-id="39958-156">The two `Bool` literal values are `true` and `false`.</span></span>

<span data-ttu-id="39958-157">Wenn zwei Ausdrücke desselben primitiven Typs vorhanden sind, können die `==` `!=` binären Operatoren und verwendet werden, um einen-Ausdruck zu erstellen `Bool` .</span><span class="sxs-lookup"><span data-stu-id="39958-157">Given any two expressions of the same primitive type, the `==` and `!=` binary operators may be used to construct a `Bool` expression.</span></span>
<span data-ttu-id="39958-158">Der Ausdruck ist true, wenn die beiden Ausdrücke gleich sind, andernfalls false.</span><span class="sxs-lookup"><span data-stu-id="39958-158">The expression will be true if the two expressions are equal, and false if not.</span></span>

<span data-ttu-id="39958-159">Werte von benutzerdefinierten Typen können nicht verglichen werden, sondern es können nur Ihre nicht umschließenden Werte verglichen werden.</span><span class="sxs-lookup"><span data-stu-id="39958-159">Values of user-defined types may not be compared, only their unwrapped values can be compared.</span></span> <span data-ttu-id="39958-160">Verwenden Sie beispielsweise den "Unwrap"-Operator `!` (ausführlich unter [Typen in f #](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)erläutert).</span><span class="sxs-lookup"><span data-stu-id="39958-160">For example, using the "unwrap" operator `!` (explained in detail at [Types in Q#](xref:microsoft.quantum.guide.types#access-anonymous-items-with-the-unwrap-operator)),</span></span>

```qsharp
newtype WrappedInt = Int;     // Yes, this is a contrived example
let x = WrappedInt(1);
let y = WrappedInt(2);
let z = x! == y!;             // This will compile and yield z = false.
let t = x == y;               // This will cause a compiler error.
```

<span data-ttu-id="39958-161">Der Gleichheits Vergleich für `Qubit` Werte ist die Identitäts Gleichheit, d. h., ob die beiden Ausdrücke dasselbe Qubit identifizieren.</span><span class="sxs-lookup"><span data-stu-id="39958-161">Equality comparison for `Qubit` values is identity equality; that is, whether the two expressions identify the same qubit.</span></span>
<span data-ttu-id="39958-162">Der Zustand der beiden Qubits wird von diesem Vergleich nicht verglichen, auf Sie zugegriffen, gemessen oder geändert.</span><span class="sxs-lookup"><span data-stu-id="39958-162">The state of the two qubits are not compared, accessed, measured, or modified by this comparison.</span></span>

<span data-ttu-id="39958-163">Der Gleichheits Vergleich für `Double` Werte kann aufgrund von Rundungs Effekten irreführend sein.</span><span class="sxs-lookup"><span data-stu-id="39958-163">Equality comparison for `Double` values may be misleading due to rounding effects.</span></span>
<span data-ttu-id="39958-164">Beispielsweise `49.0 * (1.0/49.0) != 1.0` .</span><span class="sxs-lookup"><span data-stu-id="39958-164">For instance, `49.0 * (1.0/49.0) != 1.0`.</span></span>

<span data-ttu-id="39958-165">Bei zwei numerischen Ausdrücken können die binären Operatoren,, `>` `<` `>=` und `<=` verwendet werden, um einen neuen booleschen Ausdruck zu erstellen, der true ist, wenn der erste Ausdruck größer als, kleiner als, größer als oder gleich oder kleiner oder gleich dem zweiten Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="39958-165">Given any two numeric expressions, the binary operators `>`, `<`, `>=`, and `<=` may be used to construct a new Boolean expression that is true if the first expression is respectively greater than, less than, greater than or equal to, or less than or equal to the second expression.</span></span>

<span data-ttu-id="39958-166">Bei zwei booleschen Ausdrücken `and` `or` können die binären Operatoren und verwendet werden, um einen neuen booleschen Ausdruck zu erstellen, der true ist, wenn beide Ausdrücke den Wert true haben.</span><span class="sxs-lookup"><span data-stu-id="39958-166">Given any two Boolean expressions, the `and` and `or` binary operators may be used to construct a new Boolean expression that is true if both of (resp. either or both of) the two expressions are true.</span></span>

<span data-ttu-id="39958-167">Bei jedem booleschen Ausdruck kann der `not` unäre Operator verwendet werden, um einen neuen booleschen Ausdruck zu erstellen, der true ist, wenn der konstituierende Ausdruck false ist.</span><span class="sxs-lookup"><span data-stu-id="39958-167">Given any Boolean expression, the `not` unary operator may be used to construct a new Boolean expression that is true if the constituent expression is false.</span></span>

## <a name="string-expressions"></a><span data-ttu-id="39958-168">Zeichen folgen Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-168">String Expressions</span></span>

<span data-ttu-id="39958-169">Q # ermöglicht die Verwendung von Zeichen folgen in der `fail` Anweisung (erläutert in der [Ablauf Steuerung](xref:microsoft.quantum.guide.controlflow#fail-statement)) und in der [`Message`](xref:microsoft.quantum.intrinsic.message) Standardfunktion.</span><span class="sxs-lookup"><span data-stu-id="39958-169">Q# allows strings to be used in the `fail` statement (explained at [Control Flow](xref:microsoft.quantum.guide.controlflow#fail-statement)) and in the [`Message`](xref:microsoft.quantum.intrinsic.message) standard function.</span></span>
<span data-ttu-id="39958-170">Das spezifische Verhalten der letzteren hängt von dem verwendeten Simulator ab, schreibt jedoch in der Regel eine Meldung in die Host Konsole, wenn Sie während eines Q #-Programms aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="39958-170">The specific behavior of the latter depends on the simulator being used, but typically writes a message to the host console when called during a Q# program.</span></span>

<span data-ttu-id="39958-171">Zeichen folgen in Q # sind entweder Literale oder interpoliert Zeichen folgen.</span><span class="sxs-lookup"><span data-stu-id="39958-171">Strings in Q# are either literals or interpolated strings.</span></span>

<span data-ttu-id="39958-172">Zeichenfolgenliterale ähneln in den meisten Sprachen einfachen Zeichenfolgenliteralen: eine Sequenz von Unicode-Zeichen, die in doppelten Anführungszeichen eingeschlossen sind `"` .</span><span class="sxs-lookup"><span data-stu-id="39958-172">String literals are similar to simple string literals in most languages: a sequence of Unicode characters enclosed in double quotes, `"`.</span></span>
<span data-ttu-id="39958-173">Innerhalb einer Zeichenfolge kann der umgekehrte Schrägstrich `\` verwendet werden, um ein doppeltes Anführungszeichen mit Escapezeichen zu versehen und eine neue Zeile als einzufügen, als `\n` und als `\r` Tabstopp Zeichen `\t` .</span><span class="sxs-lookup"><span data-stu-id="39958-173">Inside of a string, the back-slash character `\` may be used to escape a double quote character, and to insert a new-line as `\n`, a carriage return as `\r`, and a tab as `\t`.</span></span>
<span data-ttu-id="39958-174">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39958-174">For instance:</span></span>

```qsharp
"\"Hello world!\", she said.\n"
```
### <a name="interpolated-strings"></a><span data-ttu-id="39958-175">Interpolierte Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="39958-175">Interpolated strings</span></span>

<span data-ttu-id="39958-176">Die Q #-Syntax für Zeichen folgen Interpolationen ist eine Teilmenge der c#-Syntax, aber wir fassen hier die wichtigsten Punkte zusammen, die Sie für Q # betreffen.</span><span class="sxs-lookup"><span data-stu-id="39958-176">The Q# syntax for string interpolations is a subset of the C# syntax, but we summarize here the key points as they pertain to Q#.</span></span>
<span data-ttu-id="39958-177">Die wichtigsten Unterschiede werden im folgenden erläutert.</span><span class="sxs-lookup"><span data-stu-id="39958-177">The main distinctions are discussed below.</span></span>

<span data-ttu-id="39958-178">Wenn Sie ein Zeichenfolgenliteral als interpolierte Zeichenfolge ermitteln möchten, stellen Sie ihm ein `$`-Symbol voran.</span><span class="sxs-lookup"><span data-stu-id="39958-178">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span>
<span data-ttu-id="39958-179">Zwischen dem `$` und dem `"` , das einen zeichenfolgenliteralvorgang startet, darf kein Leerraum vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="39958-179">You cannot have any white space between the `$`and the `"` that starts a string literal.</span></span>

<span data-ttu-id="39958-180">Im folgenden finden Sie ein einfaches Beispiel, in dem die-Funktion verwendet wird [`Message`](xref:microsoft.quantum.intrinsic.message) , um das Ergebnis einer Maßeinheit zusammen mit anderen Q #-Ausdrücken in die Konsole zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="39958-180">The following is a basic example using the [`Message`](xref:microsoft.quantum.intrinsic.message) function to write the result of a measurement to the console, alongside other Q# expressions.</span></span>

```qsharp
    let num = 8;       // some Q# expression
    let res = M(q);
    Message($"Number: {num}, Result: {res}");
```
<span data-ttu-id="39958-181">Jeder gültige Q #-Ausdruck kann in einer interinterierten Zeichenfolge angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="39958-181">Any valid Q# expression may appear in an interpolated string.</span></span>

<span data-ttu-id="39958-182">Weitere Informationen zur c#-Syntax finden Sie unter [*interpoliert*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span><span class="sxs-lookup"><span data-stu-id="39958-182">Further details on the C# syntax can be found at [*Interpolated Strings*](https://docs.microsoft.com/dotnet/csharp/language-reference/keywords/interpolated-strings).</span></span>
<span data-ttu-id="39958-183">Der wichtigste Unterschied besteht darin, dass Q # keine ausführlichen (mehrzeiligen) interpoliert-Zeichen folgen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39958-183">The most notable distinction is that Q# does not support verbatim (multi-line) interpolated strings.</span></span>
<span data-ttu-id="39958-184">Ausdrücke in einer interinterierten Zeichenfolge Folgen der Q #-Syntax, nicht der c#-Syntax.</span><span class="sxs-lookup"><span data-stu-id="39958-184">Expressions inside of an interpolated string follow Q# syntax, not C# syntax.</span></span>

## <a name="range-expressions"></a><span data-ttu-id="39958-185">Bereichs Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-185">Range Expressions</span></span>

<span data-ttu-id="39958-186">Bei allen drei `Int` Ausdrücken `start` `step` ist, und `stop` `start .. step .. stop` ein Bereichs Ausdruck, dessen erstes Element `start` , zweites Element `start+step` , drittes Element `start+step+step` , usw. ist, bis `stop` übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="39958-186">Given any three `Int` expressions `start`, `step`, and `stop`, `start .. step .. stop` is a range expression whose first element is `start`, second element is `start+step`, third element is `start+step+step`, etc., until `stop` is passed.</span></span>
<span data-ttu-id="39958-187">Ein Bereich kann leer sein, wenn z.b. `step` positiv und ist `stop < start` .</span><span class="sxs-lookup"><span data-stu-id="39958-187">A range may be empty if, for instance, `step` is positive and `stop < start`.</span></span>
<span data-ttu-id="39958-188">Das letzte Element des Bereichs `stop` ist, wenn der Unterschied zwischen `start` und ein ganzzahliges `stop` Vielfaches von ist, d. h `step` ., der Bereich ist an beiden Enden inklusiv.</span><span class="sxs-lookup"><span data-stu-id="39958-188">The last element of the range will be `stop` if the difference between `start` and `stop` is an integral multiple of `step`; that is, the range is inclusive at both ends.</span></span>

<span data-ttu-id="39958-189">`Int`Bei zwei Ausdrücken `start` und `stop` `start .. stop` ist ein Bereichs Ausdruck, der gleich ist `start .. 1 .. stop` .</span><span class="sxs-lookup"><span data-stu-id="39958-189">Given any two `Int` expressions `start` and `stop`, `start .. stop` is a range expression that is equal to `start .. 1 .. stop`.</span></span>
<span data-ttu-id="39958-190">Beachten Sie, dass der implizierte Wert `step` + 1 ist, auch wenn `stop` kleiner als ist `start` . in einem solchen Fall ist der Bereich leer.</span><span class="sxs-lookup"><span data-stu-id="39958-190">Note that the implied `step` is +1 even if `stop` is less than `start`; in such a case, the range is empty.</span></span>

<span data-ttu-id="39958-191">Einige Beispiel Bereiche sind:</span><span class="sxs-lookup"><span data-stu-id="39958-191">Some example ranges are:</span></span>

- <span data-ttu-id="39958-192">`1..3`der Bereich von 1, 2, 3.</span><span class="sxs-lookup"><span data-stu-id="39958-192">`1..3` is the range 1, 2, 3.</span></span>
- <span data-ttu-id="39958-193">`2..2..5`ist der Bereich von 2, 4.</span><span class="sxs-lookup"><span data-stu-id="39958-193">`2..2..5` is the range 2, 4.</span></span>
- <span data-ttu-id="39958-194">`2..2..6`ist der Bereich von 2, 4, 6.</span><span class="sxs-lookup"><span data-stu-id="39958-194">`2..2..6` is the range 2, 4, 6.</span></span>
- <span data-ttu-id="39958-195">`6..-2..2`der Bereich ist 6, 4, 2.</span><span class="sxs-lookup"><span data-stu-id="39958-195">`6..-2..2` is the range 6, 4, 2.</span></span>
- <span data-ttu-id="39958-196">`2..1`der leere Bereich.</span><span class="sxs-lookup"><span data-stu-id="39958-196">`2..1` is the empty range.</span></span>
- <span data-ttu-id="39958-197">`2..6..7`der Bereich 2.</span><span class="sxs-lookup"><span data-stu-id="39958-197">`2..6..7` is the range 2.</span></span>
- <span data-ttu-id="39958-198">`2..2..1`der leere Bereich.</span><span class="sxs-lookup"><span data-stu-id="39958-198">`2..2..1` is the empty range.</span></span>
- <span data-ttu-id="39958-199">`1..-1..2`der leere Bereich.</span><span class="sxs-lookup"><span data-stu-id="39958-199">`1..-1..2` is the empty range.</span></span>

## <a name="qubit-expressions"></a><span data-ttu-id="39958-200">Qubit-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-200">Qubit Expressions</span></span>

<span data-ttu-id="39958-201">Die einzigen `Qubit` Ausdrücke sind Symbole, die an `Qubit` Werte oder Array Elemente von Arrays gebunden sind `Qubit` .</span><span class="sxs-lookup"><span data-stu-id="39958-201">The only `Qubit` expressions are symbols that are bound to `Qubit` values or array elements of `Qubit` arrays.</span></span>
<span data-ttu-id="39958-202">Es sind keine `Qubit` Literale vorhanden.</span><span class="sxs-lookup"><span data-stu-id="39958-202">There are no `Qubit` literals.</span></span>

## <a name="pauli-expressions"></a><span data-ttu-id="39958-203">Pauli-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-203">Pauli Expressions</span></span>

<span data-ttu-id="39958-204">Die vier Werte,,, `Pauli` `PauliI` `PauliX` `PauliY` und `PauliZ` sind gültige `Pauli` Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="39958-204">The four `Pauli` values, `PauliI`, `PauliX`, `PauliY`, and `PauliZ`, are all valid `Pauli` expressions.</span></span>

<span data-ttu-id="39958-205">Abgesehen davon sind die einzigen `Pauli` Ausdrücke Symbole, die an `Pauli` Werte oder Array Elemente von Arrays gebunden sind `Pauli` .</span><span class="sxs-lookup"><span data-stu-id="39958-205">Other than that, the only `Pauli` expressions are symbols that are bound to `Pauli` values or array elements of `Pauli` arrays.</span></span>

## <a name="result-expressions"></a><span data-ttu-id="39958-206">Ergebnis Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-206">Result Expressions</span></span>

<span data-ttu-id="39958-207">Die beiden `Result` Werte `One` und `Zero` sind gültige `Result` Ausdrücke.</span><span class="sxs-lookup"><span data-stu-id="39958-207">The two `Result` values, `One` and `Zero`, are valid `Result` expressions.</span></span>

<span data-ttu-id="39958-208">Abgesehen davon sind die einzigen `Result` Ausdrücke Symbole, die an `Result` Werte oder Array Elemente von Arrays gebunden sind `Result` .</span><span class="sxs-lookup"><span data-stu-id="39958-208">Other than that, the only `Result` expressions are symbols that are bound to `Result` values or array elements of `Result` arrays.</span></span>
<span data-ttu-id="39958-209">Beachten Sie insbesondere, dass `One` nicht mit der ganzen Zahl identisch ist `1` , und es gibt keine direkte Konvertierung zwischen Ihnen.</span><span class="sxs-lookup"><span data-stu-id="39958-209">In particular, note that `One` is not the same as the integer `1`, and there is no direct conversion between them.</span></span>
<span data-ttu-id="39958-210">Das gleiche gilt für `Zero` und `0` .</span><span class="sxs-lookup"><span data-stu-id="39958-210">The same is true for `Zero` and `0`.</span></span>

## <a name="tuple-expressions"></a><span data-ttu-id="39958-211">Tupelausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-211">Tuple Expressions</span></span>

<span data-ttu-id="39958-212">Ein tupelliteral ist eine Sequenz von Element Ausdrücken des entsprechenden Typs, die durch Kommas getrennt sind und in und eingeschlossen sind `(` `)` .</span><span class="sxs-lookup"><span data-stu-id="39958-212">A tuple literal is a sequence of element expressions of the appropriate type, separated by commas, enclosed in `(` and `)`.</span></span>
<span data-ttu-id="39958-213">Beispielsweise `(1, One)` ist ein `(Int, Result)` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="39958-213">For instance, `(1, One)` is an `(Int, Result)` expression.</span></span>

<span data-ttu-id="39958-214">Abgesehen von Literalen sind die einzigen Tupelausdrücke Symbole, die an Tupelwerte, Array Elemente von tupelarrays und Aufruf Bare Aufrufe gebunden sind, die Tupel zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="39958-214">Other than literals, the only tuple expressions are symbols that are bound to tuple values, array elements of tuple arrays, and callable invocations that return tuples.</span></span>

## <a name="user-defined-type-expressions"></a><span data-ttu-id="39958-215">Benutzerdefinierte typausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-215">User-Defined Type Expressions</span></span>

<span data-ttu-id="39958-216">Ein Literalwert eines benutzerdefinierten Typs besteht aus dem Typnamen, gefolgt von einem tupelliteraltyp mit dem basistupeltyp des Typs.</span><span class="sxs-lookup"><span data-stu-id="39958-216">A literal of a user-defined type consists of the type name followed by a tuple literal of the type’s base tuple type.</span></span>
<span data-ttu-id="39958-217">Wenn beispielsweise `IntPair` ein benutzerdefinierter Typ ist, der auf basiert `(Int, Int)` , dann `IntPair(2, 3)` wäre ein gültiges Literale dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="39958-217">For instance, if `IntPair` is a user-defined type based on `(Int, Int)`, then `IntPair(2, 3)` would be a valid literal of that type.</span></span>

<span data-ttu-id="39958-218">Anders als Literale sind die einzigen Ausdrücke eines benutzerdefinierten Typs Symbole, die an Werte dieses Typs gebunden sind, Array Elemente von Arrays dieses Typs und Aufruf Bare Aufrufe, die diesen Typ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="39958-218">Other than literals, the only expressions of a user-defined type are symbols that are bound to values of that type, array elements of arrays of that type, and callable invocations that return that type.</span></span>

## <a name="unwrap-expressions"></a><span data-ttu-id="39958-219">Entpacken von Ausdrücken</span><span class="sxs-lookup"><span data-stu-id="39958-219">Unwrap Expressions</span></span>

<span data-ttu-id="39958-220">In Q # ist der Unwrap-Operator ein nach gestelltes Ausrufezeichen `!` .</span><span class="sxs-lookup"><span data-stu-id="39958-220">In Q#, the unwrap operator is a trailing exclamation mark `!`.</span></span>
<span data-ttu-id="39958-221">Wenn beispielsweise `IntPair` ein benutzerdefinierter Typ mit dem zugrunde liegenden Typ `(Int, Int)` und `s` eine Variable mit Wert ist `IntPair(2, 3)` , `s!` wäre `(2, 3)` .</span><span class="sxs-lookup"><span data-stu-id="39958-221">For instance, if `IntPair` is a user-defined type with underlying type `(Int, Int)`, and `s` was a variable with value `IntPair(2, 3)`, then `s!` would be `(2, 3)`.</span></span>

<span data-ttu-id="39958-222">Für benutzerdefinierte Typen, die in Bezug auf andere benutzerdefinierte Typen definiert sind.</span><span class="sxs-lookup"><span data-stu-id="39958-222">For user-defined types defined in terms of other user-defined types.</span></span> <span data-ttu-id="39958-223">der Unwrap-Operator kann wiederholt werden. gibt beispielsweise `s!!` den doppelt entpackten Wert von an `s` .</span><span class="sxs-lookup"><span data-stu-id="39958-223">the unwrap operator may be repeated; for instance, `s!!` indicates the doubly-unwrapped value of `s`.</span></span>
<span data-ttu-id="39958-224">Wenn also `WrappedPair` ein benutzerdefinierter Typ mit dem zugrunde liegenden Typ `IntPair` und `t` eine Variable mit Wert ist `WrappedPair(IntPair(1,2))` , dann ist `t!!` `(1,2)` .</span><span class="sxs-lookup"><span data-stu-id="39958-224">Thus, if `WrappedPair` is a user-defined type with underlying type `IntPair`, and `t` is a variable with value `WrappedPair(IntPair(1,2))`, then `t!!` would be `(1,2)`.</span></span>

<span data-ttu-id="39958-225">Der `!` Operator hat eine höhere Rangfolge als alle anderen Operatoren, außer `[]` für die Array Indizierung und die Slicing.</span><span class="sxs-lookup"><span data-stu-id="39958-225">The `!` operator has higher precedence than all other operators other than `[]` for array indexing and slicing.</span></span>
<span data-ttu-id="39958-226">`!`und `[]` binden Sie Positions bedingt, d. h., Sie `a[i]![3]` sollten als gelesen werden `((a[i])!)[3]` : nehmen `i` Sie das ' th '-Element von `a` , entpacken Sie es, und dann das dritte Element des nicht umschließenden Werts (der ein Array sein muss).</span><span class="sxs-lookup"><span data-stu-id="39958-226">`!` and `[]` bind positionally; that is, `a[i]![3]` should be read as `((a[i])!)[3]`: take the `i`'th element of `a`, unwrap it, and then get the 3rd element of the unwrapped value (which must be an array).</span></span>

<span data-ttu-id="39958-227">Die Rangfolge des `!` Operators hat eine Beeinträchtigung, die möglicherweise nicht offensichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="39958-227">The precedence of the `!` operator has one impact that might not be obvious.</span></span>
<span data-ttu-id="39958-228">Wenn eine Funktion oder ein Vorgang einen Wert zurückgibt, der dann entpackt wird, muss der Funktions-oder Vorgangs Ausdruck in Klammern eingeschlossen werden, damit das Argument Tupel an den-Ausdruck gebunden wird, anstatt an den Unwrap-Vorgang.</span><span class="sxs-lookup"><span data-stu-id="39958-228">If a function or operation returns a value that then gets unwrapped, the function or operation call must be enclosed in parentheses so that the argument tuple binds to the call rather than to the unwrap.</span></span>
<span data-ttu-id="39958-229">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="39958-229">For example:</span></span>

```qsharp
let f = (Foo(arg))!;    // Calls Foo(arg), then unwraps the result
let g = Foo(arg)!;      // Syntax error
```

## <a name="array-expressions"></a><span data-ttu-id="39958-230">Array Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-230">Array Expressions</span></span>

<span data-ttu-id="39958-231">Ein Arrayliteral ist eine Sequenz von einem oder mehreren Element Ausdrücken, die durch Kommas getrennt sind und in und eingeschlossen ist `[` `]` .</span><span class="sxs-lookup"><span data-stu-id="39958-231">An array literal is a sequence of one or more element expressions, separated by commas, enclosed in `[` and `]`.</span></span>
<span data-ttu-id="39958-232">Alle-Elemente müssen mit demselben Typ kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="39958-232">All elements must be compatible with the same type.</span></span>


<span data-ttu-id="39958-233">Bei zwei Arrays desselben Typs kann der binäre `+` Operator verwendet werden, um ein neues Array zu bilden, bei dem es sich um die Verkettung der beiden Arrays handelt.</span><span class="sxs-lookup"><span data-stu-id="39958-233">Given two arrays of the same type, the binary `+` operator may be used to form a new array that is the concatenation of the two arrays.</span></span>
<span data-ttu-id="39958-234">Beispielsweise `[1,2,3] + [4,5,6]` ist `[1,2,3,4,5,6]` .</span><span class="sxs-lookup"><span data-stu-id="39958-234">For instance, `[1,2,3] + [4,5,6]` is `[1,2,3,4,5,6]`.</span></span>

### <a name="array-creation"></a><span data-ttu-id="39958-235">Array Erstellung</span><span class="sxs-lookup"><span data-stu-id="39958-235">Array Creation</span></span>

<span data-ttu-id="39958-236">Bei Angabe eines Typs und eines `Int` Ausdrucks `new` kann der Operator verwendet werden, um ein neues Array mit der angegebenen Größe zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="39958-236">Given a type and an `Int` expression, the `new` operator may be used to allocate a new array of the given size.</span></span>
<span data-ttu-id="39958-237">Beispielsweise `new Int[i + 1]` würde ein neues `Int` Array mit- `i + 1` Elementen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="39958-237">For instance, `new Int[i + 1]` would allocate a new `Int` array with `i + 1` elements.</span></span>

<span data-ttu-id="39958-238">Die Elemente eines neuen Arrays werden mit einem typabhängigen Standardwert initialisiert.</span><span class="sxs-lookup"><span data-stu-id="39958-238">The elements of a new array are initialized to a type-dependent default value.</span></span>
<span data-ttu-id="39958-239">In den meisten Fällen ist dies eine Variation von 0 (null).</span><span class="sxs-lookup"><span data-stu-id="39958-239">In most cases this is some variation of zero.</span></span>

<span data-ttu-id="39958-240">Bei Qubits und callables, bei denen es sich um Verweise auf Entitäten handelt, gibt es keinen angemessenen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="39958-240">For qubits and callables, which are references to entities, there is no reasonable default value.</span></span>
<span data-ttu-id="39958-241">Daher ist für diese Typen der Standardwert ein ungültiger Verweis, der nicht verwendet werden kann, ohne dass ein Laufzeitfehler verursacht wird.</span><span class="sxs-lookup"><span data-stu-id="39958-241">Thus, for these types, the default is an invalid reference that cannot be used without causing a runtime error.</span></span>
<span data-ttu-id="39958-242">Dies ähnelt einem NULL-Verweis in Sprachen wie c# oder Java.</span><span class="sxs-lookup"><span data-stu-id="39958-242">This is similar to a null reference in languages such as C# or Java.</span></span>
<span data-ttu-id="39958-243">Arrays, die Qubits oder callables enthalten, müssen ordnungsgemäß mit nicht standardmäßigen Werten initialisiert werden, bevor ihre Elemente problemlos verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="39958-243">Arrays containing qubits or callables must be properly initialized with non-default values before their elements may be safely used.</span></span> <span data-ttu-id="39958-244">Geeignete Initialisierungs Routinen finden Sie unter <xref:microsoft.quantum.arrays> .</span><span class="sxs-lookup"><span data-stu-id="39958-244">Suitable initialization routines can be found in <xref:microsoft.quantum.arrays>.</span></span>

<span data-ttu-id="39958-245">Die Standardwerte für jeden Typ lauten:</span><span class="sxs-lookup"><span data-stu-id="39958-245">The default values for each type are:</span></span>

<span data-ttu-id="39958-246">type</span><span class="sxs-lookup"><span data-stu-id="39958-246">Type</span></span> | <span data-ttu-id="39958-247">Standard</span><span class="sxs-lookup"><span data-stu-id="39958-247">Default</span></span>
---------|----------
 `Int` | `0`
 `BigInt` | `0L`
 `Double` | `0.0`
 `Bool` | `false`
 `String` | `""`
 `Qubit` | <span data-ttu-id="39958-248">_Ungültiges Qubit_</span><span class="sxs-lookup"><span data-stu-id="39958-248">_invalid qubit_</span></span>
 `Pauli` | `PauliI`
 `Result` | `Zero`
 `Range` | <span data-ttu-id="39958-249">Der leere Bereich,`1..1..0`</span><span class="sxs-lookup"><span data-stu-id="39958-249">The empty range, `1..1..0`</span></span>
 `Callable` | <span data-ttu-id="39958-250">_Ungültige Aufruf Bare_</span><span class="sxs-lookup"><span data-stu-id="39958-250">_invalid callable_</span></span>
 `Array['T]` | `'T[0]`

<span data-ttu-id="39958-251">Tupeltypen werden Element für Element initialisiert.</span><span class="sxs-lookup"><span data-stu-id="39958-251">Tuple types are initialized element-by-element.</span></span>


### <a name="array-elements"></a><span data-ttu-id="39958-252">Array Elemente</span><span class="sxs-lookup"><span data-stu-id="39958-252">Array Elements</span></span>

<span data-ttu-id="39958-253">Bei einem Array Ausdruck und einem `Int` Ausdruck kann ein neuer Ausdruck mit dem `[` und dem `]` Array Element Operator gebildet werden.</span><span class="sxs-lookup"><span data-stu-id="39958-253">Given an array expression and an `Int` expression, a new expression may be formed using the `[` and `]` array element operator.</span></span>
<span data-ttu-id="39958-254">Der neue Ausdruck hat denselben Typ wie der Elementtyp des Arrays.</span><span class="sxs-lookup"><span data-stu-id="39958-254">The new expression will be the same type as the element type of the array.</span></span>
<span data-ttu-id="39958-255">Wenn beispielsweise `a` an ein Array von s gebunden ist `Double` , dann `a[4]` ist ein- `Double` Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="39958-255">For instance, if `a` is bound to an array of `Double`s, then `a[4]` is a `Double` expression.</span></span>

<span data-ttu-id="39958-256">Wenn der Array Ausdruck kein einfacher Bezeichner ist, muss er in Klammern eingeschlossen werden, um ein Element auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="39958-256">If the array expression is not a simple identifier, it must be enclosed in parentheses in order to select an element.</span></span>
<span data-ttu-id="39958-257">Wenn `a` und Beispiels `b` Weise beide Arrays von s sind `Int` , würde ein Element aus der Verkettung wie folgt ausgedrückt werden:</span><span class="sxs-lookup"><span data-stu-id="39958-257">For instance, if `a` and `b` are both arrays of `Int`s, an element from the concatenation would be expressed as:</span></span>

```qsharp
(a + b)[13]
```

<span data-ttu-id="39958-258">Alle Arrays in Q # sind NULL basiert.</span><span class="sxs-lookup"><span data-stu-id="39958-258">All arrays in Q# are zero-based.</span></span>
<span data-ttu-id="39958-259">Das heißt, das erste Element eines Arrays `a` ist immer `a[0]` .</span><span class="sxs-lookup"><span data-stu-id="39958-259">That is, the first element of an array `a` is always `a[0]`.</span></span>


### <a name="array-slices"></a><span data-ttu-id="39958-260">Array Slices</span><span class="sxs-lookup"><span data-stu-id="39958-260">Array Slices</span></span>

<span data-ttu-id="39958-261">Bei einem Array Ausdruck und einem- `Range` Ausdruck kann ein neuer Ausdruck mit dem und dem `[` `]` Array Slice-Operator gebildet werden.</span><span class="sxs-lookup"><span data-stu-id="39958-261">Given an array expression and a `Range` expression, a new expression may be formed using the `[` and `]` array slice operator.</span></span>
<span data-ttu-id="39958-262">Der neue Ausdruck hat denselben Typ wie das Array und enthält die Array Elemente, die von den Elementen des-Elements indiziert werden `Range` , in der Reihenfolge, die durch definiert wird `Range` .</span><span class="sxs-lookup"><span data-stu-id="39958-262">The new expression will be the same type as the array and will contain the array items indexed by the elements of the `Range`, in the order defined by the `Range`.</span></span>
<span data-ttu-id="39958-263">Wenn beispielsweise `a` an ein Array von s gebunden ist `Double` , dann `a[3..-1..0]` ist ein- `Double[]` Ausdruck, der die ersten vier Elemente von enthält, `a` jedoch in umgekehrter Reihenfolge, wie Sie in angezeigt werden `a` .</span><span class="sxs-lookup"><span data-stu-id="39958-263">For instance, if `a` is bound to an array of `Double`s, then `a[3..-1..0]` is a `Double[]` expression that contains the first four elements of `a` but in the reverse order as they appear in `a`.</span></span>

<span data-ttu-id="39958-264">Wenn das `Range` leer ist, ist das resultierende Array in der Länge 0 (null).</span><span class="sxs-lookup"><span data-stu-id="39958-264">If the `Range` is empty, then the resulting array slice will be zero length.</span></span>

<span data-ttu-id="39958-265">Ebenso wie beim Verweisen auf Array Elemente muss der Array Ausdruck, wenn es sich nicht um einen einfachen Bezeichner handelt, in Klammern eingeschlossen werden, um Sie in Slices aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="39958-265">Just as with referencing array elements, if the array expression is not a simple identifier, it must be enclosed it parentheses in order to slice.</span></span>
<span data-ttu-id="39958-266">Wenn `a` und `b` beide Arrays von `Int` s sind, würde ein Slice aus der Verkettung folgendermaßen ausgedrückt werden:</span><span class="sxs-lookup"><span data-stu-id="39958-266">If `a` and `b` are both arrays of `Int`s, a slice from the concatenation would be expressed as:</span></span>

```qsharp
(a+b)[1..2..7]
```

#### <a name="inferred-startend-values"></a><span data-ttu-id="39958-267">Abherleitet anfangs-/Endwerte</span><span class="sxs-lookup"><span data-stu-id="39958-267">Inferred start/end values</span></span>

<span data-ttu-id="39958-268">Ab unserer Version 0,8 unterstützen wir Kontext Ausdrücke für die Bereichs Aufteilung.</span><span class="sxs-lookup"><span data-stu-id="39958-268">Starting with our 0.8 release, we support contextual expressions for range slicing.</span></span> <span data-ttu-id="39958-269">Insbesondere können Bereichs Start-und Endwerte im Kontext eines Bereichs aufteilen-Ausdrucks weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="39958-269">In particular, range start and end values may be omitted in the context of a range slicing expression.</span></span> <span data-ttu-id="39958-270">In diesem Fall wendet der Compiler die folgenden Regeln an, um die vorgesehenen Trennzeichen für den Bereich abzuleiten.</span><span class="sxs-lookup"><span data-stu-id="39958-270">In that case, the compiler will apply the following rules to infer the intended delimiters for the range.</span></span> 

<span data-ttu-id="39958-271">Wenn z. b. der Bereichs Start Wert weggelassen wird, wird der abherleitet Startwert</span><span class="sxs-lookup"><span data-stu-id="39958-271">For example, if the range start value is omitted,  then the inferred start value</span></span> 
- <span data-ttu-id="39958-272">ist 0 (null), wenn kein Schritt angegeben oder der angegebene Schritt positiv ist.</span><span class="sxs-lookup"><span data-stu-id="39958-272">is zero if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="39958-273">die Länge des aufgeschnittenen Arrays minus 1, wenn der angegebene Schritt negativ ist.</span><span class="sxs-lookup"><span data-stu-id="39958-273">is the length of sliced array minus one if the specified step is negative.</span></span> 

<span data-ttu-id="39958-274">Wenn der Wert für den Bereichs Endpunkt weggelassen wird, wird der abherende Endwert</span><span class="sxs-lookup"><span data-stu-id="39958-274">If the range end value is omitted,  then the inferred end value</span></span> 
- <span data-ttu-id="39958-275">die Länge des aufgeschnittenen Arrays minus 1, wenn kein Schritt angegeben oder der angegebene Schritt positiv ist.</span><span class="sxs-lookup"><span data-stu-id="39958-275">is the length of sliced array minus one if no step is specified or the specified step is positive, and</span></span> 
- <span data-ttu-id="39958-276">ist 0 (null), wenn der angegebene Schritt negativ ist.</span><span class="sxs-lookup"><span data-stu-id="39958-276">is zero if the specified step is negative.</span></span> 

```qsharp
let arr = [1,2,3,4,5,6];
let slice1  = arr[3...];      // slice1 is [4,5,6];
let slice2  = arr[0..2...];   // slice2 is [1,3,5];
let slice3  = arr[...2];      // slice3 is [1,2,3];
let slice4  = arr[...2..3];   // slice4 is [1,3];
let slice5  = arr[...2...];   // slice5 is [1,3,5];
let slice7  = arr[4..-2...];  // slice7 is [5,3,1];
let slice8  = arr[...-1..3];  // slice8 is [6,5,4];
let slice9  = arr[...-1...];  // slice9 is [6,5,4,3,2,1];
let slice10 = arr[...];       // slice10 is [1,2,3,4,5,6];
```

### <a name="copy-and-update-expressions"></a><span data-ttu-id="39958-277">Copy-und Update-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-277">Copy-and-Update Expressions</span></span>

<span data-ttu-id="39958-278">Da es sich bei allen Q #-Typen um Werttypen handelt – wobei die Qubits eine etwas besondere Rolle einnehmen – wird formal eine "Kopie" erstellt, wenn ein Wert an ein Symbol gebunden ist oder wenn ein Symbol erneut erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="39958-278">Since all Q# types are value types — with the qubits taking a somewhat special role —formally a "copy" is created when a value is bound to a symbol, or when a symbol is rebound.</span></span> <span data-ttu-id="39958-279">Dies heißt, dass das Verhalten von Q # identisch ist, wenn eine Kopie bei der Zuweisung erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="39958-279">That is to say, the behavior of Q# is the same as if a copy were created on assignment.</span></span>
<span data-ttu-id="39958-280">Natürlich werden in der Praxis nur die relevanten Teile bei Bedarf neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="39958-280">Of course in practice only the relevant pieces are actually recreated as needed.</span></span> 

<span data-ttu-id="39958-281">Dies gilt insbesondere für Arrays.</span><span class="sxs-lookup"><span data-stu-id="39958-281">This in particular also includes arrays.</span></span>
<span data-ttu-id="39958-282">Insbesondere ist es nicht möglich, Array Elemente zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="39958-282">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="39958-283">Zum Ändern eines vorhandenen Arrays muss ein *Kopier-und Aktualisierungs* Mechanismus genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="39958-283">To modify an existing array requires leveraging a *copy-and-update* mechanism.</span></span>

<span data-ttu-id="39958-284">Neue Arrays können über *Kopier-und Update* Ausdrücke aus vorhandenen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="39958-284">New arrays can be created from existing ones via *copy-and-update* expressions.</span></span>
<span data-ttu-id="39958-285">Ein Copy-and-Update-Ausdruck ist ein Ausdruck der Form `expression1 w/ expression2 <- expression3` , wobei `expression1` für einen Typ vom Typ sein muss `T[]` `T` .</span><span class="sxs-lookup"><span data-stu-id="39958-285">A copy-and-update expression is an expression of the form `expression1 w/ expression2 <- expression3`, where `expression1` has to be of type `T[]` for some type `T`.</span></span>
<span data-ttu-id="39958-286">Die zweite `expression2` definiert die Indizes der Elemente, die im Vergleich zum Array in geändert werden sollen, `expression1` und muss entweder vom Typ `Int` oder vom Typ sein `Range` .</span><span class="sxs-lookup"><span data-stu-id="39958-286">The second `expression2` defines the indices of the element(s) to modify compared to the array in `expression1` and has to be either of type `Int` or of type `Range`.</span></span>
<span data-ttu-id="39958-287">Wenn `expression2` vom Typ ist `Int` , `expression3` muss vom Typ sein `T` .</span><span class="sxs-lookup"><span data-stu-id="39958-287">If `expression2` is of type `Int`, `expression3` has to be of type `T`.</span></span> <span data-ttu-id="39958-288">Wenn `expression2` vom Typ ist `Range` , `expression3` muss vom Typ sein `T[]` .</span><span class="sxs-lookup"><span data-stu-id="39958-288">If `expression2` is of type `Range`, `expression3` has to be of type `T[]`.</span></span>

<span data-ttu-id="39958-289">Ein Copy-and-Update-Ausdruck erstellt `arr w/ idx <- value` ein neues Array, bei dem alle Elemente auf das entsprechende Element in festgelegt `arr` sind, mit Ausnahme der Elemente in `idx` , die auf die 1 (n) in festgelegt sind `value` .</span><span class="sxs-lookup"><span data-stu-id="39958-289">A copy-and-update expression `arr w/ idx <- value` constructs a new array with all elements set to the corresponding element in `arr`, except for the element(s) at `idx`, which are set to the one(s) in `value`.</span></span> <span data-ttu-id="39958-290">Wenn z. b. `arr` ein Array enthält `[0,1,2,3]` , dann</span><span class="sxs-lookup"><span data-stu-id="39958-290">For example, if `arr` contains an array `[0,1,2,3]`, then</span></span> 
- <span data-ttu-id="39958-291">`arr w/ 0 <- 10`ist das Array `[10,1,2,3]` .</span><span class="sxs-lookup"><span data-stu-id="39958-291">`arr w/ 0 <- 10` is the array `[10,1,2,3]`.</span></span>
- <span data-ttu-id="39958-292">`arr w/ 2 <- 10`ist das Array `[0,1,10,3]` .</span><span class="sxs-lookup"><span data-stu-id="39958-292">`arr w/ 2 <- 10` is the array `[0,1,10,3]`.</span></span>
- <span data-ttu-id="39958-293">`arr w/ 0..2..3 <- [10,12]`ist das Array `[10,1,12,3]` .</span><span class="sxs-lookup"><span data-stu-id="39958-293">`arr w/ 0..2..3 <- [10,12]` is the array `[10,1,12,3]`.</span></span>

#### <a name="copy-and-update-expressions-for-named-items"></a><span data-ttu-id="39958-294">Copy-und Update-Ausdrücke für benannte Elemente</span><span class="sxs-lookup"><span data-stu-id="39958-294">Copy-and-update expressions for named items</span></span>

<span data-ttu-id="39958-295">Ähnliche Ausdrücke sind für benannte Elemente in benutzerdefinierten Typen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="39958-295">Similar expressions exist for named items in user-defined types.</span></span> 

<span data-ttu-id="39958-296">Beachten Sie beispielsweise den-Typ.</span><span class="sxs-lookup"><span data-stu-id="39958-296">Consider for example the type</span></span> 

```qsharp
newtype Complex = (Re : Double, Im : Double);
```
<span data-ttu-id="39958-297">Wenn `c` den Wert des Typs enthält `Complex(1., -1.)` , dann `c w/ Re <- 0.` ist ein Ausdruck vom Typ, der ergibt `Complex` `Complex(0., -1.)` .</span><span class="sxs-lookup"><span data-stu-id="39958-297">If `c` contains the value of type `Complex(1., -1.)`, then `c w/ Re <- 0.` is an expression of type `Complex` that evaluates to `Complex(0., -1.)`.</span></span>

### <a name="jagged-arrays"></a><span data-ttu-id="39958-298">Verzweigte Arrays</span><span class="sxs-lookup"><span data-stu-id="39958-298">Jagged Arrays</span></span>

<span data-ttu-id="39958-299">Eine Jagged Array, manchmal auch als "Array von Arrays" bezeichnet, ist ein Array, dessen Elemente Arrays sind.</span><span class="sxs-lookup"><span data-stu-id="39958-299">A jagged array, sometimes called an "array of arrays," is an array whose elements are arrays.</span></span>
<span data-ttu-id="39958-300">Die Elemente einer Jagged Array können unterschiedlich sein.</span><span class="sxs-lookup"><span data-stu-id="39958-300">The elements of a jagged array can be of different sizes.</span></span>
<span data-ttu-id="39958-301">Im folgenden Beispiel wird gezeigt, wie Sie eine Jagged Array deklarieren und initialisieren, die eine Multiplikationstabelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="39958-301">The following example shows how to declare and initialize a jagged array representing a multiplication table.</span></span>

```qsharp
let N = 4;
mutable multiplicationTable = new Int[][N];
for (i in 1..N) {
    mutable row = new Int[i];
    for (j in 1..i) {
        set row w/= j-1 <- i * j;
    }
    set multiplicationTable w/= i-1 <- row;
}
```

### <a name="arrays-of-callables"></a><span data-ttu-id="39958-302">Arrays von callables</span><span class="sxs-lookup"><span data-stu-id="39958-302">Arrays of callables</span></span> 

<span data-ttu-id="39958-303">Beachten Sie, dass weitere Details zu Aufruf baren Typen unten und auf der nächsten Seite, [Vorgänge und Funktionen in f #](xref:microsoft.quantum.guide.operationsfunctions)gefunden werden können.</span><span class="sxs-lookup"><span data-stu-id="39958-303">Note that more details on callable types can be found below, as well as on the next page, [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions).</span></span>

<span data-ttu-id="39958-304">Wenn der allgemeine Elementtyp ein Vorgang oder Funktionstyp ist, müssen alle Elemente die gleichen Eingabe-und Ausgabetypen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="39958-304">If the common element type is an operation or function type, all of the elements must have the same input and output types.</span></span>
<span data-ttu-id="39958-305">Der Elementtyp des Arrays unterstützt alle Funktoren, die von allen Elementen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="39958-305">The element type of the array will support any functors that are supported by all of the elements.</span></span>
<span data-ttu-id="39958-306">Wenn z. b. `Op1` , `Op2` und `Op3` alle sind, unterstützt, unterstützt und unterstützt jedoch `Qubit[] => Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` beide:</span><span class="sxs-lookup"><span data-stu-id="39958-306">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[] => Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="39958-307">`[Op1, Op2]`ist ein Array von `(Qubit[] => Unit)` Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="39958-307">`[Op1, Op2]` is an array of `(Qubit[] => Unit)` operations.</span></span>
- <span data-ttu-id="39958-308">`[Op1, Op3]`ist ein Array von `(Qubit[] => Unit is Adj)` Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="39958-308">`[Op1, Op3]` is an array of `(Qubit[] => Unit is Adj)` operations.</span></span>
- <span data-ttu-id="39958-309">`[Op2, Op3]`ist ein Array von `(Qubit[] => Unit is Ctl)` Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="39958-309">`[Op2, Op3]` is an array of `(Qubit[] => Unit is Ctl)` operations.</span></span>

<span data-ttu-id="39958-310">Leere Array Literale, `[]` , sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="39958-310">Empty array literals, `[]`, are not allowed.</span></span>
<span data-ttu-id="39958-311">Wenn Sie stattdessen verwenden `new ★[0]` , wobei `★` als Platzhalter für einen geeigneten Typ verwendet, ermöglicht das Erstellen des gewünschten Arrays der Länge 0 (null).</span><span class="sxs-lookup"><span data-stu-id="39958-311">Instead using `new ★[0]`, where `★` is as placeholder for a suitable type, allows to create the desired array of length zero.</span></span>


## <a name="conditional-expressions"></a><span data-ttu-id="39958-312">Bedingte Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-312">Conditional Expressions</span></span>

<span data-ttu-id="39958-313">Bei zwei anderen Ausdrücken desselben Typs und eines booleschen Ausdrucks kann der bedingte Ausdruck mit dem Fragezeichen `?` und dem senkrechten Strich gebildet werden `|` .</span><span class="sxs-lookup"><span data-stu-id="39958-313">Given two other expressions of the same type and a Boolean expression, the conditional expression may be formed using the question mark `?` and the vertical bar `|`.</span></span>
<span data-ttu-id="39958-314">Beispielsweise `a==b ? c | d` .</span><span class="sxs-lookup"><span data-stu-id="39958-314">For instance, `a==b ? c | d`.</span></span>
<span data-ttu-id="39958-315">In diesem Beispiel ist der Wert des bedingten Ausdrucks, wenn den `c` Wert `a==b` true hat und wenn der Wert `d` false ist.</span><span class="sxs-lookup"><span data-stu-id="39958-315">In this example, the value of the conditional expression will be `c` if `a==b` is true and `d` if it is false.</span></span>

### <a name="conditional-expressions-with-callables"></a><span data-ttu-id="39958-316">Bedingte Ausdrücke mit callables</span><span class="sxs-lookup"><span data-stu-id="39958-316">Conditional expressions with callables</span></span>

<span data-ttu-id="39958-317">Die beiden Ausdrücke können zu Vorgängen ausgewertet werden, die über die gleichen Eingaben und Ausgaben verfügen, aber unterschiedliche Funktions tüktoren unterstützen.</span><span class="sxs-lookup"><span data-stu-id="39958-317">The two expressions may evaluate to operations that have the same inputs and outputs but support different functors.</span></span>
<span data-ttu-id="39958-318">In diesem Fall ist der Typ des bedingten Ausdrucks ein Vorgang mit diesen Eingaben und Ausgaben, der alle von beiden Ausdrücken unterstützten Funktoren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39958-318">In this case, the type of the conditional expression is an operation with those inputs and outputs that supports any functors supported by both expressions.</span></span>
<span data-ttu-id="39958-319">Wenn z. b. `Op1` , `Op2` und `Op3` alle sind, unterstützt, unterstützt und unterstützt jedoch `Qubit[]=>Unit` `Op1` `Adjoint` `Op2` `Controlled` `Op3` beide:</span><span class="sxs-lookup"><span data-stu-id="39958-319">For example, if `Op1`, `Op2`, and `Op3` all are `Qubit[]=>Unit`, but `Op1` supports `Adjoint`, `Op2` supports `Controlled`, and `Op3` supports both:</span></span>

- <span data-ttu-id="39958-320">`flag ? Op1 | Op2`ist ein- `(Qubit[] => Unit)` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="39958-320">`flag ? Op1 | Op2` is a `(Qubit[] => Unit)` operation.</span></span>
- <span data-ttu-id="39958-321">`flag ? Op1 | Op3`ist ein- `(Qubit[] => Unit is Adj)` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="39958-321">`flag ? Op1 | Op3` is a `(Qubit[] => Unit is Adj)` operation.</span></span>
- <span data-ttu-id="39958-322">`flag ? Op2 | Op3`ist ein- `(Qubit[] => Unit is Ctl)` Vorgang.</span><span class="sxs-lookup"><span data-stu-id="39958-322">`flag ? Op2 | Op3` is a `(Qubit[] => Unit is Ctl)` operation.</span></span>

<span data-ttu-id="39958-323">Wenn einer der beiden möglichen Ergebnis Ausdrücke einen Funktions-oder einen Vorgangs aufzurufen enthält, findet dieser Vorgang nur statt, wenn das Ergebnis das Ergebnis ist, das der Wert des Aufrufes ist.</span><span class="sxs-lookup"><span data-stu-id="39958-323">If either of the two possible result expressions include a function or operation call, that call will only take place if that result is the one that will be the value of the call.</span></span>
<span data-ttu-id="39958-324">`a==b ? C(qs) | D(qs)`Wenn Beispiels `a==b` Weise true ist, wird der `C` Vorgang aufgerufen, und wenn false ist, wird nur `D` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="39958-324">For instance, in the case `a==b ? C(qs) | D(qs)`, if `a==b` is true then the `C` operation will be invoked, and if it is false then only `D` will be invoked.</span></span>
<span data-ttu-id="39958-325">Dies ähnelt der Kurzschluss in anderen Sprachen.</span><span class="sxs-lookup"><span data-stu-id="39958-325">This is similar to short-circuiting in other languages.</span></span>

## <a name="callable-expressions"></a><span data-ttu-id="39958-326">Aufruf Bare Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-326">Callable Expressions</span></span>

<span data-ttu-id="39958-327">Ein Aufruf bares Literalelement ist der Name eines Vorgangs oder einer Funktion, der im Kompilierungs Bereich definiert ist.</span><span class="sxs-lookup"><span data-stu-id="39958-327">A callable literal is the name of an operation or function defined in the compilation scope.</span></span>
<span data-ttu-id="39958-328">Beispielsweise ist ein vorgangsliteral, `X` das auf den `X` -Standard Bibliotheks Vorgang verweist, und `Message` ist ein Funktionsliteral, das auf die Standard Bibliotheks `Message` Funktion verweist.</span><span class="sxs-lookup"><span data-stu-id="39958-328">For instance, `X` is an operation literal that refers to the standard library `X` operation, and `Message` is a function literal that refers to the standard library `Message` function.</span></span>

<span data-ttu-id="39958-329">Wenn ein Vorgang das `Adjoint` Funktor unterstützt, `Adjoint op` ist ein Vorgangs Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="39958-329">If an operation supports the `Adjoint` functor, then `Adjoint op` is an operation expression.</span></span>
<span data-ttu-id="39958-330">Entsprechend `Controlled` `Controlled op` ist ein Vorgangs Ausdruck, wenn der Vorgang das Funktor unterstützt.</span><span class="sxs-lookup"><span data-stu-id="39958-330">Similarly, if the operation supports the `Controlled` functor, then `Controlled op` is an operation expression.</span></span>
<span data-ttu-id="39958-331">Die Typen dieser Ausdrücke werden bei Aufrufen von [Vorgangs Spezialisierungs](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations)Vorgängen angegeben.</span><span class="sxs-lookup"><span data-stu-id="39958-331">The types of these expressions are specified at [Calling operation specializations](xref:microsoft.quantum.guide.operationsfunctions#calling-operation-specializations).</span></span>

<span data-ttu-id="39958-332">Funktoren ( `Adjoint` und `Controlled` ) werden genauer gebunden als alle anderen Operatoren, mit Ausnahme des Unwrap `!` -Operators und der Array Indizierung mit [] '.</span><span class="sxs-lookup"><span data-stu-id="39958-332">Functors (`Adjoint` and `Controlled`) bind more closely than all other operators, except for the unwrap operator `!` and array indexing with []\`.</span></span>
<span data-ttu-id="39958-333">Folglich sind die folgenden Vorgänge zulässig, vorausgesetzt, dass die Vorgänge die verwendeten Funktoren unterstützen:</span><span class="sxs-lookup"><span data-stu-id="39958-333">Thus, the following are all legal, assuming that the operations support the functors used:</span></span>

```qsharp
Adjoint Op(qs)
Controlled Op(controls, targets)
Controlled Adjoint Op(controls, targets)
Adjoint WrappedOp!(qs)
```

### <a name="type-parameterized-callable-expressions"></a><span data-ttu-id="39958-334">Typparametrisierte Aufruf Bare Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-334">Type-parameterized callable expressions</span></span>

<span data-ttu-id="39958-335">Ein Aufruf bares Literale kann als Wert verwendet werden, z. b. um einer Variablen zuzuweisen oder um Sie an eine andere Aufruf Bare zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="39958-335">A callable literal may be used as a value, say to assign to a variable or to pass to another callable.</span></span>
<span data-ttu-id="39958-336">In diesem Fall müssen Sie, wenn die Aufruf Bare [Typparameter](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables)aufweist, als Teil des Aufruf baren Werts angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="39958-336">In this case, if the callable has [type parameters](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables), they must be provided as part of the callable value.</span></span>
<span data-ttu-id="39958-337">Ein Aufruf barer Wert darf keine nicht angegebenen Typparameter aufweisen.</span><span class="sxs-lookup"><span data-stu-id="39958-337">A callable value cannot have any unspecified type parameters.</span></span>

<span data-ttu-id="39958-338">Wenn beispielsweise `Fun` eine Funktion mit der Signatur ist `'T1->Unit` :</span><span class="sxs-lookup"><span data-stu-id="39958-338">For instance, if `Fun` is a function with signature `'T1->Unit`:</span></span>

```qsharp
let f = Fun<Int>;            // f is (Int->Unit).
let g = Fun;                 // This causes a compilation error.
SomeOtherFun(Fun<Double>);   // A (Double->Unit) is passed to SomOtherFun.
SomeOtherFun(Fun);           // This also causes a compilation error.
```

## <a name="callable-invocation-expressions"></a><span data-ttu-id="39958-339">Aufruf Bare Aufruf Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="39958-339">Callable Invocation Expressions</span></span>

<span data-ttu-id="39958-340">Bei einem Aufruf baren Ausdruck (Operation oder Funktion) und einem Tupelausdruck des Eingabetyps der Aufruf baren Signatur kann ein Aufruf Ausdruck gebildet werden, indem der Tupelausdruck an den Aufruf baren Ausdruck angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="39958-340">Given a callable (operation or function) expression and a tuple expression of the input type of the callable's signature, an invocation expression may be formed by appending the tuple expression to the callable expression.</span></span>
<span data-ttu-id="39958-341">Der Typ des Aufruf Ausdrucks ist der Ausgabetyp der Signatur des Callable-Ausdrucks.</span><span class="sxs-lookup"><span data-stu-id="39958-341">The type of the invocation expression is the output type of the callable's signature.</span></span>

<span data-ttu-id="39958-342">Wenn z. b `Op` . ein Vorgang mit der Signatur ist `((Int, Qubit) => Double)` , `Op(3, qubit1)` ist ein Ausdruck vom Typ `Double` .</span><span class="sxs-lookup"><span data-stu-id="39958-342">For example, if `Op` is an operation with signature `((Int, Qubit) => Double)`, `Op(3, qubit1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="39958-343">Ebenso ist, wenn `Sin` eine Funktion mit der Signatur ist `(Double -> Double)` , `Sin(0.1)` ein Ausdruck vom Typ `Double` .</span><span class="sxs-lookup"><span data-stu-id="39958-343">Similarly, if `Sin` is a function with signature `(Double -> Double)`, `Sin(0.1)` is an expression of type `Double`.</span></span>
<span data-ttu-id="39958-344">Wenn schließlich `Builder` eine Funktion mit der Signatur ist `(Int -> (Int -> Int))` , dann `Builder(3)` ist eine Funktion von in bis int.</span><span class="sxs-lookup"><span data-stu-id="39958-344">Finally, if `Builder` is a function with signature `(Int -> (Int -> Int))`, then `Builder(3)` is a function from Into to Int.</span></span>

<span data-ttu-id="39958-345">Zum Aufrufen des Ergebnisses eines Aufruf baren Ausdrucks ist ein zusätzliches Paar von Klammern um den Aufruf baren Ausdruck erforderlich.</span><span class="sxs-lookup"><span data-stu-id="39958-345">Invoking the result of a callable-valued expression requires an extra pair of parentheses around the callable expression.</span></span>
<span data-ttu-id="39958-346">Um also das Ergebnis des Aufrufs `Builder` aus dem vorherigen Absatz aufzurufen, ist die korrekte Syntax:</span><span class="sxs-lookup"><span data-stu-id="39958-346">Thus, to invoke the result of calling `Builder` from the previous paragraph, the correct syntax is:</span></span>

```qsharp
(Builder(3))(2)
```

<span data-ttu-id="39958-347">Wenn Sie einen [vom Typ parametrisierten](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) Aufruf baren aufrufen, können die tatsächlichen Typparameter in spitzen Klammern `<` und `>` nach dem Aufruf baren Ausdruck angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="39958-347">When invoking a [type-parameterized](xref:microsoft.quantum.guide.operationsfunctions#generic-type-parameterized-callables) callable, the actual type parameters may be specified within angle brackets `<` and `>` after the callable expression.</span></span>
<span data-ttu-id="39958-348">Dies ist in der Regel unnötig, da der Q #-Compiler die eigentlichen Typen ableiten wird.</span><span class="sxs-lookup"><span data-stu-id="39958-348">This is usually unnecessary as the Q# compiler will infer the actual types.</span></span>
<span data-ttu-id="39958-349">Es *ist* jedoch für die [partielle Anwendung](xref:microsoft.quantum.guide.operationsfunctions#partial-application) erforderlich, wenn ein typparametrisiertes Argument nicht angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="39958-349">However, it *is* required for [partial application](xref:microsoft.quantum.guide.operationsfunctions#partial-application) if a type-parameterized argument is left unspecified.</span></span>
<span data-ttu-id="39958-350">Dies ist manchmal auch nützlich, wenn die Übergabe von Vorgängen mit unterschiedlichen Funktoren unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="39958-350">It is also sometimes useful when passing operations with different functor supports to a callable.</span></span>

<span data-ttu-id="39958-351">Wenn beispielsweise `Func` die Signatur aufweist und die Signatur und die Signatur `('T1, 'T2, 'T1) -> 'T2` aufweisen, `Op1` `Op2` `(Qubit[] => Unit is Adj)` `Op3` `(Qubit[] => Unit)` um `Func` mit `Op1` als erstes Argument, `Op2` als zweites und `Op3` als drittes aufzurufen:</span><span class="sxs-lookup"><span data-stu-id="39958-351">For instance, if `Func` has signature `('T1, 'T2, 'T1) -> 'T2`, `Op1` and `Op2` have signature `(Qubit[] => Unit is Adj)`, and `Op3` has signature `(Qubit[] => Unit)`, to invoke `Func` with `Op1` as the first argument, `Op2` as the second, and `Op3` as the third:</span></span>

```qsharp
let combinedOp = Func<(Qubit[] => Unit), (Qubit[] => Unit is Adj)>(Op1, Op2, Op3);
```

<span data-ttu-id="39958-352">Die Typspezifikation ist erforderlich `Op3` , da und `Op1` unterschiedliche Typen aufweisen, sodass der Compiler dies ohne Angabe der Spezifikation als mehrdeutig behandelt.</span><span class="sxs-lookup"><span data-stu-id="39958-352">The type specification is required because `Op3` and `Op1` have different types, so the compiler will treat this as ambiguous without the specification.</span></span>


## <a name="operator-precedence"></a><span data-ttu-id="39958-353">Operatorrangfolge</span><span class="sxs-lookup"><span data-stu-id="39958-353">Operator Precedence</span></span>

<span data-ttu-id="39958-354">Alle binären Operatoren sind mit Ausnahme von rechts assoziativ `^` .</span><span class="sxs-lookup"><span data-stu-id="39958-354">All binary operators are right-associative, except for `^`.</span></span>

<span data-ttu-id="39958-355">Eckige Klammern `[` und `]` , für das Aufteilen von Arrays und Indizierung, binden vor jedem Operator.</span><span class="sxs-lookup"><span data-stu-id="39958-355">Brackets, `[` and `]`, for array slicing and indexing, bind before any operator.</span></span>

<span data-ttu-id="39958-356">Die Funktoren `Adjoint` und die `Controlled` Bindung nach der Array Indizierung, aber vor allen anderen Operatoren.</span><span class="sxs-lookup"><span data-stu-id="39958-356">The functors `Adjoint` and `Controlled` bind after array indexing but before all other operators.</span></span>

<span data-ttu-id="39958-357">Klammern für Vorgangs-und Funktionsaufrufe werden auch vor jedem Operator gebunden, aber nach der Array Indizierung und den Funktoren.</span><span class="sxs-lookup"><span data-stu-id="39958-357">Parentheses for operation and function invocation also bind before any operator but after array indexing and functors.</span></span>

<span data-ttu-id="39958-358">Operatoren in Rangfolge, vom höchsten zum niedrigsten:</span><span class="sxs-lookup"><span data-stu-id="39958-358">Operators in order of precedence, from highest to lowest:</span></span>

<span data-ttu-id="39958-359">Operator</span><span class="sxs-lookup"><span data-stu-id="39958-359">Operator</span></span> | <span data-ttu-id="39958-360">Ständigkeit</span><span class="sxs-lookup"><span data-stu-id="39958-360">Arity</span></span> | <span data-ttu-id="39958-361">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="39958-361">Description</span></span> | <span data-ttu-id="39958-362">Operanden Typen</span><span class="sxs-lookup"><span data-stu-id="39958-362">Operand Types</span></span>
---------|----------|---------|---------------
 <span data-ttu-id="39958-363">nachträ`!`</span><span class="sxs-lookup"><span data-stu-id="39958-363">trailing `!`</span></span> | <span data-ttu-id="39958-364">Unär</span><span class="sxs-lookup"><span data-stu-id="39958-364">Unary</span></span> | <span data-ttu-id="39958-365">Aufheben der Umschließung</span><span class="sxs-lookup"><span data-stu-id="39958-365">Unwrap</span></span> | <span data-ttu-id="39958-366">Ein beliebiger benutzerdefinierter Typ</span><span class="sxs-lookup"><span data-stu-id="39958-366">Any user-defined type</span></span>
 <span data-ttu-id="39958-367">`-`, `~~~`, `not`</span><span class="sxs-lookup"><span data-stu-id="39958-367">`-`, `~~~`, `not`</span></span> | <span data-ttu-id="39958-368">Unär</span><span class="sxs-lookup"><span data-stu-id="39958-368">Unary</span></span> | <span data-ttu-id="39958-369">Numerische negative, bitweise Komplement logische Negation</span><span class="sxs-lookup"><span data-stu-id="39958-369">Numeric negative, bitwise complement, logical negation</span></span> | <span data-ttu-id="39958-370">`Int`, `BigInt` oder `Double` für `-` , `Int` `BigInt` `~~~` `Bool` für`not`</span><span class="sxs-lookup"><span data-stu-id="39958-370">`Int`, `BigInt` or `Double` for `-`, `Int` or `BigInt` for `~~~`, `Bool` for `not`</span></span>
 `^` | <span data-ttu-id="39958-371">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-371">Binary</span></span> | <span data-ttu-id="39958-372">Ganzzahlige Potenz</span><span class="sxs-lookup"><span data-stu-id="39958-372">Integer power</span></span> | <span data-ttu-id="39958-373">`Int`oder `BigInt` für die Basisklasse `Int` für den Exponenten</span><span class="sxs-lookup"><span data-stu-id="39958-373">`Int` or `BigInt` for the base, `Int` for the exponent</span></span>
 <span data-ttu-id="39958-374">`/`, `*`, `%`</span><span class="sxs-lookup"><span data-stu-id="39958-374">`/`, `*`, `%`</span></span> | <span data-ttu-id="39958-375">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-375">Binary</span></span> | <span data-ttu-id="39958-376">Division, Multiplikation, ganzzahliger Modulo</span><span class="sxs-lookup"><span data-stu-id="39958-376">Division, multiplication, integer modulus</span></span> | <span data-ttu-id="39958-377">`Int`, `BigInt` oder `Double` für `/` und `*` `Int` oder `BigInt` für`%`</span><span class="sxs-lookup"><span data-stu-id="39958-377">`Int`, `BigInt` or `Double` for `/` and `*`, `Int` or `BigInt` for `%`</span></span>
 <span data-ttu-id="39958-378">`+`, `-`</span><span class="sxs-lookup"><span data-stu-id="39958-378">`+`, `-`</span></span> | <span data-ttu-id="39958-379">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-379">Binary</span></span> | <span data-ttu-id="39958-380">Addition oder Zeichenfolge und Array Verkettung, Subtraktion</span><span class="sxs-lookup"><span data-stu-id="39958-380">Addition or string and array concatenation, subtraction</span></span> | <span data-ttu-id="39958-381">`Int`, `BigInt` oder `Double` , zusätzlich `String` oder ein beliebiger Arraytyp für`+`</span><span class="sxs-lookup"><span data-stu-id="39958-381">`Int`, `BigInt` or `Double`, additionally `String` or any array type for `+`</span></span>
 <span data-ttu-id="39958-382">`<<<`, `>>>`</span><span class="sxs-lookup"><span data-stu-id="39958-382">`<<<`, `>>>`</span></span> | <span data-ttu-id="39958-383">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-383">Binary</span></span> | <span data-ttu-id="39958-384">Left Shift, Right Shift</span><span class="sxs-lookup"><span data-stu-id="39958-384">Left shift, right shift</span></span> | <span data-ttu-id="39958-385">`Int` oder `BigInt`</span><span class="sxs-lookup"><span data-stu-id="39958-385">`Int` or `BigInt`</span></span>
 <span data-ttu-id="39958-386">`<`, `<=`, `>`, `>=`</span><span class="sxs-lookup"><span data-stu-id="39958-386">`<`, `<=`, `>`, `>=`</span></span> | <span data-ttu-id="39958-387">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-387">Binary</span></span> | <span data-ttu-id="39958-388">Kleiner-als-, kleiner-als-oder-gleich-, größer-als-, größer-als-oder-gleich-Vergleiche</span><span class="sxs-lookup"><span data-stu-id="39958-388">Less-than, less-than-or-equal, greater-than, greater-than-or-equal comparisons</span></span> | <span data-ttu-id="39958-389">`Int`, `BigInt` oder`Double`</span><span class="sxs-lookup"><span data-stu-id="39958-389">`Int`, `BigInt` or `Double`</span></span>
 <span data-ttu-id="39958-390">`==`, `!=`</span><span class="sxs-lookup"><span data-stu-id="39958-390">`==`, `!=`</span></span> | <span data-ttu-id="39958-391">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-391">Binary</span></span> | <span data-ttu-id="39958-392">gleich, nicht gleichmäßige Vergleiche</span><span class="sxs-lookup"><span data-stu-id="39958-392">equal, not-equal comparisons</span></span> | <span data-ttu-id="39958-393">beliebiger primitiver Typ</span><span class="sxs-lookup"><span data-stu-id="39958-393">any primitive type</span></span>
 `&&&` | <span data-ttu-id="39958-394">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-394">Binary</span></span> | <span data-ttu-id="39958-395">Bitweises AND</span><span class="sxs-lookup"><span data-stu-id="39958-395">Bitwise AND</span></span> | <span data-ttu-id="39958-396">`Int` oder `BigInt`</span><span class="sxs-lookup"><span data-stu-id="39958-396">`Int` or `BigInt`</span></span>
 `^^^` | <span data-ttu-id="39958-397">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-397">Binary</span></span> | <span data-ttu-id="39958-398">Bitweises XOR</span><span class="sxs-lookup"><span data-stu-id="39958-398">Bitwise XOR</span></span> | <span data-ttu-id="39958-399">`Int` oder `BigInt`</span><span class="sxs-lookup"><span data-stu-id="39958-399">`Int` or `BigInt`</span></span>
 <code>\|\|\|</code> | <span data-ttu-id="39958-400">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-400">Binary</span></span> | <span data-ttu-id="39958-401">Bitweises OR</span><span class="sxs-lookup"><span data-stu-id="39958-401">Bitwise OR</span></span> | <span data-ttu-id="39958-402">`Int` oder `BigInt`</span><span class="sxs-lookup"><span data-stu-id="39958-402">`Int` or `BigInt`</span></span>
 `and` | <span data-ttu-id="39958-403">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-403">Binary</span></span> | <span data-ttu-id="39958-404">Logisches AND</span><span class="sxs-lookup"><span data-stu-id="39958-404">Logical AND</span></span> | `Bool`
 `or` | <span data-ttu-id="39958-405">Binary</span><span class="sxs-lookup"><span data-stu-id="39958-405">Binary</span></span> | <span data-ttu-id="39958-406">Logisches OR</span><span class="sxs-lookup"><span data-stu-id="39958-406">Logical OR</span></span> | `Bool`
 `..` | <span data-ttu-id="39958-407">Binär/Ternär</span><span class="sxs-lookup"><span data-stu-id="39958-407">Binary/Ternary</span></span> | <span data-ttu-id="39958-408">Bereichs Operator</span><span class="sxs-lookup"><span data-stu-id="39958-408">Range operator</span></span> | `Int`
 <span data-ttu-id="39958-409">`?` `|`</span><span class="sxs-lookup"><span data-stu-id="39958-409">`?` `|`</span></span> | <span data-ttu-id="39958-410">TERNÄRE</span><span class="sxs-lookup"><span data-stu-id="39958-410">Ternary</span></span> | <span data-ttu-id="39958-411">Bedingt</span><span class="sxs-lookup"><span data-stu-id="39958-411">Conditional</span></span> | <span data-ttu-id="39958-412">`Bool`für die linke Seite</span><span class="sxs-lookup"><span data-stu-id="39958-412">`Bool` for the left-hand-side</span></span>
<span data-ttu-id="39958-413">`w/` `<-`</span><span class="sxs-lookup"><span data-stu-id="39958-413">`w/` `<-`</span></span> | <span data-ttu-id="39958-414">TERNÄRE</span><span class="sxs-lookup"><span data-stu-id="39958-414">Ternary</span></span> | <span data-ttu-id="39958-415">Kopieren und aktualisieren</span><span class="sxs-lookup"><span data-stu-id="39958-415">Copy-and-update</span></span> | <span data-ttu-id="39958-416">Weitere Informationen finden Sie unter [Copy-and-Update-Ausdrücke](#copy-and-update-expressions)</span><span class="sxs-lookup"><span data-stu-id="39958-416">see [copy-and-update expressions](#copy-and-update-expressions)</span></span>

## <a name="whats-next"></a><span data-ttu-id="39958-417">Wie geht es weiter?</span><span class="sxs-lookup"><span data-stu-id="39958-417">What's Next?</span></span>
<span data-ttu-id="39958-418">Nun, da Sie mit Ausdrücken in q # arbeiten können, können Sie sich mit den [Vorgängen und Funktionen in q #](xref:microsoft.quantum.guide.operationsfunctions) vertraut machen, um zu erfahren, wie Sie Vorgänge und Funktionen definieren und aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="39958-418">Now that you can work with expressions in Q#, you can head to [Operations and Functions in Q#](xref:microsoft.quantum.guide.operationsfunctions) to learn how to define and call operations and functions.</span></span>