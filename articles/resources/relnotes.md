---
title: Versionshinweise für das Quantum Development Kit
description: Enthält Informationen zu den neuesten Aktualisierungen für das Microsoft Quantum Development Kit (Vorschauversion).
author: bradben
ms.author: v-benbra
ms.date: 8/30/2020
ms.topic: conceptual
uid: microsoft.quantum.relnotes
no-loc:
- Q#
- $$v
ms.openlocfilehash: dd37581dff2a512a29eb7729ecbf81412917b8f8
ms.sourcegitcommit: e915baf3b84ee3a562004c5b31d157d21533d450
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2021
ms.locfileid: "99101457"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Versionshinweise für das Microsoft Quantum Development Kit

Dieser Artikel enthält Informationen zu den einzelnen Releases des Microsoft Quantum Development Kit.

Installationsanweisungen finden Sie im [Installationshandbuch](xref:microsoft.quantum.install).

Updateanweisungen finden Sie im [Updatehandbuch](xref:microsoft.quantum.update).

## <a name="version-0152101126807"></a>Version 0.15.2101.126807

*Veröffentlichungsdatum: 29. Januar, 2021*

- Dem Compiler wurden Projektvorlagen für ausführbare Dateien hinzugefügt, die auf die Q# Anbieter "ionq" und "Honey
- Aktualisieren Q# der kernelsyntax für I-Kernel zum Einschließen von Änderungen an Q# der in Version [0.15.2101125897](#version-0152101125897) eingeführten Syntax
- Bugfix zur Unterstützung der Übergabe von Arrays als Eingabeargumente an Q# Programme #401, die an Azure Quantum über übermittelt `%azure.execute` werden [](https://github.com/microsoft/iqsharp/issues/401)
- Beheben Sie den Fehler "Berechtigung verweigert" `az` in `iqsharp-base` docker- [#404](https://github.com/microsoft/iqsharp/issues/404) Images

## <a name="version-0152101125897"></a>Version 0.15.2101125897

*Veröffentlichungsdatum: 26. Januar, 2021*

- Vereinfachte Qubit-Zuordnung, die eine einfachere Syntax zum Zuordnen von Qubits bietet, [finden Sie unter Details im Q# sprachrepository](https://github.com/microsoft/qsharp-language/blob/main/Approved/1-implicitly-scoped-qubit-allocation.md).
- Es wurde QDK-Python Repository erstellt, das `azure-quantum` , den Python-Client zum Übermitteln von Quantum-inspirierten Optimierungs Aufträgen an den Azure-Quantum-Dienst und, `qdk` einschließlich `qdk.chemistry` , eine Python-basierte Hilfsschicht für die Chemie Bibliothek umfasst, die eine Q# Molekulare Visualisierung und Funktionalität zum Generieren von Eingabedateien für verschiedene Chemie Pakete wie nwchem, Psi4 und openmolcas enthält.
- Klammern sind nun optional für Vorgangs-und Funktionstypen und- `if` , `elif` `while` -und- `until` Anweisungen. Klammern für `for` `use` die Anweisungen, und wurden als `borrow` veraltet markiert.
- Verbesserte breiten Schätzungen für optimale Tiefe finden Sie unter [Details](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/1159).
- Anwenden eines als explizite Matrix bereitgestellten einheitlichen Vorgangs mithilfe `ApplyUnitary` von ([quantenlibraries # 391](https://github.com/microsoft/QuantumLibraries/pull/391), externer Beitrag von Dmytro fedoriaka)
- Korrigiert, https://github.com/microsoft/iqsharp/issues/387 indem die Auswirkungen auf die Leistung beim Q# Kernel Start beeinträchtigt werden.

## <a name="version-0142011120240"></a>Version 0.14.2011120240

*Veröffentlichungsdatum: 25. November, 2020*

- Verbesserte compilerleistung aufgrund eines schnelleren Verweis Ladevorgangs.
- Der Sprachspezifikation wurde eine [antlr-Grammatik für Q# ](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language/5_Grammar) hinzugefügt Q# .
- Der [ `Microsoft.Quantum.Preparation` Namespace](xref:Microsoft.Quantum.Preparation) wurde so aktualisiert, dass er mit der Stil Anleitung und den API-Entwurfs Prinzipien konsistent ist, und um die Reinigung gemischter gemischter Zustände mit zusätzlichen Daten zu unterstützen (siehe [Vorschlag](https://github.com/microsoft/QuantumLibraries/issues/344), [Review Notes](https://github.com/microsoft/QuantumLibraries/blob/main/Design/meetings/2020/api-design-2020-11-05.md) und PRS [#212](https://github.com/microsoft/QuantumLibraries/pull/212), [#322](https://github.com/microsoft/QuantumLibraries/pull/322), [#375](https://github.com/microsoft/QuantumLibraries/pull/375), [#376](https://github.com/microsoft/QuantumLibraries/pull/376)).
- Runde Klammern um wiederholte Aufrufausdrücke sind jetzt optional: `(Foo(x))(y)` kann als geschrieben werden `Foo(x)(y)` .
- Benutzer der Visual Studio-oder Visual Studio Code Erweiterungen, die .net 5 oder Visual Studio 16,8 installiert haben, werden möglicherweise aufgefordert, .net Core 3,1 zu installieren, um weiterhin mit den Erweiterungen zu arbeiten.

Sehen Sie sich die vollständige Liste geschlossener PRS für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-10-23..2020-11-18), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-10-23..2020-11-18), [Laufzeit](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-10-23..2020-11-18), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-10-23..2020-11-18), [ Q# I](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-10-23..2020-11-18) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-10-23..2020-11-18)an.

## <a name="version-01320111004"></a>Version 0.13.20111004

*Veröffentlichungsdatum: 10. November, 2020*

Diese Version deaktiviert IntelliSense-Funktionen für Q# Dateien in Visual Studio und Visual Studio Code, wenn keine Projektdatei vorhanden ist. Dadurch wird ein Problem behoben, bei dem IntelliSense-Funktionen nach dem Hinzufügen einer neuen Datei zu einem Projekt möglicherweise nicht mehr funktionieren Q# (siehe [qsharp-Compiler # 720](https://github.com/microsoft/qsharp-compiler/issues/720)).

## <a name="version-01320102604"></a>Version 0.13.20102604

*Veröffentlichungsdatum: 27. Oktober, 2020*

Dieses Release enthält Folgendes:

- Die Ressourcenschätzung gibt jetzt zusätzlich zur Qubit-Anzahl gleichzeitig erreichbare tiefen und breiten Schätzungen aus. Ausführliche Informationen finden Sie [hier](xref:microsoft.quantum.machines.resources-estimator#metrics-reported).

Sehen Sie sich die vollständige Liste geschlossener PRS für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [Laufzeit](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22), [ Q# I](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-09-25..2020-10-22)an.

## <a name="version-01220100504"></a>Version 0.12.20100504

*Veröffentlichungsdatum: 5. Oktober, 2020*

Diese Version behebt einen Fehler, der sich auf das Laden von Q# Notebooks auswirkt (siehe [iqsharp # 331](https://github.com/microsoft/iqsharp/pull/331)).

## <a name="version-01220092803"></a>Version 0.12.20092803

*Veröffentlichungsdatum: 29. September, 2020*

Dieses Release enthält Folgendes:

- Ankündigungs-und Entwurfs Spezifikation der [Quantum Intermediate-Darstellung (Qir)](https://github.com/microsoft/qsharp-language/tree/main/Specifications/QIR#quantum-intermediate-representation-qir) , die als gemeinsames Format für verschiedene Front-und Back-Ends gedacht ist. Weitere Informationen finden Sie auch in unserem [Blogbeitrag](https://devblogs.microsoft.com/qsharp/introducing-quantum-intermediate-representation-qir) zu Qir.
- Das neue [ Q# sprach](https://github.com/microsoft/qsharp-language) Repository, das auch die vollständige [ Q# Dokumentation](https://github.com/microsoft/qsharp-language/tree/main/Specifications/Language#q-language)enthält, wird gestartet.
- Leistungsverbesserungen für "quantumschlag Simulator" für Programme, die eine große Anzahl von Qubits betreffen: bessere Anwendung von Gate-Fusionsentscheidungen. verbesserte Parallelisierung für Linux-System hinzugefügte intelligente Zeitplanung der Gate-Ausführung Fehlerbehebungen.
- IntelliSense-Funktionen werden jetzt für Q# Dateien in Visual Studio und Visual Studio Code auch ohne Projektdatei unterstützt.
- Verschiedene Q# /python Interoperabilitäts Verbesserungen und Fehlerbehebungen, einschließlich besserer Unterstützung für numpy-Datentypen.
- Verbesserungen am Microsoft. Quantum. Arrays-Namespace (siehe [Microsoft/quantumlibraries # 313](https://github.com/microsoft/QuantumLibraries/issues/313)).
- Es wurde ein neues [Beispiel für Wiederholung bis zum Erfolg](https://github.com/microsoft/Quantum/tree/main/samples/algorithms/repeat-until-success) hinzugefügt, in dem nur zwei Qubits verwendet werden.

Seit der letzten Version wurde der standardbranch in den einzelnen Open-Source-Depots in umbenannt `main` .

Sehen Sie sich die vollständige Liste geschlossener PRS für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [Laufzeit](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24), [ Q# I](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+closed%3A2020-08-24..2020-09-24)an.

## <a name="version-01220082513"></a>Version 0.12.20082513

*Veröffentlichungsdatum: 25. August, 2020*

Dieses Release enthält Folgendes:

- Neuer [Microsoft. Quantum. Random-Namespace](xref:Microsoft.Quantum.Random), der eine komfortablere Möglichkeit zum Stichprobenentnahme von zufälligen Werten in Q# Programmen bietet. ([Quantumschlag # 311](https://github.com/microsoft/QuantumLibraries/pull/311), [qsharp-Runtime # 328](https://github.com/microsoft/qsharp-runtime/pull/328))
- Der [Microsoft. Quantum. Diagnostics-Namespace](xref:Microsoft.Quantum.Diagnostics) wurde durch einen neuen [ `DumpOperation` Vorgang](xref:Microsoft.Quantum.Diagnostics.DumpOperation)und neue Vorgänge zum Einschränken der Qubit-Zuordnung und von Oracle-aufrufen verbessert. ([Quantumschlag # 302](https://github.com/microsoft/QuantumLibraries/pull/302))
- Neuer [ `%project` Magic-Befehl](xref:microsoft.quantum.iqsharp.magic-ref.project) in I Q# und [ `qsharp.projects` API](https://docs.microsoft.com/python/qsharp-core/qsharp.projects.projects) in Python, um Verweise auf Q# Projekte außerhalb des aktuellen Arbeitsbereichs Ordners zu unterstützen. Die aktuellen Einschränkungen dieses Features finden Sie unter [iqsharp # 277](https://github.com/microsoft/iqsharp/issues/277) . 
- Unterstützung für das automatische Laden von `.csproj` Dateien für I Q# /python-Hosts, sodass externe Projekt-oder Paket Verweise zur Initialisierungs Zeit geladen werden können. Weitere Informationen finden Sie im Handbuch zur Verwendung von [ Q# mit Python und jupyter Notebooks](xref:microsoft.quantum.guide.host-programs) .
- Das Beispiel "errorcorrection. Syndrome" wurde hinzugefügt
- Die anpassbare Kopplung wurde an simpleising hinzugefügt.
- Aktualisiertes hiddenshift-Beispiel.
- Beispiel für das Lösen von Sudoku mit dem Algorithmus von Grover (externer Beitrag) wurde hinzugefügt.
- Allgemeine Fehlerbehebungen.

Sehen Sie sich die vollständige Liste geschlossener PRS für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Laufzeit](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [ Q# I](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)an.  

## <a name="version-01220072031"></a>Version 0.12.20072031

*Veröffentlichungsdatum: 21. Juli, 2020*

Dieses Release enthält Folgendes:

- Geöffnete Namespaces in Q# Notebooks sind jetzt verfügbar, wenn alle zukünftigen Zellen ausgeführt werden. Dies ermöglicht beispielsweise, dass Namespaces einmal in einer Zelle am Anfang des Notebooks geöffnet werden, anstatt relevante Namespaces in jeder codezelle öffnen zu müssen. Mit einem neuen `%lsopen` Magic-Befehl wird die Liste der aktuell geöffneten Namespaces angezeigt.

Sehen Sie sich die vollständige Liste geschlossener PRS für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Laufzeit](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [ Q# I](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)an.  

## <a name="version-01220070124"></a>Version 0.12.20070124

*Veröffentlichungsdatum: 2. Juli, 2020*

Dieses Release enthält Folgendes:

- Neues `qdk-chem` Tool zum Umrechnen von Legacy-Serialisierungsformaten für elektronische Strukturprobleme (z. b. fcidump) in [broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)
- Neue Funktionen und Vorgänge im- [`Microsoft.Quantum.Synthesis`](xref:Microsoft.Quantum.Synthesis) Namespace für die Konsistenz Anwendung klassischer Oracles mithilfe von Transformations-und Zerlegungs Algorithmen.
- Q#Nun können Sie Argumente für die `%simulate` `%estimate` -,-und anderen Magic-Befehle zulassen. Weitere Informationen finden Sie in der [ `%simulate` Magic-Befehlsreferenz](xref:microsoft.quantum.iqsharp.magic-ref.simulate) .
- Neue Phasen Anzeigeoptionen in I Q# . Weitere Informationen finden Sie in der [ `%config` Magic-Befehlsreferenz](xref:microsoft.quantum.iqsharp.magic-ref.config) .
- I Q# und das `qsharp` Python-Paket werden nun über die Configuration Manager-Pakete ([qsharp](https://anaconda.org/quantum-engineering/qsharp) und [iqsharp](https://anaconda.org/quantum-engineering/iqsharp)) bereitgestellt, um die lokale Installation von Q# jupyter-und Python-Funktionen in einer Configuration Manager-Umgebung zu vereinfachen. Weitere Informationen finden Sie in den [ Q# jupyter-Notebooks](xref:microsoft.quantum.install.jupyter) und in den Installations Handbüchern von [ Q# python](xref:microsoft.quantum.install.python) .
- Bei Verwendung des Simulators müssen sich Qubits bei der Freigabe nicht mehr im Zustand | 0 ⟩ befinden. Sie können jedoch automatisch zurückgesetzt werden, wenn Sie unmittelbar vor der Freigabe gemessen wurden.
- Updates, um den Benutzern das Verwenden von Q# Bibliotheks Paketen mit unterschiedlichen QDK-Versionen zu erleichtern, sodass nur die neben Versionsnummern der Haupt & und nicht exakt derselben Version entsprechen.
- Veralteten `Microsoft.Quantum.Primitive.*` Namespace entfernt
- Verschoderte Vorgänge:
  - `Microsoft.Quantum.Intrinsic.Assert` ist jetzt `Microsoft.Quantum.Diagnostics.AssertMeasurement`
  - `Microsoft.Quantum.Intrinsic.AssertProb` ist jetzt `Microsoft.Quantum.Diagnostics.AssertMeasurementProbability`
- Behebung von Programmfehlern 

Sehen Sie sich die vollständige Liste geschlossener PRS für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Laufzeit](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [ Q# I](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)an.  

## <a name="version-0112006403"></a>Version 0.11.2006.403

*Veröffentlichungsdatum: 4. Juni 2020*

Diese Version behebt einen Fehler, der die Kompilierung von Q# Projekten beeinträchtigt.

## <a name="version-0112006207"></a>Version 0.11.2006.207

*Veröffentlichungsdatum: 3. Juni 2020*

Dieses Release enthält Folgendes:

- Q# Notebooks und python-Host Programme treten nicht mehr auf, wenn ein Q# Einstiegspunkt vorhanden ist.
- Die [Standardbibliothek](xref:microsoft.quantum.libraries.standard.intro) wurde aktualisiert, um die Verwendung von Zugriffsmodifizierern zu ermöglichen.
- Der Compiler ermöglicht jetzt das Einfügen von Umschreibungsschritten zwischen integrierten Umschreibungsschritten.
- Einige veraltete Funktionen und Vorgänge wurden gemäß dem in den [API-Prinzipien](xref:microsoft.quantum.contributing.api-design) beschriebenen Zeitplan entfernt. Q# Programme und Bibliotheken, die in Version 0.11.2004.2825 ohne Warnungen erstellt werden, funktionieren weiterhin unverändert.

Sehen Sie sich die vollständige Liste geschlossener PRS für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Laufzeit](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed), [ Q# I](https://github.com/microsoft/iqsharp/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed)an.  

> [!NOTE]
> Diese Version enthält einen Fehler, der die Kompilierung von Q# Projekten beeinträchtigt. Wir empfehlen das Upgrade auf ein neueres Release.

## <a name="version-01120042825"></a>Version 0.11.2004.2825

*Veröffentlichungsdatum: 30. April 2020*

Dieses Release enthält Folgendes:

- Neue Unterstützung für Q# Anwendungen, die keine c#-oder python-Hostdatei mehr benötigen. Weitere Informationen zu den ersten Schritten mit Q# Anwendungen finden Sie [hier](xref:microsoft.quantum.install.standalone).
- Der Schnellstart für den Quantum-Zufallszahlengenerator wurde so aktualisiert, dass keine C#- oder Python-Hostdatei mehr erforderlich ist. Siehe aktualisierter [Schnellstart](xref:microsoft.quantum.quickstarts.qrng)
- Leistungsverbesserungen bei I Q# docker-Images

> [!NOTE]
> Q# Anwendungen, die das neue-Attribut verwenden, [`@EntryPoint()`](xref:Microsoft.Quantum.Core.EntryPoint) können derzeit nicht von Python-oder .NET-Host Programmen aufgerufen werden.
> Weitere Informationen finden Sie in den Leitfäden für [Python](xref:microsoft.quantum.install.python)- und [.NET-Interoperabilität](xref:microsoft.quantum.install.cs).

## <a name="version-01120033107"></a>Version 0.11.2003.3107

*Veröffentlichungsdatum: 31. März 2020*

Dieses Release enthält kleinere Fehlerbehebungen für die Version 0.11.2003.2506.

## <a name="version-01120032506"></a>Version 0.11.2003.2506

*Veröffentlichungsdatum: 26. März 2020*

Dieses Release enthält Folgendes:

- Neue Unterstützung für Zugriffsmodifizierer in. Q# Weitere Informationen finden Sie unter [Access Modifizierer](xref:microsoft.quantum.qsharp.accessmodifiers)
- Aktualisiert auf .NET Core SDK 3.1

Hier finden Sie die vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020022610"></a>Version 0.10.2002.2610

*Veröffentlichungsdatum: 27. Februar 2020*

Dieses Release enthält Folgendes:

- Neue Quantum Machine Learning-Bibliothek. Weitere Informationen finden Sie auf unserer [QML-Seite](xref:microsoft.quantum.machine-learning.concepts.intro).
- Q#Fehlerbehebungen, was zu einer Leistungssteigerung von 10 bis 20 Mal beim Laden von nuget-Paketen führt

Hier finden Sie die vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01020012831"></a>Version 0.10.2001.2831

*Veröffentlichungsdatum: 29. Januar 2020*

Dieses Release enthält Folgendes:

- Neues NuGet-Paket „Microsoft.Quantum.SDK“, mit dem das NuGet-Paket „Microsoft.Quantum.Development.Kit“ bei der Erstellung neuer Projekte ersetzt wird. Das NuGet-Paket „Microsoft.Quantum.Development.Kit“ wird für vorhandene Projekte weiter unterstützt. 
- Unterstützung für Q# compilererweiterungen, die vom neuen Microsoft. Quantum. SDK nuget-packge aktiviert werden. Weitere Informationen finden Sie [in der Dokumentation auf GitHub](https://github.com/microsoft/qsharp-compiler/tree/main/src/QuantumSdk#extending-the-q-compiler), im [Beispiel zu compilererweiterungen](https://github.com/microsoft/qsharp-compiler/tree/main/examples/CompilerExtensions) und im [ Q# dev-Blog](https://devblogs.microsoft.com/qsharp/extending-the-q-compiler/) .
- Unterstützung für .NET Core 3.1 hinzugefügt. Wir empfehlen Ihnen dringend, Version 3.1.100 zu installieren, da es bei Buildvorgängen mit früheren .NET Core SDK-Versionen zu Problemen kommen kann.
- Neue Compilertransformationen verfügbar unter „Microsoft.Quantum.QsCompiler.Experimental“.
- Neue Funktionalität zur Offenlegung von Ausgabe Zustands Vektoren als HTML in IQ#
- EstimateFrequencyA-Unterstützung zu Microsoft.Quantum.Characterization für Hadamard- und SWAP-Tests hinzugefügt.
- Der "modifitudeverstärkernamespace" verwendet jetzt eine Q# Stil Anleitung.

Hier finden Sie die vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019120501"></a>Version 0.10.1912.0501

*Veröffentlichungsdatum: 5. Dezember 2019*

Dieses Release enthält Folgendes:

- Neues Test Attribut für Komponenten Q# Tests finden Sie [hier](xref:microsoft.quantum.guide.testingdebugging) in der [](xref:Microsoft.Quantum.Diagnostics.Test) aktualisierten API-Dokumentation und im Thema aktualisierte Tests & Debuggen.
- Im Fall eines Q# Programmlauf Fehlers wurde eine Stapel Überwachung hinzugefügt.
- Unterstützung für Breakpoints in Visual Studio Code aufgrund einer Aktualisierung der [OmniSharp-C#-Erweiterung für Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)

Hier finden Sie die vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Version 0.10.1911.1607

*Veröffentlichungsdatum: 17. November 2019*

Dieses Release enthält Folgendes:

- Behebung von Leistungsproblemen für [Quanten-Katas](https://github.com/Microsoft/QuantumKatas) und Jupyter Notebook-Instanzen

Hier finden Sie die vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Version 0.10.1911.307

*Veröffentlichungsdatum: 1. November 2019*

Dieses Release enthält Folgendes:

- Updates für Visual Studio Code & Visual Studio-Erweiterungen zur Bereitstellung von Language Server als eigenständige ausführbare Datei, die die Abhängigkeit der .net Core SDK Version beseitigt.  
- Migration zu .NET Core 3.0
- Breaking Change an Microsoft.Quantum.Simulation.Core.IOperationFactory mit Einführung der neuen `Fail`-Methode. Dies betrifft nur benutzerdefinierte Simulatoren, die SimulatorBase nicht erweitern. Weitere Informationen finden Sie im [Pull Request auf GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).
- Neue Unterstützung für veraltete Attribute

Hier finden Sie die vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Version 0.9.1909.3002

*Veröffentlichungsdatum: 30. September 2019*

Dieses Release enthält Folgendes:

- Neue Unterstützung für die Q# Codevervollständigung in Visual Studio 2019 (Versionen 16,3 & später) & Visual Studio Code
- neues [Quantum Kata](https://github.com/Microsoft/QuantumKatas) für Quantenaddierer

Hier finden Sie die vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Version 0.9 (*PackageReference 0.9.1908.2902*)

*Veröffentlichungsdatum: 29. August 2019*

Dieses Release enthält Folgendes:

- Neue Unterstützung für [Konjugations Anweisungen](xref:microsoft.quantum.qsharp.conjugations#conjugations) in Q#
- neue Codeaktionen im Compiler wie beispielsweise „Ersetzen durch“, „Add documentation“ (Dokumentation hinzufügen) und Updates für einfache Arrayelemente
- Installationsvorlagen und neue Projektbefehle für die Visual Studio Code-Erweiterung
- neue Varianten des ApplyIf-Kombinators wie beispielsweise [Microsoft.Quantum.Canon.ApplyIfOne](xref:Microsoft.Quantum.Canon.ApplyIfOne)
- zusätzliche in Jupyter Notebook konvertierte [Quantum Katas](https://github.com/Microsoft/QuantumKatas)
- Für die Visual Studio-Erweiterung ist jetzt Visual Studio 2019 erforderlich.

Hier finden Sie die vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), [Compiler](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), [Runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) und [Katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

Hier werden die Änderungen sowie Anweisungen zum Aktualisieren vorhandener Programme beschrieben.  Weitere Informationen zu diesen Änderungen finden Sie im [ Q# dev-Blog](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>Version 0.8 (*PackageReference 0.8.1907.1701*)

*Veröffentlichungsdatum: 12. Juli 2019*

Dieses Release enthält Folgendes:

- Neue Indizierung für das Aufteilen von Arrays finden Sie in [der Sprachreferenz](xref:microsoft.quantum.qsharp.contextualexpressions#contextual-and-omitted-expressions) , um weitere Informationen zu erhalten.
- Hinzu [ Q# gefügter](https://github.com/microsoft/iqsharp/blob/main/README.md) dockerfile-Datei, die auf dem [Microsoft-Container Registry](https://github.com/microsoft/ContainerRegistry)gehostet wird, finden Sie im I-Repository
- wichtige Änderungen für den [Ablaufverfolgungssimulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro), Updates für Konfigurationseinstellungen und Namensänderungen (siehe [.NET-API-Browser für die aktualisierten Namen](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration))

Hier finden Sie eine vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) und [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Version 0.7 (*PackageReference 0.7.1905.3109*)

*Veröffentlichungsdatum: 31. Mai 2019*

Dieses Release enthält Folgendes:
- Ergänzungen zur Q# Sprache, 
- Aktualisierungen der Quantum Chemistry Library (Quantenchemiebibliothek) 
- neue numerische Bibliothek

Hier finden Sie eine vollständige Liste geschlossener Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) und [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Hier werden die Änderungen sowie Anweisungen zum Aktualisieren vorhandener Programme beschrieben.  Weitere Informationen zu diesen Änderungen finden Sie im [ Q# dev-Blog](https://devblogs.microsoft.com/qsharp).

### <a name="no-locq-language-syntax"></a>Q# Sprachsyntax
Mit dieser Version wird eine neue Q# Sprachsyntax hinzugefügt:
* Fügen Sie benannte Elemente für [benutzerdefinierte Typen] Microsoft. Quantum. qsharp. typedeklarationen # Type-Deklarationen hinzu.  
* benutzerdefinierte Typkonstruktoren für die Verwendung als Funktionen
* Unterstützung für [copy-and-update](xref:microsoft.quantum.qsharp.copyandupdateexpressions#copy-and-update-expressions) und [apply-and-reassign](xref:microsoft.quantum.qsharp.variabledeclarationsandreassignments#evaluate-and-reassign-statements) in benutzerdefinierten Typen
* optionales Blockieren von Fehlerbehebungen im Zusammenhang mit [repeat-until-success](xref:microsoft.quantum.qsharp.conditionalloops#repeat-statement)-Schleifen
* Unterstützung für while-Schleifen in Funktionen (nicht in Vorgängen)

### <a name="library"></a>Bibliothek 

Mit diesem Release wird eine numerische Bibliothek hinzugefügt: Informieren Sie sich über die [Verwendung der numerischen Bibliothek](xref:microsoft.quantum.numerics.usage), und probieren Sie die [neuen Beispiele](https://github.com/microsoft/quantum/tree/main/Numerics) aus.  [PR #102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Mit diesem Release werden Erweiterungen neu organisiert, und die Chemiebibliothek wird aktualisiert:
* verbesserte Modularität von Komponenten, der Erweiterbarkeit und allgemeine Codebereinigung  [PR #58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Unterstützung für [Multireferenz-Wellenfunktionen](xref:microsoft.quantum.chemistry.concepts.multireference) (sowohl für Multireferenz-Wellenfunktionen als auch für einheitlich verbundene Cluster).  [PR #110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Vielen Dank!) [1QBit](https://1qbit.com)-Mitwirkender ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)): Energieauswertung mithilfe eines variablen Ansatzes. [PR #120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Aktualisieren des [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge)-Schemas auf die neue [Version 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2) und Hinzufügen einer einheitlichen gekoppelten Clusterspezifikation. [Issue #65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Hinzufügen der Python-Interoperabilität zu Chemiebibliothekfunktionen Testen Sie dieses [Beispiel](https://github.com/microsoft/Quantum/tree/main/Chemistry/PythonIntegration). [Problem 53](https://github.com/microsoft/QuantumLibraries/issues/53) [PR 110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Version 0.6.1905

*Veröffentlichungsdatum: 3. Mai 2019*

Dieses Release enthält Folgendes:
- nimmt Änderungen an der Q# Sprache vor. 
- Neustrukturierung der Bibliotheken des Quantum Development Kit 
- neue Beispiele 
- Fehlerbehebungen  (sämtliche geschlossene Pull Requests für [Bibliotheken](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) und [Beispiele](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed))  

Hier werden die Änderungen sowie Anweisungen zum Aktualisieren vorhandener Programme beschrieben.  Weitere Informationen zu diesen Änderungen finden Sie unter devblogs.microsoft.com/qsharp.

### <a name="no-locq-language-syntax"></a>Q# Sprachsyntax
Mit dieser Version wird eine neue Q# Sprachsyntax hinzugefügt:
* Fügen Sie eine [schnelle Methode zum Ausdrücken von Spezialisierungen von Quantenvorgängen](xref:microsoft.quantum.qsharp.specializationdeclarations) (Steuerelement und Adjunkte) mit `+`-Operatoren hinzu.  Die frühere Syntax ist veraltet.  Programme, die die alte Syntax verwenden (z. B. `: adjoint`), funktionieren auch weiterhin, es wird jedoch eine Warnung zur Kompilierzeit generiert.  
* Durch Hinzufügen eines neuen ternären Operators für [Copy-and-Update](xref:microsoft.quantum.qsharp.copyandupdateexpressions#copy-and-update-expressions), `w/` `<-` kann die Array Erstellung als Änderung eines vorhandenen Arrays ausgedrückt werden.
* Fügen Sie die Common [Apply-and-REASSIGN-Anweisung](xref:microsoft.quantum.qsharp.variabledeclarationsandreassignments#evaluate-and-reassign-statements)hinzu, z. b., `+=` , `w/=` .
* Fügen Sie eine Methode zum Angeben eines kurzen Namens für Namespaces in [offenen Direktiven](xref:microsoft.quantum.qsharp.namespaces#open-directives) hinzu.

Mit diesem Release ist es nicht mehr möglich, ein Arrayelement auf der linken Seite einer set-Anweisung anzugeben.  Dies liegt daran, dass diese Syntax impliziert, dass Arrays veränderbar sind, wenn das Ergebnis des Vorgangs tatsächlich immer das Erstellen eines neuen Arrays mit der Änderung war.  Stattdessen wird ein Compilerfehler mit dem Vorschlag generiert, den neuen copy-and-update-Operator (`w/`) zu verwenden, um das gleiche Ergebnis zu erzielen.  

### <a name="library-restructuring"></a>Umstrukturierung der Bibliothek
Mit diesem Release werden die Bibliotheken neu organisiert, um ein konsistentes Wachstum zu ermöglichen:
* Der Namespace Microsoft.Quantum.Primitive wird in Microsoft.Quantum.Intrinsic umbenannt.  Diese Vorgänge werden vom Zielcomputer implementiert.  Der Namespace Microsoft.Quantum.Primitive ist veraltet.  Eine Runtimewarnung informiert Sie darüber, wann Programme mithilfe von veralteten Namen Vorgänge und Funktionen aufrufen.

* Das Paket Microsoft.Quantum.Canon wird in Microsoft.Quantum.Standard umbenannt.  Dieses Paket enthält Namespaces, die von den meisten Q# Programmen gemeinsam sind.  Dies schließt Folgendes ein:  
    - Microsoft.Quantum.Canon-Paket für allgemeine Vorgänge
    - Microsoft.Quantum.Arithmetic für universelle arithmetische Operationen
    - Microsoft.Quantum.Preparation für Vorgänge zum Vorbereiten des Qubit-Zustands.
    - Microsoft.Quantum.Simulation für die Simulationsfunktionalität

Durch diese Änderung treten bei Programmen, die eine einzelne „Open“-Anweisung für den Namespace Microsoft.Quatum.Canon enthalten, möglicherweise Buildfehler auf, wenn das Programm auf Vorgänge verweist, die in die anderen drei neuen Namespaces verschoben wurden.  Das Hinzufügen zusätzlicher „Open“-Anweisungen für die drei neuen Namespaces ist eine einfache Möglichkeit, dieses Problem zu beheben.  

* Mehrere Namespaces sind veraltet, da die Vorgänge in anderen Namespaces neu organisiert wurden. Programme, die diese Namespaces verwenden, funktionieren weiterhin. Eine Warnung zur Kompilierzeit bezeichnet den Namespace, in dem der Vorgang definiert ist.  

* Das Namespace Microsoft.Quantum.Arithmetic wurde normalisiert, um den benutzerdefinierten <xref:Microsoft.Quantum.Arithmetic.LittleEndian>-Typ zu verwenden. Verwenden Sie bei Bedarf die Funktion [BigEndianAsLittleEndian](xref:Microsoft.Quantum.Arithmetic.BigEndianAsLittleEndian) für die Konvertierung zu Little-Endian.  

* Die Namen mehrerer callables (Funktionen und Vorgänge) wurden so geändert, dass Sie dem [ Q# Stil Handbuch](xref:microsoft.quantum.contributing.style)entsprechen.  Die alten Callable-Namen sind veraltet.  Programme, die die alten Callables-Namen verwenden, funktionieren weiterhin. Es wird eine Warnung zur Kompilierzeit generiert. 

### <a name="new-samples"></a>Neue Beispiele

Wir haben ein [Beispiel für die Verwendung Q# mit dem F #-Treiber](https://github.com/Microsoft/Quantum/pull/164)hinzugefügt.  

**Besonderer Dank** gilt dem folgenden Mitwirkenden an der offenen Codebasis unter http://github.com/Microsoft/Quantum. Diese Beiträge ergänzen die umfangreichen Codebeispiele erheblich Q# :

* Mathias Soeken ([@msoeken](https://github.com/msoeken)): Oracle-Funktionssynthese. [PR #135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migrieren vorhandener Projekte zu Version 0.6.1905

Informationen zum Aktualisieren des Microsoft Quantum Development Kit finden Sie im [Installationshandbuch](xref:microsoft.quantum.install).
  
Wenn Sie über vorhandene Q# Projekte aus Version 0,5 des quantumentwicklungskit verfügen, sind die folgenden Schritte erforderlich, um diese Projekte zur neuesten Version zu migrieren.

1. Projekte müssen in der richtigen Reihenfolge aktualisiert werden.  Wenn Sie über eine Projektmappe mit mehreren Projekten verfügen, sollten Sie jedes Projekt in der Reihenfolge aktualisieren, in der darauf verwiesen wird.
2. Führen Sie an einer Eingabeaufforderung aus, `dotnet clean` um alle vorhandenen Binärdateien und zwischen Dateien zu entfernen.
3. Bearbeiten Sie in einem Text-Editor die CSPROJ-Datei, um die Version von den Microsoft.Quantum-`PackageReference`-Paketen auf Version 0.6.1904 zu ändern. Ändern Sie außerdem den Paketnamen „Microsoft.Quantum.Canon“ in „Microsoft.Quantum.Standard“. Beispiel:

    ```xml
    <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
    <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
    ```
4. Führen Sie an der Eingabeaufforderung den folgenden Befehl aus: `dotnet msbuild`  
5. Aufgrund der oben aufgeführten Änderungen müssen Sie die Fehler danach möglicherweise dennoch manuell beheben.  In vielen Fällen werden diese Fehler auch von IntelliSense in Visual Studio oder Visual Studio Code gemeldet.
    - Öffnen Sie den Stammordner des Projekts oder die entsprechende Projektmappe in Visual Studio 2019 oder Visual Studio Code.
    - Nachdem Sie eine QS-Datei im Editor geöffnet haben, sollte die Ausgabe der Q# Spracherweiterung im Fenster Ausgabe angezeigt werden.
    - Öffnen Sie nach dem erfolgreichen Laden des Projekts (im Ausgabefenster angegeben) jede Datei, um alle verbleibenden Probleme manuell zu beheben.

> [!NOTE]
> * Bei Version 0.6 unterstützt der im Quantum Development Kit enthaltene Sprachserver nur einen Arbeitsbereich.
> * Öffnen Sie den Stammordner, der das Projekt selbst und alle verwiesene Projekte enthält, um mit einem Projekt in Visual Studio Code arbeiten zu können.   
> * Damit Sie mit einer Projektmappe in Visual Studio arbeiten können, müssen sich alle in der Projektmappe enthaltenen Projekte im selben Ordner wie die Projektmappe oder in einem ihrer Unterordner befinden.  
> * Verweise zwischen Projekten, die zu Version 0.6 oder höher migriert wurden, und Projekte, die ältere Paketversionen verwenden, werden **nicht** unterstützt.

## <a name="version-051904"></a>Version 0.5.1904

*Veröffentlichungsdatum: 15. April 2019*

Dieses Release enthält Fehlerbehebungen.


## <a name="version-051903"></a>Version 0.5.1903

*Veröffentlichungsdatum: 27. März 2019*

Dieses Release enthält Folgendes:

- Bietet Unterstützung für Jupyter Notebook, die eine hervorragend Möglichkeit bietet, sich über vertraut zu machen Q# .  [Sehen Sie sich die neuen Jupyter Notebook-Beispiele an, und lernen Sie, wie Sie eigene Notebooks schreiben](xref:microsoft.quantum.install). 

- Hinzufügen der ganzzahligen Addiererarithmetik zur Quantum Canon-Bibliothek.  Befassen Sie sich mit einem Jupyter Notebook, in dem [beschrieben wird, wie die neuen ganzzahligen Addierer verwendet werden](https://github.com/microsoft/Quantum/blob/main/samples/arithmetic/AdderExample.ipynb).

- Problembehebung für das von der Community gemeldete DumpRegister-Issue ([#148](https://github.com/Microsoft/Quantum/issues/148))

- Die Möglichkeit zum Zurückgeben von innerhalb einer [using-und-Kredit Anweisung](xref:microsoft.quantum.qsharp.quantummemorymanagement#quantum-memory-management)wurde hinzugefügt.

- überarbeiteter [Leitfaden zu den ersten Schritten](xref:microsoft.quantum.install)


## <a name="version-051902"></a>Version 0.5.1902

*Veröffentlichungsdatum: 27. Februar 2019*

Dieses Release enthält Folgendes:

- Es wurde die Unterstützung für einen plattformübergreifenden Python-Host hinzugefügt.  Das `qsharp` Paket für python vereinfacht das simulieren Q# von Vorgängen und Funktionen innerhalb von Python. Hier finden Sie weitere Informationen zur [Python-Interoperabilität](xref:microsoft.quantum.install). 

- Die Visual Studio- und Visual Studio Code-Erweiterungen unterstützen jetzt das Umbenennen von Symbolen (z. B. Funktionen und Vorgänge).

- Die Visual Studio-Erweiterung kann jetzt in Visual Studio 2019 installiert werden.

## <a name="version-041901"></a>Version 0.4.1901

*Veröffentlichungsdatum: 30. Januar 2019*

Dieses Release enthält Folgendes:

- Unterstützung für den neuen primitiven Typ „BigInt“, der eine ganze Zahl mit Vorzeichen beliebiger Größe darstellt.  Weitere Informationen finden Sie unter [bigint](xref:microsoft.quantum.qsharp.valueliterals#bigint-literals).
- neuer spezieller und schneller Toffoli-Simulator, mit dem X-, CNOT- und mehrfach gesteuerte X-Quantenvorgänge mit einer großen Anzahl von Qubits simuliert werden können.  Weitere Informationen zum [Toffoli-Simulator](xref:microsoft.quantum.machines.toffoli-simulator) finden Sie hier.
- Fügt eine einfache Ressourcenschätzung hinzu, die die Ressourcen schätzt, die zum Ausführen einer bestimmten emulatorinstanz eines Q# Vorgangs auf einem Quantum-Computer erforderlich sind.  Weitere Informationen zur [Ressourcenschätzung](xref:microsoft.quantum.machines.resources-estimator) finden Sie hier.


## <a name="version-0318112802"></a>Version 0.3.1811.2802

*Veröffentlichungsdatum: 28. November 2018*

Obwohl diese Version bei der Visual Studio Code-Erweiterung nicht verwendet wurde, wurde sie gekennzeichnet und im Rahmen der [Bereinigung der Erweiterungen](https://code.visualstudio.com/blogs/2018/11/26/event-stream) im Zusammenhang mit dem NPM-Paket `event-stream` aus dem Marketplace entfernt. Diese Version entfernt alle Runtimeabhängigkeiten, die dazu führen könnten, dass die Erweiterung rote Flags auslöst.

Wenn Sie die Erweiterung zuvor installiert haben, müssen Sie sie noch mal installieren, indem Sie im Visual Studio Marketplace die [Microsoft Quantum Development Kit for Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode)-Erweiterung aufrufen und auf „Installieren“ klicken. Wir entschuldigen uns für die Unannehmlichkeiten.


## <a name="version-0318111511"></a>Version 0.3.1811.1511

*Veröffentlichungsdatum: 20. November 2018*

Mit diesem Release wird ein Fehler behoben, der verhindert hat, dass einige Benutzer die Visual Studio-Erweiterung erfolgreich herunterladen können.

## <a name="version-031811203"></a>Version 0.3.1811.203

*Veröffentlichungsdatum: 2. November 2018*

Dieses Release enthält unter anderem folgende Fehlerbehebungen:

* Durch das Aufrufen von `DumpMachine` kann der Zustand des Simulators in bestimmten Situationen geändert werden.
* Beim Entwickeln von Projekten mithilfe einer Version von .NET Core (vor Version 2.1.403) wurden Warnungen zur Kompilierzeit entfernt.
* Die Dokumentation wurde besonders hinsichtlich der QuickInfos überarbeitet, die während des Bewegens des Mauszeigers in Visual Studio Code oder Visual Studio angezeigt werden.

## <a name="version-0318102508"></a>Version 0.3.1810.2508

*Veröffentlichungsdatum: 29. Oktober 2018*

Dieses Release enthält neue Sprachfeatures und bietet eine verbesserte Entwicklerumgebung:

* Diese Version enthält einen Sprachserver für sowie Q# die Client Integrationen für Visual Studio und Visual Studio Code. Dies ermöglicht die Nutzung einer ganzen Reihe neuer IntelliSense-Features sowie Livefeedback beim Schreiben in Form von gewellten Unterstreichungen von Fehlern und Warnungen. 
* Durch die einfache Navigation zu und präzise Bereiche für Diagnosen sowie zusätzliche Details in den angezeigten Informationsfeldern werden die Diagnosemeldungen mit diesem Update im Allgemeinen verbessert.
* Die Q# Sprache wurde so erweitert, dass Sie die Art und Weise vereinheitlicht, wie Entwickler häufige Vorgänge ausführen können, sowie neue Verbesserungen an den sprach Features, um die Quantum-Berechnung zu berechnen.  Es gibt eine Handvoll grundlegende Änderungen an der Q# Sprache in dieser Version.   

Dieses Release umfasst auch eine neue Quantum Chemistry Library (Quantenchemiebibliothek):

* Die Chemiebibliothek enthält neue Hamilton-Simulationsfeatures einschließlich der folgenden:
    - Trotter-Suzuki-Integratoren in beliebiger, gleichmäßiger Reihenfolge für verbesserte Simulationsgenauigkeit
    - Qubit-Simulationstechnik mit chemiespezifischen Optimierungen zum Reduzieren der Komplexität des $T$-Gates
* neu eingeführtes Open-Source-Schema namens Broombridge-Schema (bezugnehmend auf ein als Geburtsort der Hamiltonians gefeiertes [Wahrzeichen](https://en.wikipedia.org/wiki/Broom_Bridge)) zum Importieren von Darstellungen von Molekülen und deren Simulation
* mehrere mithilfe des Broombridge-Schemas definierte chemische Darstellungen.  Diese Modelle wurden von [NWChem](http://www.nwchem-sw.org/), einem leistungsstarken Open-Source-Tool für computergestützte Chemie, generiert.
* Tutorials und Beispiele zur Erklärung der Verwendung der Chemiebibliothek und der Broombridge-Datenmodelle für Folgendes:
    - Konstruieren einfacher Hamilton-Funktionen mithilfe der Chemiebibliothek
    - Visualisieren des Bodens und angeregter Energiezustände von Lithiumhybrid mithilfe der Phasenschätzung
    - Ausführen von Ressourcenschätzungen der Quantenchemiesimulation
    - Schätzen des Energieniveaus von Molekülen, die vom Broombridge-Schema dargestellt werden
* In der Dokumentation wird die Verwendung von nwchem zum Generieren zusätzlicher chemischer Modelle für die Quantum-Simulation mit beschrieben Q# .

Hier erhalten Sie weitere Informationen zur [Quantum Development Kit-Chemiebibliothek](xref:microsoft.quantum.chemistry.concepts.intro).

Mit der neuen Chemiebibliothek verschieben wir die Bibliotheken in das neue GitHub-Repository [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Die Beispiele befinden sich im Repository [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  Wir freuen uns über Beiträge zu beiden Repositorys.

Diese Version enthält Fehlerbehebungen und Features für Probleme, die von der Community gemeldet wurden.

### <a name="community-contributions"></a>Beiträge der Community

**Besonderer Dank** gilt den folgenden Mitwirkenden an der offenen Codebasis unter http://github.com/Microsoft/Quantum. Diese Beiträge ergänzen die umfangreichen Codebeispiele erheblich Q# :

* Rolf Huisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): die Leistung für QASM/ Q# Entwickler wurde verbessert, indem ein QASM für die Übersetzer erstellt wurde Q# . [PR #58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)):  implementierte das CHSH-Spiel als Beispiel. Dies ist ein Quantenspiel zur Nichtlokalität.  [PR #84](https://github.com/Microsoft/Quantum/pull/84).

Außerdem danken wir Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[PR #90](https://github.com/Microsoft/quantum/pull/90)), Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[PR #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) und Lee James O'Riordan ([@mlxd](https://github.com/mlxd),[PR #96](https://github.com/Microsoft/Quantum/pull/96)) für ihre Beiträge zur Verbesserung der Inhalte durch Korrekturen an der Dokumentation, Rechtschreibung und Tippfehlern. 

## <a name="version-021809701"></a>Version 0.2.1809.701

*Veröffentlichungsdatum: 10. September 2018*

Dieses Release enthält Fehlerbehebungen zu Problemen, die von der Community gemeldet wurden.

## <a name="version-0218063001"></a>Version 0.2.1806.3001

*Veröffentlichungsdatum: 30. Juni 2018*

Diese Veröffentlichung ist nur eine kurze Lösung für [Probleme, die auf GitHub gemeldet #48](https://github.com/Microsoft/Quantum/issues/48) ( Q# Kompilierung schlägt fehl, wenn der Benutzername ein Leerzeichen enthält). Für die entsprechende neue Version `0.2.1806.3001-preview` gelten dieselben Updateanweisungen wie für Version `0.2.1806.1503`.

## <a name="version-0218061503"></a>Version 0.2.1806.1503

*Veröffentlichungsdatum: 22. Juni 2018*

Dieses Release enthält mehrere Beiträge der Community sowie eine verbesserte Debugfunktionen und Leistungsverbesserungen.  Dies gilt insbesondere in folgenden Fällen:

* Leistungsverbesserungen für kleine und große Simulationen für den QuantumSimulator-Zielcomputer
* Verbesserte Debugfunktionen
* Communitybeiträge zu Problembehebungen, Hilfsfunktionen, Vorgängen und neue Beispiele

### <a name="performance-improvements"></a>Leistungsverbesserungen

Dieses Update umfasst bedeutende Leistungsverbesserungen für die Simulation einer kleinen oder großen Anzahl von Qubits für alle Zielcomputer.  Diese Verbesserung ist bei der H<sub>2</sub>-Simulation besonders sichtbar. Dies ist ein Standardbeispiel im Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Verbesserte Debugfunktionen

In diesem Update wurden neue Debugfunktionen hinzugefügt:
* Die zwei neuen Vorgänge @"microsoft.quantum.extensions.diagnostics.dumpmachine" und @"microsoft.quantum.extensions.diagnostics.dumpregister" wurden hinzugefügt, die Wave-Funktionsinformationen über den Zielquantencomputer zu einem bestimmten Zeitpunkt zurückgeben.  
* Die Wahrscheinlichkeit zum Messen von $\ket{1}$ für ein einzelnes Qubit wird in Visual Studio nun automatisch im Debugfenster für den QuantumSimulator-Zielcomputer angezeigt.
* In Visual Studio wurde die Anzeige von Variableneigenschaften in den Debugfenstern **Auto** und **Lokal** verbessert. 

Erfahren Sie mehr über das [Testen und Debuggen](xref:microsoft.quantum.guide.testingdebugging).

### <a name="community-contributions"></a>Beiträge der Community

Die Q# CommunityCommunity wächst, und wir sind begeistert, dass die ersten vom Benutzer bereitgestellten Bibliotheken und Beispiele angezeigt werden, die an unsere Open-Codebasis übermittelt wurden http://github.com/Microsoft/quantum .  **Vielen Dank** an die folgenden Mitwirkenden:
* Mathias Soeken ([@msoeken](https://github.com/msoeken)) hat ein Beispiel zum Definieren einer transformationsbasierter Logiksynthesemethode beigesteuert, die Toffoli-Netzwerke zum Implementieren einer gegebenen Permutation erstellt. Der Code wird vollständig in Q# Funktionen und Operationen geschrieben.  [PR #41](https://github.com/Microsoft/Quantum/pull/41).
* Rolarhuisman ( [@RolfHuisman](https://github.com/RolfHuisman) ): Microsoft MVP Rolf Huisman hat ein Beispiel bereitgestellt, das flatqasm Q# -Code aus dem Code für eine eingeschränkte Klasse von Programmen generiert, die keine klassische Ablauf Steuerung und eingeschränkte Quantum-Vorgänge aufweisen. [PR #59](https://github.com/Microsoft/Quantum/pull/59).
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)) verbesserte unsere Codebasis mit einer Bibliotheksfunktion für gesteuerte Vorgänge. [PR #53](https://github.com/Microsoft/Quantum/pull/53).
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)) behob @"microsoft.quantum.canon.quantumphaseestimation" und erstellte neue Komponententests.  [PR #54](https://github.com/Microsoft/Quantum/pull/54).
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)) bereinigte das Beispiel „Teleportation“, indem sichergestellt wird, dass die QuantumSimulator-Instanz verworfen wird. [PR #20](https://github.com/Microsoft/Quantum/pull/20).

Außerdem **danken** wir den folgenden mitwirkenden Microsoft Software Engineers des Commercial Engineering Services-Teams, die während ihres Hackathons wertvolle Änderungen an unserer Dokumentation vorgenommen haben.  Ihre Änderungen sorgten für deutliche Verbesserungen an der Verständlichkeit und dem Onboarding für uns alle:
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Update für vorhandene Projekte

Dieses Release ist vollständig abwärtskompatibel. Sie können einfach Updates für die NuGet-Pakete in Ihren Projekten auf Version `0.2.1806.1503-preview` und eine **vollständige Neuerstellung** durchführen, um sicherzustellen, dass alle Zwischendateien wiederhergestellt werden.

Befolgen Sie die normalen Anweisungen zum Durchführen eines [Paketupdates](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package) über Visual Studio.

Führen Sie den folgenden Befehl aus, um Updates für Projektvorlagen über die Befehlszeile durchzuführen.
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

Nachdem Sie diesen Befehl ausgeführt haben, nutzen alle neuen Projekte, die mithilfe von `dotnet new <project-type> -lang Q#` erstellt werden, automatisch diese Version des Quantum Development Kit.

Führen Sie den folgenden Befehl innerhalb des Verzeichnisses eines jeweiligen Projekts aus, um ein Update für ein vorhandenes Projekt durchzuführen, damit es die neueste Version nutzt:

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Wenn ein vorhandenes Projekt auch die XUnit-Integration für Komponententests verwenden, kann ein ähnlicher Befehl auch zum Durchführen eines Updates für dieses Paket verwendet werden.
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

Je nachdem, welche Version von XUnit in Ihrem Testprojekt verwendet wird, müssen Sie möglicherweise ein Update auf XUnit 2.3.1 durchführen:
```
dotnet add package xunit -v "2.3.1" 
```

Stellen Sie nach dem Update sicher, dass Sie alle temporären Dateien entfernen, die von der vorherigen Version erstellt wurden, indem Sie folgenden Befehl ausführen:
```
dotnet clean 
```

### <a name="known-issues"></a>Bekannte Probleme

Es sind keine weiteren Probleme bekannt.


## <a name="version-0218022202"></a>Version 0.2.1802.2202

*Veröffentlichungsdatum: 26. Februar 2018*

In diesem Release wurde Unterstützung für die Entwicklung auf mehr Plattformen, die Interoperabilität von Sprachen sowie Leistungsverbesserungen eingeführt. Dies gilt insbesondere in folgenden Fällen:

- Unterstützung für die Entwicklung basierend auf macOS und Linux 
- .NET Core-Kompatibilität, einschließlich plattformübergreifender Unterstützung von Visual Studio Code
- eine vollständige Open-Source-Lizenz für Bibliotheken des Quantum Development Kit
- Verbesserung der Simulatorleistung bei Projekten mit 20 oder mehr Qubits
- Interoperabilität mit der Programmiersprache Python (Preview Release für Windows ist verfügbar)

### <a name="net-editions"></a>.NET-Editionen

Die .NET-Plattform ist in zwei verschiedenen Editionen verfügbar. Das mit Windows bereitgestellte .NET Framework und die Open-Source-Plattform .NET Core, die unter Windows, macOS und Linux verfügbar ist.
In diesem Release werden die meisten Bestandteile des Quantum Development Kit als Bibliotheken für .NET Standard bereitgestellt, was die Klassen umfasst, die .NET Framework und .NET Core gemein haben.
Diese Bibliotheken sind daher mit den aktuellen Versionen von .NET Framework und .NET Core kompatibel.

Damit also sichergestellt werden kann, dass mithilfe des Quantum Development Kit geschriebene Projekte möglichst portabel sind, wird empfohlen, mit dem Quantum Development Kit geschriebene Bibliotheksprojekte für .NET Standard zu schreiben, während Konsolenanwendungen für .NET Core geschrieben werden.
Da die vorherigen Releases des Quantum Development Kit nur .NET Framework unterstützt haben, müssen Sie Ihre vorhandenen Projekte möglicherweise migrieren. Weitere Informationen hierzu finden Sie unten.

### <a name="project-migration"></a>Projektmigration

Projekte, die mit vorherigen Versionen des Quantum Development Kit erstellt wurden, funktionieren weiterhin, solange Sie keine Updates für die enthaltenen NuGet-Pakete durchführen. Führen Sie die folgenden Schritte durch, um vorhandenen Code zur neuen Version zu migrieren:
1. Erstellen Sie ein neues .net Core-Projekt mit dem richtigen Typ der Q# Projektvorlage (Anwendung, Bibliothek oder Test Projekt).
2. Kopieren Sie vorhandene QS- und CS/FS-Dateien aus dem alten Projekt in das neue Projekt (über „Hinzufügen > Vorhandenes Element“). Kopieren Sie nicht die Datei „AssemblyInfo.cs“.
3. Erstellen Sie das Projekt, und führen Sie es aus.

Beachten Sie, dass der Vorgang „RandomWalkPhaseEstimation“ aus dem Namespace „Microsoft.Quantum.Canon“ in den Namespace „Microsoft.Research.Quantum.RandomWalkPhaseEstimation“ im Repository [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc) verschoben wurde.

### <a name="known-issues"></a>Bekannte Probleme

- Die `--filter` Option auf funktioniert `dotnet test` nicht ordnungsgemäß für Tests, die in geschrieben wurden Q# .
  Daher können einzelne Komponententests nicht in Visual Studio Code ausgeführt werden. Es wird empfohlen `dotnet test` , an der Eingabeaufforderung zu verwenden, um alle Tests erneut auszuführen.

## <a name="version-0118011707"></a>Version 0.1.1801.1707

*Veröffentlichungsdatum: 18. Januar 2018*

In diesem Release wurden einige Probleme behoben, die von der Community gemeldet wurden. Die folgenden Probleme wurden behoben:

- Der Simulator funktioniert nun mit altem CPUs, die nicht AVX-fähig sind.
- Regionale Dezimal Einstellungen bewirken nicht, dass der Q# Parser fehlschlägt.
- Der primitive Vorgang `SignD` gibt nun `Int` anstelle von `Double` zurück.


## <a name="version-011712901"></a>Version 0.1.1712.901

*Veröffentlichungsdatum: 11. Dezember 2017*

### <a name="known-issues"></a>Bekannte Probleme

#### <a name="hardware-and-software-requirements"></a>Hardware- und Softwareanforderungen

- Die Ausführung des im Quantum Development Kit enthaltenen Simulators erfordert eine 64-Bit-Installation von Windows.
- Der Quantensimulator von Microsoft, der mit dem Quantum Development Kit installiert wird, nutzt AVX (Advanced Vector Extensions) und erfordert eine AVX-fähige CPU. Im ersten Quartal von 2011 ausgelieferte Intel-Prozessoren („Sandy Bridge“) oder höher unterstützen AVX. Die Unterstützung früherer CPUs wird noch ausgewertet. Weitere Informationen werden möglicherweise noch angekündigt.

#### <a name="project-creation"></a>Projekterstellung

- Beim Erstellen einer Projekt Mappe (. sln), die verwendet Q# , muss die Projekt Mappe ein Verzeichnis sein, das höher als jedes Projekt (. csproj) in der Projekt Mappe ist. Beim Erstellen einer neuen Projektmappe können Sie dies sicherstellen, indem Sie sich vergewissern, dass das Kontrollkästchen „Projektmappenverzeichnis erstellen“ im Dialogfeld „Neues Projekt“ aktiviert ist. Wenn das nicht der Fall ist, müssen die NuGet-Pakete für das Quantum Development Kit manuell installiert werden.

#### Q#

- IntelliSense zeigt keine korrekten Fehler für Q# Code an. Stellen Sie sicher, dass Sie Buildfehler in Visual Studio Fehlerliste anzeigen, um die richtigen Q# Fehler anzuzeigen. Beachten Sie auch, dass Q# Fehler erst angezeigt werden, nachdem Sie einen Build erstellt haben.
- Die Verwendung eines veränderlichen Arrays in einer Teilanwendung kann zu unerwartetem Verhalten führen.
- Die Bindung eines nicht veränderlichen Arrays an ein veränderliches Array (angenommen a = b, wobei „b“ ein veränderliches Array ist) kann zu unerwartetem Verhalten führen.
- Profilerstellung, Code Coverage und andere vs-Plug-Ins können Q# Zeilen und Blöcke nicht immer genau zählen.
- Der Q# Compiler überprüft keine interpoliert-Zeichen folgen. Es ist möglich, c#-Kompilierungsfehler zu erstellen, indem Variablennamen falsch geschrieben oder Ausdrücke in interpoliert Zeichen folgen verwendet werden Q# .

#### <a name="simulation"></a>Simulation

- Der Quantensimulator nutzt OpenMP, um die lineare Algebra zu parallelisieren. OpenMP verwendet standardmäßig alle verfügbaren Hardwarethreads, weshalb Programme mit wenigen Qubits häufig langsam ausgeführt werden, stellt die Koordination die tatsächliche Arbeit in den Schatten. Dies kann behoben werden, indem eine kleine Zahl für die Umgebungsvariable OMP_NUM_THREADS festgelegt wird. Als grobe Faustregel gilt, dass 1 Thread für etwa 4 Qubits genügt und dann für jeden weiteren Qubit ein weiterer Thread benötigt wird. Dies hängt jedoch stark von Ihrem Algorithmus ab.

#### <a name="debugging"></a>Debuggen

- F11 (schrittweise) funktioniert im Q# Code nicht.
- Die Code Hervorhebung im Q# Code an einem Haltepunkt oder einer einstufigen Pause ist manchmal ungenau. Es wird zwar die richtige Zeile hervorgehoben, jedoch werden Anfang und Ende manchmal an den falschen Spalten auf der Zeile hervorgehoben.

#### <a name="testing"></a>Testen

- Tests müssen im 64-Bit-Modus ausgeführt werden. Wenn Ihre Tests mit der Ausnahme „BadImageFormatException“ fehlschlagen, öffnen Sie das Testmenü, und klicken Sie auf „Testeinstellungen“ > Standardmäßige Prozessorarchitektur > X64“.
- Die Ausführung einiger Tests dauert länger (abhängig von Ihrem Computer bis zu 5 Minuten). Das ist normal, da einige mehr als 20 Qubits nutzen. Der größte Test nutzt aktuell 23 Qubits.

#### <a name="samples"></a>Beispiele

- Auf einigen Computern werden kleine Beispiele möglicherweise langsam ausgeführt, es sei denn, für die Umgebungsvariable OMP_NUM_THREADS ist der Wert „1“ festgelegt. Weitere Informationen finden Sie in der Anmerkung unter „Simulation“.

#### <a name="libraries"></a>Bibliotheken

- Es gibt eine implizite Annahme, dass die Qubits, die in verschiedenen Argumenten an einen Vorgang übergeben werden, sich voneinander unterscheiden. Beispielsweise gehen alle Bibliotheksvorgänge (und alle Simulatoren) davon aus, dass zwei Qubits, die an einen gesteuerten Vorgang übergeben werden, KEINE unterschiedlichen Qubits sind. Verstöße gegen diese Annahme können zu unvorhersehbarem und unerwartetem Verhalten führen. Es ist möglich, dies mithilfe des Quantenablaufverfolgungssimulators zu testen.
- Die Funktion „Microsoft.Quantum.Bind“ funktioniert in allen Fällen möglicherweise nicht erwartungsgemäß.
- Im Namespace „Microsoft.Quantum.Extensions.Math“ gibt die SignD-Funktion einen Double-Wert anstelle eines Int-Werts zurück, obwohl die zugrunde liegende Funktion „System.Math.Sign“ immer einen Integer zurückgibt. Das Ergebnis kann mit „1,0“, „-1,0“ und „0,0“ verglichen werden, da für diese Double-Werte exakte Binärdarstellungen vorliegen.
