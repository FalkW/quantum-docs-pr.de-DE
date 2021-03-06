---
title: Quantum-Algorithmen in Q#
description: Erfahren Sie mehr über grundlegende Quantum Computing-Algorithmen, einschließlich Amplitude-Verstärkung, Fourier Transform, Draper und Beauregard-Adders und Phasen Schätzung.
author: QuantumWriter
ms.author: martinro
ms.date: 12/11/2017
ms.topic: conceptual
uid: microsoft.quantum.libraries.standard.algorithms
no-loc:
- Q#
- $$v
ms.openlocfilehash: d4d8c35b3196ffb9915c6da06116b3c7dfd0562a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859010"
---
# <a name="quantum-algorithms"></a>Quantum-Algorithmen #

## <a name="amplitude-amplification"></a>Amplitudenverstärkung ##

Die *Amplitude-Verstärkung* ist eines der grundlegenden Tools von Quantum Computing. Es ist die grundlegende Idee, dass die Suche, die Amplitude-Schätzung und viele Quantum Machine Learning-Algorithmen zugrunde liegen.  Es gibt viele Varianten, und in wird Q# eine allgemeine Version basierend auf der schrägen Amplitude-Verstärkung mit partiellen Reflektionen bereitgestellt, um den größten Anwendungsbereich zu ermöglichen.

Die zentrale Idee hinter der Amplitude-Verstärkung besteht darin, die Wahrscheinlichkeit eines gewünschten Ergebnisses zu verstärken, indem eine Sequenz von Reflektionen durchgeführt wird.  Diese Reflektionen drehen den Anfangszustand näher an den gewünschten Zielzustand, der häufig als markierter Zustand bezeichnet wird.  Insbesondere wenn die Wahrscheinlichkeit, dass der Anfangszustand in einem markierten Zustand gemessen wird, $ \sin ^ 2 (\urta) $ ist, wird nach dem Anwenden der Amplitude-Verstärkung $m $ die Erfolgswahrscheinlichkeit auf $ \sin ^ 2 ((2 m + 1) \urta) $ festgelegt.  Dies bedeutet, dass, wenn $ \teta = \ Pi/[2 (2n + 1)] $ für einen Wert von $n $ ist, die Amplitude-Verstärkung die Wahrscheinlichkeit des Erfolgs auf $100 \\ % $ nach $n $ Iterationen der Amplitude-Verstärkung erhöhen kann.  Da $ \Der Ta = \sin ^ {-1} (\sqrt{\pr (Success)}) $, bedeutet dies, dass die Anzahl der Iterationen, die erforderlich sind, um einen erfolgreichen Abruf zu erzielen, quadratisch niedriger ist als die erwartete Anzahl, die für die Suche nach einem markierten Zustand nicht deterministisch mithilfe der zufälligen Stichprobenentnahme benötigt wird.

Für jede Iterations der Amplitude-Verstärkung müssen zwei reflektionsoperatoren angegeben werden. Insbesondere, wenn $Q $ der Amplitude-Verstärkungs Vorgang ist und $P _0 $ ein Projektor-Operator auf den ursprünglichen Teilbereich ist und $P _1 $ der Projektor auf dem markierten Teilbereich ist, dann $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Denken Sie daran, dass es sich bei einem Projektor um einen hermitian-Operator handelt, der die Eigenwerte $ + $1 und $0 $ aufweist und als Ergebnis $ (\boldone-2P_0) $ einheitlich ist, da es Eigenwerte aufweist, die die Stämme von Unity sind (in diesem Fall $ \pm $1). Stellen Sie sich als Beispiel die Groß-/Kleinschreibung der Grover-Suche mit dem anfänglichen Status $H ^ {\otimes n} \ket {0} $ und dem markierten Status $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket {0} \bra {0} H ^ {\otimes n} $ und $P _1 = \ket{m}\bra{m} $.  In den meisten Anwendungen der Amplitude-Verstärkung $P _0 $ ein Projektor auf einen Ausgangszustand, was bedeutet, dass $P _0 = \boldone-2 \ Ket {\ PSI} \ Bra {\ PSI} $ für einen Vektor $ \ket{\psi} $; bei einer pervious Amplitude-Verstärkung $P _0 $ in der Regel in viele Quantum-Zustände projiziert (d. h. die Multiplizität des $ + $1-Eigenwerts von $P _0 $ ist größer als $1 $).

Die Logik hinter der Amplitude-Verstärkung folgt direkt aus der Eigen Zerlegung von $Q $.  Insbesondere die Eigenvektoren von $Q $, dass der anfängliche Zustand, der nicht 0 (null) unterstützt, eine lineare Kombination der $ + $1-Eigenvektoren von $P _0 $ und $P _1 $ sind.  Insbesondere kann der anfängliche Status für die Amplitude-Verstärkung (vorausgesetzt, dass es sich um einen $ + $1-eigen Vektor $P _0 $) als $ $ \ket{\psi} = \frac{-i}{\sqrt {2} } \left (e ^ {i\der Ta} \ Ket {\ psi_ +} + e ^ {-i\der Ta} \ Ket {\ psi_-} \right) $ $ WHERE $ \ket{\ psi_ \pm} $ sind Eigenvektoren von $Q $ mit eigen Werten $e ^ {\pm 2i \ der TA} $ und verfügen nur über Unterstützung für die $ + $1-Eigenvektoren der $P _0 $ und $P _1 $.  Die Tatsache, dass die Eigenwerte $e ^ {\pm i \thta} $ sind, impliziert, dass der Operator $Q $ eine Drehung in einem zweidimensionalen Teilbereich durchführt, der von den beiden Projektoren festgelegt wird, und den ursprünglichen Zustand, in dem der Drehungs Winkel $2 \ Teta $ ist.  Aus diesem Grund ist die Erfolgswahrscheinlichkeit nach $m $ Iterationen von $Q $ die Erfolgswahrscheinlichkeit $ \sin ^ 2 ([2M + 1] \urta) $.

Eine weitere nützliche Eigenschaft, die daraus resultiert, besteht darin, dass der Eigen Wert $ \teta $ direkt mit der Wahrscheinlichkeit verknüpft ist, dass der Anfangszustand markiert wäre (in dem Fall, dass $P _0 $ ein Projektor ist, der nur den ursprünglichen Zustand aufweist).  Da die eigen Phasen von $Q $ $2 \ der TA = 2 \ Sin ^ {-1} (\sqrt{\pr (Success)}) $ lauten, folgt Folgendes: Wenn wir die Phasen Schätzung auf $Q $ anwenden, können wir die Erfolgswahrscheinlichkeit für ein einheitliches Quantum-Verfahren ermitteln.  Dies ist hilfreich, da hierfür quadratisch weniger Anwendungen des Quantums ausgeführt werden müssen, um die Erfolgswahrscheinlichkeit zu erlernen, als andernfalls erforderlich wäre.

Q# führt die Amplitude-Verstärkung als Spezialisierung der schrägen Amplitude-Verstärkung ein.  Eine schrägende Amplitude-Verstärkung verdient diesen Moniker, da der Projektor auf dem anfänglichen eigen Raum keinen Projektor auf dem ursprünglichen Zustand aufweisen muss.  In diesem Sinne ist das Protokoll für den ursprünglichen Zustand nicht sichtbar.  Die Schlüssel Anwendung der schrägen Amplitude-Verstärkung erfolgt in bestimmten *linearen Kombinationen von einheitlichen* hamiltona-Simulationsmethoden, bei denen der ursprüngliche Zustand unbekannt ist, aber mit einem Ancilla-Register im Simulations Protokoll entkoppelt wird.  Wenn dieses Ancilla-Register als fester Wert gemessen werden soll, z. b. $0 $, dann wenden solche Simulationsmethoden die gewünschte einheitliche Transformation auf die restlichen Qubits an (so genannte System Register).  Alle anderen Messergebnisse führen jedoch zu einem Fehler.  Eine schrägende Amplitude-Verstärkung ermöglicht, dass die Wahrscheinlichkeit, dass diese Messung erfolgreich ist, auf $100 \\ % $ mithilfe der oben genannten Argumentation erhöht werden kann.  Außerdem entspricht die gewöhnliche Amplitude-Verstärkung dem Fall, in dem das System Register leer ist.  Aus diesem Grund Q# verwendet die Verstärkung der Amplitude-Verstärkung als grundlegende Amplitude-Verstärkungs Unterroutine.

Die allgemeine Routine ( `AmpAmpObliviousByReflectionPhases` ) verfügt über zwei Register, die `ancillaRegister` als und bezeichnet werden `systemRegister` . Außerdem werden zwei Oracles für die erforderlichen Reflektionen akzeptiert. Der `ReflectionOracle` verhält sich nur auf dem, `ancillaRegister` während der `ObliviousOracle` für beide Register gemeinsam agiert. Die Eingabe für `ancillaRegister` muss mit dem Eigen Zustand "-1" des ersten reflektionsoperators "$ \boldone-2P_1 $" initialisiert werden.

In der Regel bereitet das Oracle den Status in der Berechnungsbasis $ \ket{0...0} $ vor. In unserer Implementierung werden die `ancillaRegister` konfime von einem Qubit ( `flagQubit` ), das den `stateOracle` und den Rest der gewünschten ancillas steuert. `stateOracle`Wird angewendet, wenn auf `flagQubit` $ \ket $ festgelegt ist {1} .

Eine kann auch Oracles `StateOracle` und `ObliviousOracle` anstelle von Reflektionen über einen-Befehl bereitstellen `AmpAmpObliviousByOraclePhases` .

Wie bereits erwähnt, ist die herkömmliche Amplitude-Verstärkung nur ein Sonderfall dieser Routinen, bei denen `ObliviousOracle` der Identitäts Operator ist und keine System-Qubits vorhanden sind (d. h. `systemRegister` leer ist). Wenn Sie Phasen für partielle Reflektionen (z. b. für die Grover-Suche) abrufen möchten, ist die-Funktion `AmpAmpPhasesStandard` verfügbar. Unter finden Sie `DatabaseSearch.qs` eine Beispiel Implementierung des Grover-Algorithmus.

Wir verknüpfen die Single-Qubit-Rotations Phasen mit den Reflexions Operator Phasen, wie im Dokument von [G.H. Low, I. L. Chuang](https://arxiv.org/abs/1707.05391)beschrieben. Die verwendeten festgelegten Punkt Phasen werden in " [yum", "Low" und "Chuang](https://arxiv.org/abs/1409.3305) " zusammen mit den Phasen " [niedrig", "Yoder" und "Chuang](https://arxiv.org/abs/1603.03996)" ausführlich erläutert

Für den Hintergrund könnten Sie von der [Standard mäßigen Amplitude-Verstärkung](https://arxiv.org/abs/quant-ph/0005055) ausgehen und dann zu einer Einführung in die [pervious Amplitude-Verstärkung](https://arxiv.org/abs/1312.1414) und schließlich zu den in [niedrig und Chuang](https://arxiv.org/abs/1610.06546)dargestellten verallgemeinerungs Vorrichtungen wechseln. Eine schöne Übersichts Darstellung dieses gesamten Bereichs (im Zusammenhang mit der hamiltona-Simulation) wurde von [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf)angegeben.

## <a name="quantum-fourier-transform"></a>Quantum Fourier-Transformation ##

Die Fourier-Transformation ist ein grundlegendes Tool der klassischen Analyse und ist ebenso wichtig für Quantum-Berechnungen.
Darüber hinaus überschreitet die Effizienz von *Quantum Fourier Transform* (QFT) weit mehr, was auf einem klassischen Computer möglich ist, sodass es zu einem der ersten Tools der Wahl ist, wenn ein Quantum-Algorithmus entworfen wird.

Als ungefähre Generalisierung der QFT stellen wir den Vorgang bereit, der <xref:Microsoft.Quantum.Canon.ApproximateQFT> Weitere Optimierungen ermöglicht, indem Rotationen bereinigt werden, die für die gewünschte algorithmische Genauigkeit nicht unbedingt notwendig sind.
Der ungefähre QFT erfordert die dyadic-$Z $-Rotation-Vorgang <xref:Microsoft.Quantum.Intrinsic.RFrac> und den- <xref:Microsoft.Quantum.Intrinsic.H> Vorgang.
Es wird davon ausgegangen, dass die Eingabe und die Ausgabe in Big Endian-Codierung codiert werden---d. h., das Qubit mit Index `0` wird im äußersten äußersten (höchsten) Bit der binären ganzzahligen Darstellung codiert.
Dies richtet sich nach der [Ket-Notation](xref:microsoft.quantum.concepts.dirac), da das Registrieren von drei Qubits im Status $ \ket {100} $ $q _0 $ im Status $ \ket $ entspricht, {1} während sich die $q _1 $ und $q _2 $ im Status $ \ket {0} $ befinden.
Der Näherungs Parameter $a $ bestimmt die Bereinigungs Ebene der $Z $-Drehungen, d. h. $a \in [0.. n] $.
In diesem Fall werden alle $Z $-Drehungen $2 \ Pi/2 ^ k $, wobei $k > a $ aus der QFT-Leitung entfernt werden.
Es ist bekannt, dass für $k \ge \ Log_2 (n) + \ Log_2 (1/\epsilon) + $3. eine kann $ \\ | \operatschmue{QFT}-\operatschmue{aqft} \\ | < \epsilon $ binden.
Hier \\ ist $ | \cdot \\ | $ die Operator Norm, bei der es sich in diesem Fall um die Quadratwurzel des größten [Eigenwerts](xref:microsoft.quantum.concepts.matrix-advanced) von $ (\operatorname{QFT}-\operatorname{aqft}) handelt (\operatorname{QFT}-\operatorname{aqft}) ^ \dagger $.

## <a name="arithmetic"></a>Arithmetik ##

Ebenso wie Arithmetik beim klassischen Computing eine zentrale Rolle spielt, ist Sie auch bei der Quantenberechnung unverzichtbar.  Algorithmen, wie z. b. der factoringalgorithmus von Shor, Quantum-Simulationsmethoden und viele für die Organisation basierende Algorithmen basieren auf zusammenhängenden arithmetischen Operationen.  Die meisten Ansätze für die arithmetische Erstellung bei quantadder-Leitungen.  Der einfachste Adder nimmt eine klassische Eingabe $b $ und fügt den Wert einem Quantum-Zustand mit einer Ganzzahl von $ \ket{a} $ hinzu.  Mathematisch hat der Adler (der $ \operatschmue{Add} (b) $ für die klassische Eingabe $b $) die Eigenschaft

$ $ \operatschmue{Add} (b) \ket{a} = \ket{a + b}.
$ $ Diese einfache Adder-Leitung ist eher inkrementierter als ein Adder.
Sie kann in einen Adder konvertiert werden, der über $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b} über zwei Quantum-Eingaben verfügt. $ $ using $n $-gesteuerten Anwendungen von addern in der Form \begin{align} \operatschmue{Add} \ket{a} \ket{b} & = \lambda \_ {a \_ 0} \left (\operatschmue{Add} (1) \right) \lambda \_ {a \_ 1} \left (\operatorname{Add} (2) \right) \lambda \_ {a \_ 2} \left (\operatorname{Add} (4) \right) \cdots \lambda \_ {a \_ {n-1}} \left (\operatschmue{Add} ({{n-1}}) \right) \ket{a}\ket{b} \\ \\ & = \ket{a} \ket{b + a}, \end{align} für $n $-Bit-Ganzzahlen $a $ und $b $ und Addition Modulo $2 ^ n $.  Beachten Sie, dass die Notation $ \lambda \_ x (A) $ für jeden Vorgang $A $ auf die gesteuerte Version dieses Vorgangs mit dem Qubit $x $ as-Steuerelement verweist.

Ebenso kann die klassisch kontrollierte Multiplikation (eine modulare Form, die für den Shor-Factoring-Algorithmus unverzichtbar ist) mithilfe einer ähnlichen Reihe von kontrollierten Ergänzungen ausgeführt werden: \begin{align} \operatschmue{mult} (a) \ket{x}\ket{b} & = \lambda \_ {x \_ 0} \left (\operatornamental e{Add} (2 ^ 0 a) \right) \lambda \_ {a \_ 1} \left (\operatschmue{Add} (2 ^ 1a) \right) \lambda \_ {a \_ 2} \left (\operatschmue{Add} (2 ^ 2 a) \right) \cdots \lambda \_ {x \_ {n-1}} \left (\operatschmue{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\ \\ & = \ket{x}\ket{b + AX}.
\end{align} es gibt eine Untergrenze für die Multiplikation auf Quantum-Computern, die Sie möglicherweise aus der Definition von $ \operatschmue{mult} $ oben bemerken.  Anders als bei der Addition speichert die Quantum-Version dieser Verbindung das Produkt der Eingaben in einem Zusatz Register anstelle des Eingabe Registers.  In diesem Beispiel wird das Register mit dem Wert $b $ initialisiert, aber in der Regel wird der Wert 0 (null) beibehalten.  Dies ist in erforderlich, da im Allgemeinen keine Multiplikations Umkehrung für den allgemeinen $a $ und $x $ vorliegt.  Da alle Quantum-Vorgänge, die Maßeinheit, nicht umkehrbar sind, müssen wir genügend Informationen aufbewahren, um die Multiplikation umzukehren.  Aus diesem Grund wird das Ergebnis in einem separaten Array gespeichert.  Dieser Trick zum Speichern der Ausgabe eines nicht rückgängig-Vorgangs, wie Multiplikation, in einem separaten Register wird nach Charlie Bennett als "Bennett-Trick" bezeichnet und ist ein grundlegendes Tool sowohl bei der umkehrbaren als auch bei der quantumberechnung.

Viele Quantum-Verbindungen wurden hinzugefügt, und jede untersucht einen anderen Kompromiss hinsichtlich der Anzahl von Qubits (Leerraum) und der Anzahl von erforderlichen Gate-Vorgängen (Zeit).  Wir sehen uns die unten stehenden, als Draper Adder (Draper Adder) und den "Beauregard Adder" bezeichneten, äußerst effizienten addern

### <a name="draper-adder"></a>Draper Adder ###

Der Draper Adder ist wohl einer der elegantesten Quantum-Adders, da er die Quantum-Eigenschaften zum Durchführen der Addition direkt aufruft.  Der Einblick hinter den Draper Adder besteht darin, dass die Fourier-Transformation verwendet werden kann, um Phasenverschiebungen in eine bitschicht zu übersetzen.  Danach folgt, dass durch Anwenden einer Fourier-Transformation, Anwenden entsprechender Phasenverschiebungen und anschließendes wieder verwenden der Fourier-Transformation ein Adder implementiert werden kann.  Im Gegensatz zu vielen anderen addern, die vorgeschlagen wurden, verwendet der Draper Adder explizit Quantum-Effekte, die durch die Quantum Fourier-Transformation eingeführt wurden.  Sie verfügt nicht über ein naturklassisches Gegenstück.  Die einzelnen Schritte der Draper-Adder sind unten angegeben.

Angenommen, Sie haben zwei $n $-Bit-Qubit registriert die ganzen Zahlen $a $ und $b $, dann für alle $a $ $ $ \operatorname{QFT}\ket{a} = \frac {1} {\sqrt{2 ^ n}} \sum \_ {j = 0} ^ {2 ^ n-1} e ^ {i2\pi (aj)/2 ^ n} \ket{j}.
$ $, Wenn wir $ $ \ket{\phi \_ k (a)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi a/2 ^ k} \ket {1} \right) definieren, $ $ dann können Sie nach einiger Algebra sehen, dass $ $ \operatorname{QFT}\ket{a} = \ket{\phi \_ 1 (a)} \otimes \cdots \otimes \ket{\phi \_ n (a)}.
$ $ Der Pfad zum Durchführen eines Adder wird dann klar, nachdem er beobachtet hat, dass die Summe der Eingaben als $ $ \ket{a + b} = \operatorname{QFT} ^ {-1} \ket{\phi \_ 1 (a + b)} \otimes \cdots \otimes \ket{\phi \_ n (a + b)}
$ $ Die ganzen Zahlen $b $ und $a $ können dann hinzugefügt werden, indem die gesteuerte Phasen Drehung für jedes der Qubits in der Zerlegung mithilfe der Bits von $b $ As-Steuerelementen durchgeführt wird.

Diese Erweiterung kann weiter vereinfacht werden, indem Sie feststellen, dass für beliebige ganzzahlige $j $ und reelle Zahl $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Dies liegt daran, dass Sie, wenn Sie "$ 360 ^ {\circ} $ degrees ($ 2 \ Pi $ radiane)" in einem Kreis drehen, am Ende genau den Anfang haben.  Der einzige wichtige Teil von $x $ für $e ^ {i2\pi x} $ ist daher der Bruchteil von $x $.  Insbesondere, wenn eine binäre Erweiterung der Form $x = y +0. x \_ 0x \_ 2 \ ldots x n $ vorhanden ist, \_ $e ^ {i2\pi x} = e ^ {i2\pi (0). x \_ 0x \_ 2 \ ldots x \_ {n-1})} $ und somit $ $ \ket{\phi \_ k (a + b)} = \frac {1} {\sqrt {2} } \left (\ket {0} + e ^ {i2\pi [a/2 ^ k +0. b \_ k\ldots b \_ 1]} \ket {1} \right). $ $ Dies bedeutet, dass beim Durchführen einer Addition durch Erhöhen der einzelnen tensorflow-Faktoren in der Erweiterung der Fourier-Transformation von $ \ket{a} $ die Anzahl der Rotationen verringert wird, wenn $k $ abnimmt.  Dadurch wird die Anzahl der im Adder benötigten Quantum-Gates erheblich reduziert.  Wir bezeichnen die Fourier-Transformation, die Phasen Addition und die umgekehrten Fourier Transform-Schritte, die den Draper Adder als $ \operatschmue{QFT} ^ {-1} \left (\phi \\ \! \operatorname{Add}\right) \operatorname{QFT} $ umfassen. Eine Quantum-Verbindung, die diese Vereinfachung verwendet, um den gesamten Prozess zu implementieren, finden Sie unten.

![Draper-Adder als Verbindungs Diagramm dargestellt](~/media/draper.svg)

Jede kontrollierte $e ^ {I2 \ Pi/k} $ Gate in der Verbindung bezieht sich auf ein steuerungsphase.  Diese Gates verfügen über die-Eigenschaft auf dem Qubits-Paar, für das Sie agieren, $ \ket {00} \mapsto \ket {00} $, aber $ \ket {11} \mapsto e ^ {I2 \ Pi/k} \ Ket {11} $.  Mit dieser Verbindung können wir zusätzliche Qubits ohne zusätzliche Qubits ausführen, abgesehen von denjenigen, die zum Speichern der Eingaben und Ausgaben benötigt werden.

### <a name="beauregard-adder"></a>Beauregard Adder ###

Der Beauregard Adder ist ein quantmodularer Adder, der den Draper Adder verwendet, um die Addition Modulo $N $ für eine beliebige positive ganze Zahl $N $ auszuführen.  Die Bedeutung von Quantum-modularen addern, wie z. b. "Beauregard Adder", ergibt sich in hohem Maße von ihrer Verwendung im modularen exponentiations Schritt im Shor-Algorithmus für die Factoring.  Ein Quantum-Modultyp hat die folgenden Aktionen für die Quantum-Eingabe $ \ket{b} $ und die klassische Eingabe $a $, wobei $a $ und $b $ als ganze Zahlen mod $N $ erwartet werden. Dies bedeutet, dass Sie das Intervall $ [0, \ldots, N-1] $ aufweisen.

$ $ \ket{b}\rightarrow \ket{b + a \text{mod} N} = \begin{Cases} \ket{b + a}, & b + a < N \\ \\ \ket{b + a-N}, & (b + a) \ge N \end{Cases}.
$$

Der Beauregard-Adder verwendet den Draper Adder (genauer gesagt: $ \phi \\ \! \operatschmue{Add} $), um $a $ und $b $ in der Phase hinzuzufügen.  Anschließend wird der gleiche Vorgang verwendet, um zu ermitteln, ob $a + b <N $ durch Subtrahieren von $N $ und testen, ob $a + b-N<$0.  Die Verbindung speichert diese Informationen in einem zusätzlichen Qubit und fügt dann dem Register $N $ zurück, wenn $a + b<N $.  Anschließend wird die Berechnung dieses hilfbits abgeschlossen (dieser Schritt ist erforderlich, um sicherzustellen, dass die Zuordnung von "Ancilla" nach dem Aufruf von Adder aufgehoben werden kann).  Die Verbindung für den Beauregard-Adder ist unten angegeben.

!["Beauregard Adder", dargestellt als Leitungs Diagramm](~/media/beau.svg)

Hier hat das Gate $ \phi \\ \! \operatschmue{Add} $ dieselbe Form wie $ \phi \\ \! \operatschmue{Add} $, mit der Ausnahme, dass die Eingabe in diesem Kontext klassisch anstelle von Quantum ist.  Dadurch können die kontrollierten Phasen in "$ \phi \\ \! \operatschmue{Add} $" durch Phasen Gates ersetzt werden, die dann zusammen in weniger Vorgänge kompiliert werden können, um sowohl die Anzahl der Qubits und die Anzahl der für den Adder benötigten Gates zu verringern.

Weitere Informationen finden Sie unter [M. roetteler, Th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) und [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Quantenphasenschätzung ###

Eine besonders wichtige Anwendung der Quantum Fourier-Transformation ist das Erlernen der Eigenwerte einheitlicher Operatoren, ein Problem, das als *Phasen Schätzung* bezeichnet wird.
Stellen Sie sich einen einheitlichen $U $ und den Status $ \ket{\phi} $ vor, sodass $ \ket{\phi} $ ein eigen Zustand von $U $ mit unbekannter eigen Wert $ \phi $, \begin{Equation} u\ket {\ Phi} = \phi\ket{\phi}.
\end{Equation} wenn nur der Zugriff auf $U $ als Oracle möglich ist, können wir die Phase $ \phi $ erlernen, indem wir verwenden, dass $Z $-Drehungen, die auf das Ziel einer kontrollierten Operation angewendet werden, zurück an das Steuerelement weitergegeben werden.

Angenommen, $V $ ist eine kontrollierte Anwendung $U $, so: \begin{align} v (\ket {0} \otimes \ket{\phi}) & = \ket {0} \otimes \ket{\phi} \\ \\ \textrm{und} v (\ket {1} \otimes \ket{\phi}) & = e ^ {i \phi} \ket {1} \otimes \ket{\phi}.
\end{align} dann, nach Linearität, \begin{align} V (\ket{+} \otimes \ket{\phi}) & = \bruchteil {(\ket {0} \otimes \ket{\phi}) + e ^ {i \phi} (\ket {1} \otimes \ket{\phi})} {\sqrt {2} }.
\end{align} wir können Begriffe erfassen, um zu ermitteln, dass "\begin{align} V" (\ket{+} \otimes \ket{\phi}) & = \bruch {\ket {0} + e ^ {i \phi} \ket {1} } {\ Sqrt {2} } \otimes \ket{\phi} \\ \\ & = (R_1 (\phi) \ket{+}) \otimes \ket{\phi}, \end{align}, wobei $R _1 $ der einheitliche ist, der durch den Vorgang angewendet wird <xref:Microsoft.Quantum.Intrinsic.R1> .
Anders ausgedrückt: die Auswirkung der Anwendung von $V $ ist exakt identisch mit der Anwendung von $R _1 $ mit einem unbekannten Winkel, auch wenn wir nur auf $V $ als Oracle zugreifen können.
Daher wird für den Rest dieser Diskussion die Phasen Schätzung in Bezug auf $R _1 (\phi) $ erläutert, die wir mit dem sogenannten *Phasen-Kickback* implementieren.

Da das Steuerelement und das Ziel Register nach diesem Vorgang nicht mehr geändert werden, können wir $ \ket{\phi} $ als Ziel einer kontrollierten Anwendung von $U ^ $2 wieder verwenden, um ein zweites Steuerelement-Qubit auf den Status $R _1 (2 \phi) \ket{+} $ vorzubereiten.
Auf diese Weise können wir ein Register der Form "\begin{align} \ket{\psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \phi) \ket{+} \\ \\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket {0} + \) abrufen. Exp (i 2 ^ {j} \phi) \ket {1} \right) \\ \\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \phi k) \ket{k} \end{align}, wobei $n $ die erforderliche Anzahl von Genauigkeits Bits ist, und wo wir $ {} \propto $ verwendet haben {} , um anzugeben, dass der normalisierungs Faktor $1/\sqrt{2 ^ n} $ unterdrückt wurde.

Wenn wir davon ausgehen, dass $ \phi = 2 \pi p/2 ^ k $ für eine ganze Zahl $p $ ist, erkennen wir dies als $ \ket{\psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, wobei $p _J $ das $j ^ {\textrm{Th}} $ Bit $2 \pi \phi $ ist.
Wenn Sie das Adjoint der Quantum Fourier-Transformation anwenden, erhalten wir daher die binäre Darstellung der Phase, die als Quantenzustand codiert ist.

In Q# wird dies durch den- <xref:Microsoft.Quantum.Characterization.QuantumPhaseEstimation> Vorgang implementiert, der eine <xref:Microsoft.Quantum.Oracles.DiscreteOracle> implementierende Anwendung von $U ^ m $ als Funktion von positiven ganzen Zahlen $m $ übernimmt.
