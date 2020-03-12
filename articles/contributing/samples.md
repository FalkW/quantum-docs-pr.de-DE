---
title: Mitwirken von Beispielen an das Microsoft QDK
description: Erfahren Sie, wie Sie Beispielcode zum Microsoft Quantum Development Kit (QDK) beitragen.
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.samples
ms.openlocfilehash: 3bd0de04a448c74eea6c3e8e3a15dcbb19f9d705
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2020
ms.locfileid: "79024150"
---
# <a name="contributing-samples-to-the-quantum-development-kit"></a><span data-ttu-id="cd9a4-103">Mitwirken von Beispielen für das Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="cd9a4-103">Contributing Samples to the Quantum Development Kit</span></span>

<span data-ttu-id="cd9a4-104">Wenn Sie an dem [beispielrepository](https://github.com/Microsoft/Quantum)Code mitwirken möchten, vielen Dank, dass Sie die Quantum Development Community besser platzieren!</span><span class="sxs-lookup"><span data-stu-id="cd9a4-104">If you're interested in contributing code to the [samples repository](https://github.com/Microsoft/Quantum), thank you for making the quantum development community a better place!</span></span>

## <a name="the-quantum-development-kit-samples-repository"></a><span data-ttu-id="cd9a4-105">Das Quantum Development Kit-beispielrepository</span><span class="sxs-lookup"><span data-stu-id="cd9a4-105">The Quantum Development Kit Samples Repository</span></span>

<span data-ttu-id="cd9a4-106">Um Ihnen bei der Vorbereitung Ihres Beitrags zu helfen, so weit wie möglich zu helfen, ist es hilfreich, sich einen kurzen Blick darauf zu verschaffen, wie das beispielrepository angelegt wird:</span><span class="sxs-lookup"><span data-stu-id="cd9a4-106">To help you prepare your contribution to help out as much as possible, it's helpful to take a quick look at how the samples repository is laid out:</span></span>

```plaintext
microsoft/Quantum
📁 samples/
  📁 algorithms/
    📁 chsh-game/
      📝 CHSHGame.csproj
      📝 Game.qs
      📝 Host.cs
      📝 host.py
      📝 README.md
     ⋮
  📁 arithmetic/
  📁 characterization/
  📁 chemistry/
   ⋮
```

<span data-ttu-id="cd9a4-107">Das heißt, die Beispiele im [Microsoft/quantum-Repository](https://github.com/microsoft/Quantum) werden nach Themenbereich in verschiedene Ordner aufgeteilt, wie z. b. `algorithms/`, `arithmetic/`oder `characterization/`.</span><span class="sxs-lookup"><span data-stu-id="cd9a4-107">That is, the samples in the [microsoft/Quantum repository](https://github.com/microsoft/Quantum) are broken down by subject area into different folders such as `algorithms/`, `arithmetic/`, or `characterization/`.</span></span>
<span data-ttu-id="cd9a4-108">Innerhalb des Ordners für jeden Themenbereich besteht jedes Beispiel aus einem einzelnen Ordner, der alle Elemente sammelt, die ein Benutzer zum Durchsuchen und verwenden dieses Beispiels benötigt.</span><span class="sxs-lookup"><span data-stu-id="cd9a4-108">Within the folder for each subject area, each sample consists of a single folder that collects everything a user will need to explore and make use of that sample.</span></span>

## <a name="how-samples-are-structured"></a><span data-ttu-id="cd9a4-109">Strukturieren von Beispielen</span><span class="sxs-lookup"><span data-stu-id="cd9a4-109">How Samples are Structured</span></span>

<span data-ttu-id="cd9a4-110">Sehen wir uns die Dateien an, aus denen sich die einzelnen Ordner bilden, betrachten wir das [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="cd9a4-110">Looking at the files that make up each folder, let's dive into the [`algorithms/chsh-game/`](https://github.com/microsoft/Quantum/tree/master/samples/algorithms/chsh-game) sample.</span></span>

| <span data-ttu-id="cd9a4-111">Datei</span><span class="sxs-lookup"><span data-stu-id="cd9a4-111">File</span></span>              | <span data-ttu-id="cd9a4-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="cd9a4-112">Description</span></span>                                                |
|-------------------|------------------------------------------------------------|
| `CHSHGame.csproj` | <span data-ttu-id="cd9a4-113">Q #-Projekt, das zum Erstellen des Beispiels mit dem .net Core SDK verwendet wird</span><span class="sxs-lookup"><span data-stu-id="cd9a4-113">Q# project used to build the sample with the .NET Core SDK</span></span> |
| `Game.qs`         | <span data-ttu-id="cd9a4-114">F #-Vorgänge und-Funktionen für das Beispiel</span><span class="sxs-lookup"><span data-stu-id="cd9a4-114">Q# operations and functions for the sample</span></span>                 |
| `Host.cs`         | <span data-ttu-id="cd9a4-115">C#zum Ausführen des Beispiels verwendetes Host Programm</span><span class="sxs-lookup"><span data-stu-id="cd9a4-115">C# host program used to run the sample</span></span>                     |
| `host.py`         | <span data-ttu-id="cd9a4-116">Zum Ausführen des Beispiels verwendetes python-Host Programm</span><span class="sxs-lookup"><span data-stu-id="cd9a4-116">Python host program used to run the sample</span></span>                 |
| `README.md`       | <span data-ttu-id="cd9a4-117">Dokumentation zur Funktionsweise des Beispiels und zur Verwendung</span><span class="sxs-lookup"><span data-stu-id="cd9a4-117">Documentation on what the sample does and how to use it</span></span>    |

<span data-ttu-id="cd9a4-118">Nicht alle Samples haben genau denselben Satz von Dateien (z. b. können einige Beispiele vorhanden sein C#, andere verfügen möglicherweise nicht über einen python-Host, oder einige Beispiele erfordern möglicherweise, dass die Datendateien für die Daten ordnungsgemäß funktionieren).</span><span class="sxs-lookup"><span data-stu-id="cd9a4-118">Not all samples will have the exact same set of files (e.g.: some samples may be C#-only, others may not have a Python host, or some samples may require auxillary data files to work).</span></span>

## <a name="anatomy-of-a-helpful-readme-file"></a><span data-ttu-id="cd9a4-119">Anatomie einer hilfreichen Infodatei</span><span class="sxs-lookup"><span data-stu-id="cd9a4-119">Anatomy of a Helpful README File</span></span>

<span data-ttu-id="cd9a4-120">Eine besonders wichtige Datei ist jedoch die `README.md`-Datei, da die Benutzer für den Einstieg in Ihr Beispiel benötigen.</span><span class="sxs-lookup"><span data-stu-id="cd9a4-120">One especially important file, though, is the `README.md` file, as that's what users need to get started with your sample!</span></span>

<span data-ttu-id="cd9a4-121">Jede `README.md` sollte mit einigen Metadaten beginnen, mit deren Hilfe docs.Microsoft.com/Samples ihren Beitrag finden kann.</span><span class="sxs-lookup"><span data-stu-id="cd9a4-121">Each `README.md` should start with some metadata that helps docs.microsoft.com/samples find your contribution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="cd9a4-122">Sehen Sie sich an, wie das Beispiel für das CHSH-Spiel</span><span class="sxs-lookup"><span data-stu-id="cd9a4-122">See how the chsh-game sample is rendered</span></span>](https://docs.microsoft.com/samples/microsoft/quantum/validating-quantum-mechanics/)

<span data-ttu-id="cd9a4-123">Diese Metadaten werden als [YAML-Header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) bereitgestellt, der angibt, welche Sprachen Ihr Beispiel abdeckt (in der Regel `qsharp`, `csharp`und `python`) und welche Produkte in Ihrem Beispiel behandelt werden (in der Regel nur `qdk`).</span><span class="sxs-lookup"><span data-stu-id="cd9a4-123">This metadata is provided as a [YAML header](https://dotnet.github.io/docfx/spec/docfx_flavored_markdown.html#yaml-header) that indicates what languages your sample covers (typically, this will be `qsharp`, `csharp`, and `python`), and what products your sample covers (typically, just `qdk`).</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="1-11":::

> [!IMPORTANT]
> <span data-ttu-id="cd9a4-124">Der `page_type: sample`-Schlüssel im-Header ist erforderlich, damit das Beispiel unter docs.Microsoft.com/Samples angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cd9a4-124">The `page_type: sample` key in the header is required for your sample to appear at docs.microsoft.com/samples.</span></span>
> <span data-ttu-id="cd9a4-125">Ebenso sind die `product`-und `language` Schlüssel wichtig, um Benutzern zu helfen, das Beispiel zu finden und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cd9a4-125">Similarly, the `product` and `language` keys are critical for helping users to find and run your sample.</span></span>

<span data-ttu-id="cd9a4-126">Danach ist es hilfreich, eine kurze Einführung zu erhalten, in der das neue Beispiel angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="cd9a4-126">After that, it's helpful to give a short intro that says what your new sample does:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="13-21":::

<span data-ttu-id="cd9a4-127">Benutzer Ihres Beispiels können auch wissen, was Sie benötigen, um es auszuführen (z. b. benötigen Benutzer nur das Quantum Development Kit selbst oder benötigen zusätzliche Software, wie z. b. Node. js?):</span><span class="sxs-lookup"><span data-stu-id="cd9a4-127">Users of your sample will also appreciate knowing what they need to run it (e.g.: do users just need the Quantum Development Kit itself, or do they need additional software such as node.js?):</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="23-25":::

<span data-ttu-id="cd9a4-128">Damit können Sie die Benutzer darüber informieren, wie das Beispiel ausgeführt werden soll:</span><span class="sxs-lookup"><span data-stu-id="cd9a4-128">With all that in place, you can tell users how to run your sample:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="27-50":::

<span data-ttu-id="cd9a4-129">Schließlich ist es hilfreich, Benutzern mitzuteilen, was jede Datei in Ihrem Beispiel tut und wo Sie weitere Informationen erhalten können:</span><span class="sxs-lookup"><span data-stu-id="cd9a4-129">Finally, it's helpful to tell users what each file in your sample does, and where they can go for more information:</span></span>

:::code language="markdown" source="~/quantum/samples/algorithms/chsh-game/README.md" range="52-61":::

> [!WARNING]
> <span data-ttu-id="cd9a4-130">Stellen Sie sicher, dass Sie hier absolute URLs verwenden, da das Beispiel unter einer anderen URL angezeigt wird, wenn es unter docs.Microsoft.com/Samples gerendert wird.</span><span class="sxs-lookup"><span data-stu-id="cd9a4-130">Make sure to use absolute URLs here, since your sample will appear at a different URL when rendered at docs.microsoft.com/samples!</span></span>
