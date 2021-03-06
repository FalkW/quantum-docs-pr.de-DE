---
title: Entwickeln mit Q#-Jupyter Notebook-Instanzen
description: Hier erfahren Sie, wie Sie mithilfe von Jupyter Notebook-Instanzen eine Anwendung vom Typ Q# erstellen.
author: bradben
ms.author: v-benbra
ms.date: 8/20/2020
ms.topic: quickstart
uid: microsoft.quantum.install.jupyter
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4cef9b7252a2199b2ea995c4cf819a3582d9ca8f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844292"
---
# <a name="develop-with-q-jupyter-notebooks"></a>Entwickeln mit Q#-Jupyter Notebook-Instanzen

Installieren Sie das QDK für die Entwicklung von Q#-Vorgängen in Q#-Jupyter Notebook-Instanzen.

Jupyter Notebooks ermöglichen die direkte Codeausführung parallel zu Anweisungen, Notizen und anderem Inhalt. Diese Umgebung ist ideal für die Erstellung von Q#-Code mit eingebetteten Erläuterungen oder interaktiven Tutorials zum Quantencomputing. Hier erfahren Sie, welche Schritte zum Erstellen eigener Q#-Notebooks erforderlich sind.

## <a name="install-the-iq-jupyter-kernel"></a>Installieren des IQ#-Jupyter-Kernels

IQ# (ausgesprochen „i-q-sharp“) ist eine hauptsächlich von Jupyter und Python genutzte Erweiterung für das .NET Core SDK, die die Kernfunktionen für das Kompilieren und Simulieren von Q#-Vorgängen bereitstellt.

### <a name="install-using-conda-recommended"></a>[Installation mithilfe von Conda (empfohlen)](#tab/tabid-conda)

1. Installieren Sie [Miniconda](https://docs.conda.io/en/latest/miniconda.html) oder [Anaconda](https://www.anaconda.com/products/individual#Downloads). **Hinweis:** Eine 64-Bit-Installation ist erforderlich.

1. Öffnen Sie eine Anaconda-Eingabeaufforderung.

   - Wenn Sie PowerShell oder pwsh verwenden möchten: Öffnen Sie eine Shell, führen Sie `conda init powershell`aus, schließen Sie die Shell, und öffnen Sie sie erneut.

1. Erstellen und aktivieren Sie eine neue Conda-Umgebung namens `qsharp-env` mit den erforderlichen Paketen (einschließlich Jupyter Notebook und IQ#). Führen Sie dazu die folgenden Befehle aus:

    ```
    conda create -n qsharp-env -c quantum-engineering qsharp notebook

    conda activate qsharp-env
    ```

1. Führen Sie `python -c "import qsharp"` über das gleiche Terminal aus, um die Installation zu überprüfen und den lokalen Paketcache mit allen erforderlichen QDK-Komponenten aufzufüllen.

### <a name="install-using-net-cli-advanced"></a>[Installieren mithilfe der .NET-CLI (erweitert)](#tab/tabid-dotnetcli)

1. Voraussetzungen:

    - [Python](https://www.python.org/downloads/) 3.6 oder höher
    - [Jupyter Notebook](https://jupyter.readthedocs.io/en/latest/install.html)
    - [.NET Core SDK 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)

1. Installieren Sie das `Microsoft.Quantum.IQSharp`-Paket.

    ```dotnetcli
    dotnet tool install -g Microsoft.Quantum.IQSharp
    dotnet iqsharp install
    ```

> [!NOTE]
> Wenn Sie während des Schritts `dotnet iqsharp install` einen Fehler erhalten, sollten Sie ein neues Terminalfenster öffnen und den Vorgang dann wiederholen.
> Falls der Vorgang immer noch nicht erfolgreich ist, sollten Sie mit dem installierten Tool `dotnet-iqsharp` (unter Windows `dotnet-iqsharp.exe`) Folgendes ausführen:
> ```
> /path/to/dotnet-iqsharp install --user --path-to-tool="/path/to/dotnet-iqsharp"
> ```
> Ersetzen Sie hierbei `/path/to/dotnet-iqsharp` durch den absoluten Pfad zum Tool `dotnet-iqsharp` in Ihrem Dateisystem.
> Normalerweise finden Sie dies unter `.dotnet/tools` in Ihrem Benutzerprofilordner.
    
**_

Das ist alles! Sie verfügen nun über den IQ#-Kernel für Jupyter, der die Kernfunktionen zum Kompilieren und Ausführen von Q#-Vorgängen in Jupyter Notebook-Instanzen vom Typ Q# bereitstellt.

## <a name="create-your-first-q-notebook"></a>Erstellen Ihres ersten Q#-Notebooks

Nun können Sie Ihre Q#-Jupyter Notebook-Installation überprüfen, indem Sie einen einfachen Q#-Vorgang schreiben und ausführen.

1. Führen Sie in der bei der Installation erstellten Umgebung (d. h. entweder in der von Ihnen erstellten Conda-Umgebung oder in der Python-Umgebung, in der Sie Jupyter installiert haben) den folgenden Befehl aus, um den Jupyter Notebook-Server zu starten:

    ```
    jupyter notebook
    ```

    - Wenn Jupyter Notebook nicht automatisch in Ihrem Browser geöffnet wird, kopieren Sie die URL aus der Befehlszeile in den Browser.

1. Wählen Sie _ *Neu > Q#* * aus, um eine Jupyter Notebook-Instanz mit einem Q#-Kernel zu erstellen, und fügen Sie in der ersten Notebookzelle den folgenden Code hinzu:

    :::code language="qsharp" source="~/quantum/samples/interoperability/qrng/Qrng.qs" range="6-13":::

1. Führen Sie diese Zelle des Notebooks aus:

    ![Jupyter Notebook-Zelle mit Q#-Code](~/media/install-guide-jupyter.png)

    In der Ausgabe der Zelle sollte `SampleQuantumRandomNumberGenerator` angezeigt werden. Bei der Ausführung in Jupyter Notebook wird der Q#-Code kompiliert, und die Zelle gibt den Namen der gefundenen Vorgänge aus.

1. Führen Sie in einer neuen Zelle den soeben erstellten Vorgang aus (in einem Simulator), indem Sie den Befehl `%simulate` verwenden:

    ![Jupyter Notebook-Zelle mit %simulate-Magic-Befehl](~/media/install-guide-jupyter-simulate.png)

    Das Ergebnis des von Ihnen aufgerufenen Vorgangs sollte angezeigt werden. Da in diesem Fall ein zufälliges Ergebnis durch den Vorgang generiert wird, wird entweder `Zero` oder `One` auf dem Bildschirm angezeigt. Wenn Sie die Zelle wiederholt ausführen, sollte jedes Ergebnis ungefähr die Hälfte der Zeit angezeigt werden.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie das QDK für Q#-Jupyter Notebook-Instanzen nun installiert haben, können Sie [Ihr erstes Quantenprogramm](xref:microsoft.quantum.quickstarts.qrng) schreiben und ausführen. Schreiben Sie dazu Q#-Code direkt in der Jupyter Notebook-Umgebung.

Weitere Beispiele für die Verwendung von Q#-Jupyter Notebook-Instanzen finden Sie hier:

- [Einführung in Q# und Jupyter Notebook.](https://docs.microsoft.com/samples/microsoft/quantum/intro-to-qsharp-jupyter/) Enthält eine Q#-Jupyter Notebook-Instanz mit weiteren Details zur Verwendung von Q# in der Jupyter-Umgebung.
- [Quanten-Katas](xref:microsoft.quantum.overview.katas), eine Open-Source-Sammlung mit eigenverantwortlich zu absolvierenden Tutorials und Programmierübungen in Form von Q#-Jupyter Notebook-Instanzen. Die [Tutorial-Notebooks der Quanten-Katas](https://github.com/microsoft/QuantumKatas#tutorial-topics) sind ein guter Ausgangspunkt. Die Quanten-Katas sind so ausgelegt, dass Ihnen gleichzeitig Elemente des Quantencomputings und der Q#-Programmierung vermittelt werden. Sie sind ein hervorragendes Beispiel dafür, welche Arten von Inhalt Sie mit Q#-Jupyter Notebook-Instanzen erstellen können.
