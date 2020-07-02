---
title: 'Ausführen des Grover-Suchalgorithmus in Q#: Quantum Development Kit'
description: Erstellen eines Q#-Projekts, das den Grover-Algorithmus veranschaulicht, einen der kanonischen Quantenalgorithmen.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/19/2019
ms.topic: article
uid: microsoft.quantum.quickstarts.search
ms.openlocfilehash: 9e4c53b4d5159cf07f0654603c1d477ad09eb7c6
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274742"
---
# <a name="tutorial-implement-grovers-search-algorithm-in-q"></a>Tutorial: Implementierung des Grover-Suchalgorithmus in Q\#

In diesem Tutorial erfahren Sie, wie Sie eine Grover-Suchabfrage erstellen und ausführen, um die Suche in unstrukturierten Daten zu beschleunigen.  Bei der Grover-Suche handelt es sich um einen der beliebtesten Quantencomputingalgorithmen. Diese relativ kleine Q#-Implementierung vermittelt Ihnen einen Eindruck davon, welche Vorteile die Programmierung von Quantenlösungen mit einer allgemeinen Q#-Quantenprogrammiersprache zum Ausdrücken von Quantenalgorithmen bietet.  Die Simulationsausgabe am Ende der Anleitung zeigt, dass die Suche nach einer bestimmten Zeichenfolge in einer Liste unsortierter Einträge nur einen Bruchteil der Zeit dauert, die für die Durchsuchung der gesamten Liste auf einem klassischen Computer benötigt würde.

Der Grover-Algorithmus durchsucht eine Liste unstrukturierter Daten nach bestimmten Elementen. Er kann beispielsweise diese Frage beantworten: Ist diese Karte, die aus einem Kartenstapel gezogen wurde, ein Herz As? Die Bezeichnung des spezifischen Elements wird als _markierte Eingabe_ bezeichnet.

Bei Verwendung des Grover-Suchalgorithmus besteht Sicherheit, dass ein Quantencomputer diese Suche in weniger Schritten ausführt als die Anzahl der Elemente in der durchsuchten Liste – das kann kein klassischer Algorithmus. Die höhere Geschwindigkeit ist im Fall des Kartenstapels vernachlässigbar. In Listen, die Millionen oder Milliarden Elemente enthalten, wird sie aber wichtig.

Sie können den Grover-Suchalgorithmus mit wenigen Codezeilen erstellen.

## <a name="prerequisites"></a>Voraussetzungen

- Das Microsoft [Quantum Development Kit][install].

## <a name="what-does-grovers-search-algorithm-do"></a>Was macht der Grover-Suchalgorithmus?

Der Grover-Algorithmus fragt, ob ein Element in einer Liste dasjenige ist, nach dem wir suchen. Dazu erstellt er eine Quantenüberlagerung der Indizes der Liste mit jedem Koeffizienten (jeder Wahrscheinlichkeitsamplitude), wodurch die Wahrscheinlichkeit dargestellt wird, dass ein bestimmter Index der gesuchte ist.

Im Kern des Algorithmus befinden sich zwei Schritte, die den Koeffizienten des gesuchten Index inkrementell verstärken, bis die Wahrscheinlichkeitsamplitude des betreffenden Koeffizienten sich eins annähert.

Die Anzahl der inkrementellen Verstärkungen ist kleiner als die Anzahl der Elemente in der Liste. Das ist der Grund, warum der Grover-Suchalgorithmus die Suche in weniger Schritten als jeder klassische Algorithmus durchführen kann.

![Funktionsdiagramm des Grover-Suchalgorithmus](~/media/grover.png)

## <a name="write-the-code"></a>Schreiben des Codes

1. Verwenden Sie das Quantum Development Kit, um ein [neues Q#-Projekt für die Befehlszeilenanwendung zu erstellen](xref:microsoft.quantum.install.standalone). Geben Sie dem Projekt den Namen `Grover`.

1. Fügen Sie den folgenden Code der `Program.qs`-Datei in Ihrem neuen Projekt hinzu:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/SimpleGrover.qs" range="4-41":::

1. Um die Liste zu definieren, die wir durchsuchen, erstellen Sie eine neue Datei `Reflections.qs`, und fügen Sie den folgenden Code ein:

    :::code language="qsharp" source="~/quantum/samples/algorithms/simple-grover/Reflections.qs" range="4-70":::

    Die `ReflectAboutMarked`-Operation definiert die markierte Eingabe, nach der Sie suchen: die Zeichenfolge aus abwechselnden Nullen und Einsen. In diesem Beispiel wird die markierte Eingabe hartcodiert. Sie kann erweitert werden, um nach verschiedenen Eingaben zu suchen, oder generalisiert, um nach beliebigen Eingaben zu suchen.

1. Führen Sie als Nächstes Ihr neues Q#-Programm aus, um das von `ReflectAboutMarked` markierte Element zu finden.

### <a name="q-command-line-applications-with-visual-studio-or-visual-studio-code"></a>Q#-Befehlszeilenanwendungen mit Visual Studio oder Visual Studio Code

Die ausführbare Datei führt den Vorgang oder die Funktion, der bzw. die mit dem Attribut `@EntryPoint()` markiert ist, abhängig von der Projektkonfiguration und den Befehlszeilenoptionen für einen Simulator oder eine Ressourcenschätzung aus.

Drücken Sie in Visual Studio einfach STRG+F5, um das Skript auszuführen.

Erstellen Sie in VS Code erstmalig die Datei `Program.qs`, indem Sie Folgendes im Terminal eingeben:

```Command line
dotnet build
```

Bei nachfolgenden Ausführungen muss diese Datei nicht erneut erstellt werden. Geben Sie für die Ausführung den folgenden Befehl ein, und drücken Sie die EINGABETASTE:

```Command line
dotnet run --no-build
```

Im Terminal sollte die folgende Meldung angezeigt werden:

```
operations.qs:
This operation applies Grover's algorithm to search all possible inputs to an operation to find a particular marked state.
Usage:
operations.qs [options] [command]

--n-qubits <n-qubits> (REQUIRED)
-s, --simulator <simulator>         The name of the simulator to use.
--version                           Show version information
-?, -h, --help                      Show help and usage information
Commands:
```

Das liegt daran, dass Sie die Anzahl der zu verwendenden Qubits nicht angegeben haben. Vom Terminal werden daher die für die ausführbare Datei verfügbaren Befehle ausgegeben. Wenn Sie 5 Qubits verwenden möchten, geben Sie Folgendes ein:

```Command line
dotnet run --n-qubits 5
```

Nach dem Drücken der EINGABETASTE sollte die folgende Ausgabe angezeigt werden:

```
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
Reflecting about marked state...
[Zero,One,Zero,One,Zero]
```

## <a name="next-steps"></a>Nächste Schritte

Wenn Ihnen dieses Tutorial gefallen hat, sehen Sie sich einige der unten aufgeführten Ressourcen an, um mehr darüber zu erfahren, wie Sie Q# verwenden können, um eigene Quantenanwendungen zu schreiben:

- [Zurück zum Leitfaden mit den ersten Schritte mit dem QDK](xref:microsoft.quantum.welcome)
- Ausprobieren eines [Beispiels](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/database-search) für einen allgemeineren Grover-Suchalgorithmus
- [Weitere Informationen zur Grover-Suche mit den Quanten-Katas](xref:microsoft.quantum.overview.katas)
- Informieren Sie sich ausführlicher über die [Amplitudenverstärkung][amplitude-amplification], die Quantencomputingtechnik hinter dem Suchalgorithmus von Grover.
- [Quantencomputingkonzepte](xref:microsoft.quantum.concepts.intro)
- [Quantum Development Kit-Beispiele](https://docs.microsoft.com/samples/browse/?products=qdk)

<!-- LINKS -->

[install]: xref:microsoft.quantum.install
[amplitude-amplification]: xref:microsoft.quantum.libraries.standard.algorithms#amplitude-amplification