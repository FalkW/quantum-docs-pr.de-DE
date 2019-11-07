---
title: Was können Quantencomputer?
description: Erfahren Sie mehr über die Macht von Quantencomputern, von neuartigen Quantenalgorithmen bis zu von Quanten inspirierten Algorithmen, die auf klassischen Computern ausgeführt werden.
author: natke
ms.author: nakersha
ms.date: 10/23/2019
ms.topic: article
uid: microsoft.quantum.overview.computers
ms.openlocfilehash: 9d8ba90a504f298f9465ebf564c43625a4d43168
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529950"
---
# <a name="what-can-a-quantum-computer-do"></a><span data-ttu-id="93c6e-103">Was kann ein Quantencomputer?</span><span class="sxs-lookup"><span data-stu-id="93c6e-103">What can a quantum computer do?</span></span>

<span data-ttu-id="93c6e-104">Was können wir mit einem Quantencomputer tun, das sich mit einem klassischen Computer nicht erledigen lässt?</span><span class="sxs-lookup"><span data-stu-id="93c6e-104">What can we do with a quantum computer that can't be done with a classical one?</span></span>

<span data-ttu-id="93c6e-105">Die Lösung einiger der schwierigsten Probleme der Welt, zu der aktuelle Computer Milliarden Jahre Rechenzeit benötigen, könnte von einem Quantencomputer in Tagen, Stunden oder sogar Minuten erledigt werden.</span><span class="sxs-lookup"><span data-stu-id="93c6e-105">To solve some of the world's most challenging problems, where finding a solution would take current computers billions of years, a quantum computer could do so in days, hours, or even minutes.</span></span>

<span data-ttu-id="93c6e-106">Quantencomputer werden es Forschern ermöglichen, neue Katalysatoren und Materialien zu entwickeln, Medikamente zu verbessern, den Fortschritt in der künstlichen Intelligenz zu beschleunigen und grundlegende Fragen zum Ursprung des Universums zu beantworten.</span><span class="sxs-lookup"><span data-stu-id="93c6e-106">Quantum computing will enable researchers to develop new catalysts and materials, improve medicines, accelerate advances in artificial intelligence, and answer fundamental questions about the origins of our universe.</span></span>

## <a name="quantum-simulation"></a><span data-ttu-id="93c6e-107">Quantensimulation</span><span class="sxs-lookup"><span data-stu-id="93c6e-107">Quantum simulation</span></span>

<span data-ttu-id="93c6e-108">Die Nutzung von Quantenprogrammen zum Modellieren der eigentlichen Quantensysteme hat das Potenzial, zu umfassenden Erkenntnissen zu führen, die Innovationen in vielen Branchen nach sich ziehen können.</span><span class="sxs-lookup"><span data-stu-id="93c6e-108">Using quantum programs to model quantum systems themselves has vast potential for unlocking insights leading to innovations across many industries.</span></span> <span data-ttu-id="93c6e-109">Photosynthese, Supraleiter und komplexe Moleküle sind Beispiele für Quantensysteme, die mithilfe von Quantenprogrammen simuliert werden können.</span><span class="sxs-lookup"><span data-stu-id="93c6e-109">Photosynthesis, superconductors, and complex molecules are examples of quantum systems that can be simulated using quantum programs.</span></span>

<span data-ttu-id="93c6e-110">Das Simulieren von mikroskopisch kleinen Systemen, die sich nach den Gesetzen der Quantenmechanik verhalten, bringt hohen Berechnungsaufwand mit sich.</span><span class="sxs-lookup"><span data-stu-id="93c6e-110">Simulating microscopic systems that behave according to the laws of quantum mechanics is computationally expensive.</span></span> <span data-ttu-id="93c6e-111">Wir müssen alle möglichen Zustände berücksichtigen, die sich überlagern können, und die Anzahl der Zustände wächst exponentiell mit der Größe des Systems.</span><span class="sxs-lookup"><span data-stu-id="93c6e-111">We need to take into account all the possible states that can be in superposition and the number of states grows exponentially with the size of the system.</span></span> <span data-ttu-id="93c6e-112">Auf einem Quantencomputer brauchen wir gar nicht alle Zustände des Systems zu modellieren.</span><span class="sxs-lookup"><span data-stu-id="93c6e-112">In a quantum computer, we don’t need to model all of the states of the system.</span></span> <span data-ttu-id="93c6e-113">Stattdessen betten wir den Quantenzustand des Systems, das wir modellieren möchten, in die Qubits des Computers selbst ein, und führen die Simulation mit einer bestimmten Menge an Quantengattern aus.</span><span class="sxs-lookup"><span data-stu-id="93c6e-113">Instead, we embed the quantum state of the system that we want to simulate in the qubits of the computer itself, and run the simulation with a specific set of quantum gates.</span></span> <span data-ttu-id="93c6e-114">Anders ausgedrückt: Wir verwenden einen Quantencomputer, um ein Quantensystem zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="93c6e-114">In other words, we use a quantum computer to simulate a quantum system.</span></span>

<span data-ttu-id="93c6e-115">Chemische Moleküle sind Quantensysteme und können daher auf diese Weise analysiert werden.</span><span class="sxs-lookup"><span data-stu-id="93c6e-115">Chemical molecules are quantum systems and therefore can be analyzed in this way.</span></span> <span data-ttu-id="93c6e-116">Eine solche spezifische chemische Verbindung ist das Enzym _Nitrogenase_, das möglicherweise das Potenzial besitzt, Energieverbrauch und Treibhausgasemissionen aktueller Dünger zu reduzieren – vorausgesetzt, wir verstehen seine Eigenschaften besser.</span><span class="sxs-lookup"><span data-stu-id="93c6e-116">One such specific chemical is the _nitrogenase_ enzyme, which, with a better understanding of its properties, could have the potential to reduce the energy consumption and greenhouse gas emission of current fertilizers.</span></span>

## <a name="cryptography"></a><span data-ttu-id="93c6e-117">Kryptografie</span><span class="sxs-lookup"><span data-stu-id="93c6e-117">Cryptography</span></span>

<span data-ttu-id="93c6e-118">Der vielleicht bekannteste Anwendungsbereich von Quantencomputern ist die Kryptografie. Peter Shor hat 1994 gezeigt, dass mit einem skalierbaren Quantencomputer alle gängigen Verschlüsselungsverfahren geknackt werden können.</span><span class="sxs-lookup"><span data-stu-id="93c6e-118">Perhaps the most famous application of quantum computers is in cryptography, where Peter Shor showed in 1994 that a scalable quantum computer can break every widely used encryption technique.</span></span>  <span data-ttu-id="93c6e-119">Die klassische Kryptografie basiert auf der „Widerspenstigkeit“ von Vorgängen mit hohen Zahlen, z. B. der Faktorisierung großer Zahlen in zwei Primzahlen.</span><span class="sxs-lookup"><span data-stu-id="93c6e-119">Classical cryptography relies on the intractability of operations on large numbers, such as factorization of large numbers into two prime numbers.</span></span>

<span data-ttu-id="93c6e-120">Quantencomputer machen diese Vorgänge theoretisch lenkbar (per Shor-Algorithmus).</span><span class="sxs-lookup"><span data-stu-id="93c6e-120">Quantum computing makes these operations theoretically tractable (via Shor's algorithm).</span></span> <span data-ttu-id="93c6e-121">Zwar ist die Implementierung dieses Algorithmus beim aktuellen Maßstab von Quantenhardware physisch nicht möglich, er hat aber die Entwicklung quantenresistenter Algorithmen in Gang gebracht, um Datensicherheit zukunftssicher zu gestalten, einschließlich neuartiger Quantenalgorithmen für die Verschlüsselung und die Verteilung von Kryptografieschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="93c6e-121">Whilst implementation of this algorithm is not physically possible with the current scale of quantum hardware, it has spawned development of quantum-resistant algorithms to future-proof data security, including novel quantum algorithms for encryption and cryptographic key distribution.</span></span>

<span data-ttu-id="93c6e-122">Bei Microsoft verfügen wir über das weltweit führende Team im Bereich Post-Quantenkryptografie und -sicherheit, das an der Entwicklung von quantenresistenten Algorithmen arbeitet.</span><span class="sxs-lookup"><span data-stu-id="93c6e-122">Here at Microsoft, we have the world's leading team in post-quantum cryptography and security developing quantum-resistant algorithms.</span></span>

## <a name="optimization"></a><span data-ttu-id="93c6e-123">Optimierung</span><span class="sxs-lookup"><span data-stu-id="93c6e-123">Optimization</span></span>

<span data-ttu-id="93c6e-124">Bei der Optimierung geht es darum, eine umfangreiche Suche in einem hochdimensionalen Bereich zur Erzielung einer Lösung durchzuführen, mit der eine bestimmte Kostenfunktion minimiert wird.</span><span class="sxs-lookup"><span data-stu-id="93c6e-124">Optimization is the task of performing a large search over a high-dimensional space for a solution that minimizes a given cost function.</span></span>   <span data-ttu-id="93c6e-125">Auf einem Quantencomputer können wir Optimierungsalgorithmen beschleunigen, um Lösungen zu finden, die auf andere Weise nicht möglich wären.</span><span class="sxs-lookup"><span data-stu-id="93c6e-125">On a quantum computer, we can speed up optimization algorithms, enabling finding solutions that otherwise were not possible.</span></span> <span data-ttu-id="93c6e-126">Beispiele für Anwendungsbereiche sind Transport/Logistik, Gesundheitswesen, Diagnostik und Materialwissenschaft.</span><span class="sxs-lookup"><span data-stu-id="93c6e-126">Applications range from transportation and logistics, healthcare, diagnostics, and material science.</span></span> <span data-ttu-id="93c6e-127">Dies kann erhebliche Auswirkungen auf die Effizienz der Branche haben.</span><span class="sxs-lookup"><span data-stu-id="93c6e-127">There can be a profound impact on how these industries can become more efficient.</span></span>

<span data-ttu-id="93c6e-128">Die Optimierung per Quantencomputing ermöglicht uns Innovationen im Bereich Transport/Logistik, die mit den heutigen klassischen Systemen nicht möglich sind.</span><span class="sxs-lookup"><span data-stu-id="93c6e-128">Optimization with quantum computing allows us to innovate around transportation and logistics in a way that is not possible with today’s classical systems.</span></span>

<span data-ttu-id="93c6e-129">Per Optimierung des Datenverkehrsflusses können Staus reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="93c6e-129">Optimizing traffic flow can reduce congestion.</span></span>  <span data-ttu-id="93c6e-130">Weitere Bereiche neben der Routenplanung sind die Gatezuweisung für den Luftverkehr, die Paketzustellung, die Auftragsplanung und mehr.</span><span class="sxs-lookup"><span data-stu-id="93c6e-130">In addition to route planning, there is airplane gate assignment, package delivery, job scheduling and more.</span></span> <span data-ttu-id="93c6e-131">Wenn in der Materialwirtschaft weitere Durchbrüche erzielt werden, entstehen neue Energieformen, Akkus mit höherer Kapazität und leichtere, besser haltbare Materialien.</span><span class="sxs-lookup"><span data-stu-id="93c6e-131">With breakthroughs in materials science, there will be new forms of energy, batteries with greater capacity, lighter and stronger materials.</span></span>

## <a name="machine-learning"></a><span data-ttu-id="93c6e-132">Machine Learning</span><span class="sxs-lookup"><span data-stu-id="93c6e-132">Machine learning</span></span>

<span data-ttu-id="93c6e-133">Ein großer Teil der numerischen Berechnungen auf klassischen Computern besteht im Lösen linearer Gleichungssysteme. Dies gilt insbesondere für maschinelles Lernen, bei dem der größte Teil des Rechenaufwands in die Berechnung der Umkehrung riesiger Matrizen fließt.</span><span class="sxs-lookup"><span data-stu-id="93c6e-133">A great number of numerical calculations on classical computing consist mainly in solving linear systems of equations, especially true in the field of machine learning where most of the computation cost goes into calculating the inverse of huge matrices.</span></span>

<span data-ttu-id="93c6e-134">Glücklicherweise gibt es einen Quantenalgorithmus, der es uns ermöglicht, das System exponentiell schneller als mit einem klassischen Computer zu lösen.</span><span class="sxs-lookup"><span data-stu-id="93c6e-134">Fortunately, there is a quantum algorithm that allows us to approximately solve the system exponentially faster than a classical computer.</span></span> <span data-ttu-id="93c6e-135">Dies ebnet den Weg für die hohe Beschleunigung bei jedem Problem, für das die Lösung linearer Gleichungssysteme erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="93c6e-135">The algorithm opens the door to great speedups in every problem that needs the solution to linear systems of equations.</span></span>

<span data-ttu-id="93c6e-136">Lösungen von Problemen in diesen Bereichen sind hilfreich für die Energiekrise, den Klimawandel, die Nahrungsmittelknappheit und persönliche und präzise medizinische Diagnosen.</span><span class="sxs-lookup"><span data-stu-id="93c6e-136">Solutions to problems in these areas will help address the energy crisis, climate change, food scarcity, and personal and precise medical diagnosis.</span></span>

## <a name="quantum-inspired-computing"></a><span data-ttu-id="93c6e-137">Von Quanten inspiriertes Computing</span><span class="sxs-lookup"><span data-stu-id="93c6e-137">Quantum-inspired computing</span></span>

<span data-ttu-id="93c6e-138">Von Quanten inspirierte Algorithmen werden mit klassischer Software implementiert, verwenden aber Quantenprinzipien, um höhere Geschwindigkeit und Genauigkeit zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="93c6e-138">Quantum-inspired algorithms are implemented with classical software, but use quantum principles for increased speed and accuracy.</span></span>

<span data-ttu-id="93c6e-139">Von Quanten inspirierte Algorithmen werden in der medizinischen Forschung angewendet.</span><span class="sxs-lookup"><span data-stu-id="93c6e-139">Quantum-inspired algorithms are being applied to medical research.</span></span> <span data-ttu-id="93c6e-140">Beispielsweise, um die Genauigkeit von MRI-Scans (Magnetic Resonance Imaging, Magnetresonanztomografie) zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="93c6e-140">For example, to improve the accuracy of Magnetic Resonance Imaging (MRI) scans.</span></span> <span data-ttu-id="93c6e-141">Das von Quanten inspirierte Computing wird verwendet, um die Konfiguration der MRI-Computer zur Erkennung bestimmter Krankheiten zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="93c6e-141">Quantum-inspired computing is being used to optimize the configuration of the MRI machines for identification of specific diseases.</span></span>

## <a name="next-steps"></a><span data-ttu-id="93c6e-142">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="93c6e-142">Next steps</span></span>

* [<span data-ttu-id="93c6e-143">Warum sollte ich Quantencomputing erlernen?</span><span class="sxs-lookup"><span data-stu-id="93c6e-143">Why should I learn quantum computing?</span></span>](xref:microsoft.quantum.overview.why)
* [<span data-ttu-id="93c6e-144">Einstieg in das Microsoft Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="93c6e-144">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)