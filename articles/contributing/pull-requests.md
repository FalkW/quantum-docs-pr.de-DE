---
title: Öffnen von Pull Requests | Microsoft-Dokumentation
description: Öffnen von Pull Requests
author: cgranade
ms.author: chgranad
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.contributing.pulls
ms.openlocfilehash: d70a0a0319d14cfdae4910b897733d77b236f2f9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2019
ms.locfileid: "73183725"
---
# <a name="opening-pull-requests"></a><span data-ttu-id="af582-103">Öffnen von Pull Requests</span><span class="sxs-lookup"><span data-stu-id="af582-103">Opening Pull Requests</span></span> #

<span data-ttu-id="af582-104">Die gesamte Dokumentation für das Quantum Development Kit wird mithilfe des git-Versionskontrollsystems durch die Verwendung mehrerer in GitHub gehosteter Depots verwaltet.</span><span class="sxs-lookup"><span data-stu-id="af582-104">All of the documentation for the Quantum Development Kit is managed using the Git version control system through the use of several repositories hosted on GitHub.</span></span>
<span data-ttu-id="af582-105">Die gemeinsame Verwendung von git und GitHub erleichtert die Zusammenarbeit mit dem Quantum Development Kit.</span><span class="sxs-lookup"><span data-stu-id="af582-105">Using Git and GitHub together makes it easy to collaborate widely on the Quantum Development Kit.</span></span>
<span data-ttu-id="af582-106">Vor allem kann ein git-Repository geklont oder verzweigt werden, um eine vollständig unabhängige Kopie dieses Repository zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="af582-106">In particular, any Git repository can be cloned or forked to make a completely independent copy of that repository.</span></span>
<span data-ttu-id="af582-107">Auf diese Weise können Sie mit den Tools und in einem von Ihnen bevorzugten Tempo an Ihrem Beitrag arbeiten.</span><span class="sxs-lookup"><span data-stu-id="af582-107">This allows you to work on your contribution with the tools and at a pace that you prefer.</span></span>

<span data-ttu-id="af582-108">Wenn Sie bereit sind, können Sie uns eine Anforderung senden, ihren Beitrag in unsere Repos aufzunehmen, indem Sie die _Pull Request_ Funktionen von GitHub verwenden.</span><span class="sxs-lookup"><span data-stu-id="af582-108">When you're ready, you can send us a request to include your contribution into our repos, using GitHub's _pull request_ functionality.</span></span>
<span data-ttu-id="af582-109">Die Seite für die einzelnen Pull Request enthält Details zu allen Änderungen, die ihren Beitrag vornehmen, eine Liste der Kommentare zu Ihrem Beitrag und eine Reihe von Überprüfungs Tools, mit denen andere Mitglieder der Community Feedback und Ratschläge bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="af582-109">The page for each pull request includes details of all the changes that make your contribution, a list of comments on your contribution, and a set of review tools that other members of the community can use to provide feedback and advice.</span></span>

> [!NOTE]
> <span data-ttu-id="af582-110">Während ein vollständiges Tutorial zu git über den Rahmen dieses Handbuchs hinausgeht, können wir die folgenden Links für weitere Ressourcen zum Erlernen von git vorschlagen:</span><span class="sxs-lookup"><span data-stu-id="af582-110">While a full tutorial on Git is beyond the scope of this guide, we can suggest the following links for more resources on learning Git:</span></span>
>
> - <span data-ttu-id="af582-111">[Erlernen von git](https://www.atlassian.com/git): eine Reihe von git-Tutorials von Atlassian.</span><span class="sxs-lookup"><span data-stu-id="af582-111">[Learn Git](https://www.atlassian.com/git): A set of Git tutorials from Atlassian.</span></span>
> - <span data-ttu-id="af582-112">[Versionskontrolle in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): eine Anleitung zur Verwendung Visual Studio Code als GUI für git.</span><span class="sxs-lookup"><span data-stu-id="af582-112">[Version Control in Visual Studio Code](https://code.visualstudio.com/docs/editor/versioncontrol): A guide on how to use Visual Studio Code as a GUI for Git.</span></span>
> - <span data-ttu-id="af582-113">[GitHub-Lernlabor](https://lab.github.com/): eine Reihe von Online Kursen zur Verwendung von git, GitHub und verwandten Technologien.</span><span class="sxs-lookup"><span data-stu-id="af582-113">[GitHub Learning Lab](https://lab.github.com/): A set of online courses for using Git, GitHub, and related technologies.</span></span>
> - <span data-ttu-id="af582-114">[Visualisieren von git](https://git-school.github.io/visualizing-git/): ein interaktives Tool zum Visualisieren der Änderung des Status eines Repository durch git-Befehle.</span><span class="sxs-lookup"><span data-stu-id="af582-114">[Visualizing Git](https://git-school.github.io/visualizing-git/): An interactive tool for visualizing how Git commands change the state of a repository.</span></span>
> - <span data-ttu-id="af582-115">[Versionskontrolle mit git (epqis 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): ein git-Tutorial, das auf wissenschaftliche Berechnungen ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="af582-115">[Version Control with Git (EPQIS 2016)](https://nbviewer.jupyter.org/github/QuinnPhys/PythonWorkshop-science/blob/master/lecture-1-scicomp-tools-part1.ipynb#Version-Control-with-Git-(50-Minutes)): A Git tutorial oriented towards scientific computing.</span></span>
> - <span data-ttu-id="af582-116">[Erlernen von git-Verzweigungen](https://learngitbranching.js.org/): ein interaktiver Satz von Verzweigungen und neustützten rätseln zum Erlernen neuer git-Features.</span><span class="sxs-lookup"><span data-stu-id="af582-116">[Learn Git Branching](https://learngitbranching.js.org/): An interactive set of branching and rebasing puzzles to help learn new Git features.</span></span>

## <a name="what-is-a-pull-request"></a><span data-ttu-id="af582-117">Was ist ein Pull Request?</span><span class="sxs-lookup"><span data-stu-id="af582-117">What is a Pull Request?</span></span> ##

<span data-ttu-id="af582-118">Wenn Sie die oben genannten Punkte erwähnt haben, ist es hilfreich, etwas zu sagen, was ein Pull Request **ist**.</span><span class="sxs-lookup"><span data-stu-id="af582-118">Having said the above, it's helpful to take a few moments to say what a pull request **is**.</span></span>
<span data-ttu-id="af582-119">Beim Arbeiten mit git werden alle Änderungen als _Commits_ dargestellt, die beschreiben, wie diese Änderungen mit dem Zustand des Repository in Beziehung stehen, bevor diese geändert werden.</span><span class="sxs-lookup"><span data-stu-id="af582-119">When working with Git, any changes are represented as _commits_ that describe how those changes are related to the state of the repository before those changes.</span></span>
<span data-ttu-id="af582-120">Wir zeichnen häufig Diagramme, in denen Commits als Kreise mit Pfeilen aus vorherigen Commits gezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="af582-120">We'll often draw diagrams in which commits are drawn as circles with arrows from previous commits.</span></span>

<span data-ttu-id="af582-121">Angenommen, Sie haben einen Beitrag in einer _Verzweigung_ mit dem Namen `feature`gestartet.</span><span class="sxs-lookup"><span data-stu-id="af582-121">Suppose you have started a contribution in a _branch_ called `feature`.</span></span>
<span data-ttu-id="af582-122">Ihre Verzweigung von **Microsoft/Quantum** könnte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="af582-122">Then your fork of **Microsoft/Quantum** might look something like this:</span></span>

![](~/media/git-workflow-step0.png)

<span data-ttu-id="af582-123">Wenn Sie Ihre Änderungen in Ihrem lokalen Repository vornehmen, können Sie Änderungen aus einem anderen Repository per _Pull_ abrufen, um alle Änderungen zu erfassen, die mit upstreamvorgängen durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="af582-123">If you make your changes in your local repository, you can _pull_ changes from another repository into yours to catch up to any changes that happened upstream.</span></span>

![](~/media/git-workflow-step1.png)

<span data-ttu-id="af582-124">Pull Requests funktionieren auf die gleiche Weise, aber in umgekehrter Reihenfolge: Wenn Sie einen Pull Request öffnen, bitten Sie das upstreamrepository, in den Beitrag zu ziehen.</span><span class="sxs-lookup"><span data-stu-id="af582-124">Pull requests work the same way, but in reverse: when you open a pull request, you ask for the upstream repository to pull your contribution in.</span></span>

![](~/media/git-workflow-step2.png)

<span data-ttu-id="af582-125">Wenn Sie eine Pull Request in einem unserer Depots öffnen, bietet GitHub anderen Benutzern in der Community die Möglichkeit, eine Zusammenfassung Ihrer Änderungen anzuzeigen, Sie zu kommentieren und Vorschläge für einen noch besseren Beitrag zu geben.</span><span class="sxs-lookup"><span data-stu-id="af582-125">When you open a pull request to one of our repositories, GitHub will offer an opportunity for others in the community to see a summary of your changes, to comment on them, and to make suggestions for how to help make an even better contribution.</span></span>

![](~/media/pull-request-header.png)

<span data-ttu-id="af582-126">Mithilfe dieses Prozesses können wir die GitHub-Funktionalität nutzen, um Beiträge zu verbessern und ein qualitativ hochwertiges Produkt für die Quantum-Programmier Community zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="af582-126">Using this process helps us use GitHub functionality to improve contributions and to maintain a high-quality product for the quantum programming community.</span></span>

## <a name="how-to-make-a-pull-request"></a><span data-ttu-id="af582-127">So erstellen Sie einen Pull Request</span><span class="sxs-lookup"><span data-stu-id="af582-127">How to Make a Pull Request</span></span> ##

<span data-ttu-id="af582-128">Es gibt zwei Hauptmethoden, um eine Pull Request zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="af582-128">There are two main ways to make a pull request.</span></span>
<span data-ttu-id="af582-129">Bei kleinen Änderungen, die nur eine einzelne Datei betreffen, kann die GitHub-Webschnittstelle verwendet werden, um eine Pull Request vollständig online zu machen.</span><span class="sxs-lookup"><span data-stu-id="af582-129">For small changes that only affect a single file, the GitHub web interface can be used to make a pull request entirely online.</span></span>
<span data-ttu-id="af582-130">Für kompliziertere Beiträge ist es am häufigsten einfacher, Ihren lokalen Computer zu verwenden, um zuerst eine Pull Request vorzubereiten.</span><span class="sxs-lookup"><span data-stu-id="af582-130">For more complicated contributions, it's most often easier to use your local computer to prepare for a pull request first.</span></span>

<!--
### Using the Web Interface ###

**TODO**

### Command-Line and GitHub Flow ###

Most of the time, it's easier to prepare a pull request on your own computer; that makes it easier to work incrementally, and to test your changes.
If you haven't already done so, the first step is to _fork_ the repository that you'd like to contribute to.
Forking makes a complete clone of the original repository, but under your GitHub account instead of under [Microsoft](http://github.com/Microsoft/) or [MicrosoftDocs](http://github.com/MicrosoftDocs/).
This way, you can edit your personal fork to your heart's content before making a pull request for your work.

**TODO: pick up here**

## Code Review and Etiquette ##

**TODO: PR ettiquette, reviews, etc.**

-->

## <a name="next-steps"></a><span data-ttu-id="af582-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="af582-131">Next steps</span></span> ##

<span data-ttu-id="af582-132">Herzlichen Glückwunsch zur Verwendung von git, um die Quantum Development Kit-Community zu unterstützen!</span><span class="sxs-lookup"><span data-stu-id="af582-132">Congratulations on using Git to help out the Quantum Development Kit community!</span></span>
<span data-ttu-id="af582-133">Weitere Informationen zum mitwirken von Code finden Sie im folgenden Handbuch.</span><span class="sxs-lookup"><span data-stu-id="af582-133">To learn more about how to contribute code, please continue with the following guide.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="af582-134">Weitere Informationen zum mitwirken von Code</span><span class="sxs-lookup"><span data-stu-id="af582-134">Learn how to contribute code</span></span>](xref:microsoft.quantum.contributing.code)