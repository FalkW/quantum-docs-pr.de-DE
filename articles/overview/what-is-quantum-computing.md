---
title: Was ist Quantencomputing?
description: Erfahren Sie, was Quantencomputing ist und was ein Quantencomputer kann.
author: natke
ms.author: nakersha
ms.date: 10/22/2019
ms.topic: article
uid: microsoft.quantum.overview.what
ms.openlocfilehash: 2f3b64b00a0a9552e52e34cb1e3652810b266eab
ms.sourcegitcommit: edcf15044d7bdf4f8b21fb8f6af4bde475eb13a0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "73529930"
---
# <a name="what-is-quantum-computing"></a><span data-ttu-id="322dd-103">Was ist Quantencomputing?</span><span class="sxs-lookup"><span data-stu-id="322dd-103">What is quantum computing?</span></span>

<span data-ttu-id="322dd-104">Es gibt einige Probleme, die so schwierig und so unglaublich gewaltig sind, dass ihre Lösung selbst bei Zusammenarbeit aller Supercomputer der Welt länger als die Lebensdauer des Universums dauern würde.</span><span class="sxs-lookup"><span data-stu-id="322dd-104">There are some problems so difficult, so incredibly vast, that even if every supercomputer in the world worked on the problem, it would still take longer than the lifetime of the universe to solve.</span></span>

<span data-ttu-id="322dd-105">Quantencomputer bieten das Versprechen, einige der größten Herausforderungen unseres Planeten zu lösen – im Bereich Umweltschutz, Landwirtschaft, Gesundheitswesen, Energie, Klima, Materialwissenschaft und bei Problemen, die wir bisher nicht einmal kennen.</span><span class="sxs-lookup"><span data-stu-id="322dd-105">Quantum computers hold the promise to solve some of our planet's biggest challenges - in environment, agriculture, health, energy, climate, materials science, and problems we’ve not yet even imagined.</span></span> <span data-ttu-id="322dd-106">Der Einfluss von Quantencomputern wird weitreichend sein, so groß wie die Schaffung des Transistors im Jahr 1947, die den Weg zur digitalen Ökonomie von heute ebnete.</span><span class="sxs-lookup"><span data-stu-id="322dd-106">The impact of quantum computers will be far-reaching and have as great an impact as the creation of the transistor in 1947, which paved the way for today’s digital economy.</span></span>

<span data-ttu-id="322dd-107">Quantencomputer nutzen die einzigartigen Verhaltensweisen der Quantenphysik, um ein neues und leistungsstarkes Modell des Computings bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="322dd-107">Quantum computing harnesses the unique behavior of quantum physics to provide a new and powerful model of computing.</span></span> <span data-ttu-id="322dd-108">Die Theorie der Quantenphysik postuliert, dass Materie auf Quantenebene sich in einer Überlagerung mehrerer klassischer Zustände befinden kann.</span><span class="sxs-lookup"><span data-stu-id="322dd-108">The theory of quantum physics posits that matter, at a quantum level can be in a superposition of multiple classical states.</span></span> <span data-ttu-id="322dd-109">Und diese vielen Zustände überlagern einander wie Wellen in einem Gezeitenbecken.</span><span class="sxs-lookup"><span data-stu-id="322dd-109">And those many states interfere with each other like waves in a tide pool.</span></span>  <span data-ttu-id="322dd-110">Nach einer Messung stellt sich einer der klassischen Zustände ein.</span><span class="sxs-lookup"><span data-stu-id="322dd-110">The state of matter after a measurement "collapses" into one of the classical states.</span></span> 

<span data-ttu-id="322dd-111">Daraufhin wird bei einer Wiederholung der gleichen Messung das gleiche klassische Ergebnis erreicht.</span><span class="sxs-lookup"><span data-stu-id="322dd-111">Thereafter, repeating the same measurement will produce the same classical result.</span></span>  <span data-ttu-id="322dd-112">Eine Quantenverschränkung tritt auf, wenn Partikel so miteinander interagieren, dass sich der Quantenzustand der einzelnen Partikel nur in Abhängigkeit von den anderen Partikeln beschreiben lässt, selbst wenn die Partikel physisch weit voneinander entfernt sind.</span><span class="sxs-lookup"><span data-stu-id="322dd-112">Quantum entanglement occurs when particles interact in ways such that the quantum state of each cannot be described independently of the others, even if the particles are physically far apart.</span></span>  

<span data-ttu-id="322dd-113">Quantencomputer speichern Informationen in Quantenzuständen von Materie und profitieren von Quanteneigenschaften wie Superposition und Verschränkung, um Quantenberechnungen auf der Grundlage dieser Informationen durchzuführen, wobei sie Quanteninterferenzen nutzen und lernen, sie zu programmieren.</span><span class="sxs-lookup"><span data-stu-id="322dd-113">Quantum computing stores information in quantum states of matter and uses its quantum nature of superposition and entanglement to realize quantum operations that compute on that information, thereby harnessing and learning to program quantum interference.</span></span>

<span data-ttu-id="322dd-114">Quantencomputing mag sich einschüchternd anhören, aber mit den richtigen Ressourcen können Sie noch heute anfangen, Quantenanwendungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="322dd-114">Quantum computing might sound daunting, but with the right resources you can start building quantum applications today.</span></span>

## <a name="the-qubit"></a><span data-ttu-id="322dd-115">Das Qubit</span><span class="sxs-lookup"><span data-stu-id="322dd-115">The qubit</span></span>

<span data-ttu-id="322dd-116">Quantencomputing definiert Computingkonzepte, die das Quantenverhalten widerspiegeln.</span><span class="sxs-lookup"><span data-stu-id="322dd-116">Quantum computing defines computing concepts that reflect the quantum behavior.</span></span>  <span data-ttu-id="322dd-117">Am Anfang des Quantencomputings steht das Konzept eines Qubit.</span><span class="sxs-lookup"><span data-stu-id="322dd-117">Quantum computing begins with the notion of a qubit.</span></span>  <span data-ttu-id="322dd-118">Beim Quantencomputing bildet ein Quantenbit – **Qubit** – eine Quanteninformationseinheit, wie ein klassisches Bit.</span><span class="sxs-lookup"><span data-stu-id="322dd-118">In quantum computing, a quantum bit - **qubit** - is a unit of quantum information, like a classical bit.</span></span> <span data-ttu-id="322dd-119">Klassische Bits enthalten einen einzelnen binären Wert (0 oder 1). Der Zustand eines Qubits kann dagegen eine **Superposition** sein (also 0 und 1 gleichzeitig).</span><span class="sxs-lookup"><span data-stu-id="322dd-119">Where classical bits hold a single binary value such as a 0 or 1, the state of a qubit can be in a **superposition** of 0 and 1 simultaneously.</span></span>  

<span data-ttu-id="322dd-120">Die Messung eines Qubits verändert dessen Zustand.</span><span class="sxs-lookup"><span data-stu-id="322dd-120">The act of measuring a qubit changes a qubit state.</span></span> <span data-ttu-id="322dd-121">Nach der Messung geht das Qubit von einer Superposition in einen der klassischen Zustände über.</span><span class="sxs-lookup"><span data-stu-id="322dd-121">With measurement, the qubit goes from being in superposition to one of the classical states.</span></span>  

<span data-ttu-id="322dd-122">Mehrere Qubits können außerdem **verschränkt** sein.</span><span class="sxs-lookup"><span data-stu-id="322dd-122">Multiple qubits can also be **entangled**.</span></span> <span data-ttu-id="322dd-123">Bei der Messung eines verschränkten Qubits wird unsere Kenntnis des Zustands der anderen Qubits ebenfalls aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="322dd-123">When we make a measurement of one entangled qubit, our knowledge of the state of the other(s) is updated as well.</span></span>

## <a name="quantum-algorithms"></a><span data-ttu-id="322dd-124">Quantenalgorithmen</span><span class="sxs-lookup"><span data-stu-id="322dd-124">Quantum algorithms</span></span>

<span data-ttu-id="322dd-125">Quantenalgorithmen nutzen Quanteneigenschaften und -verhaltensweisen, um klassische Algorithmen zu beschleunigen oder völlig neue Möglichkeiten für die Modellierung physischer Systeme zu bieten.</span><span class="sxs-lookup"><span data-stu-id="322dd-125">Quantum algorithms are designed to take advantage of quantum nature and behavior to speed up classical algorithms, or to provide entirely new ways of modeling physical systems.</span></span>  <span data-ttu-id="322dd-126">Diese Algorithmen nutzen die Art der Informationscodierung durch Qubits sowie die Möglichkeit zur parallelen Verwendung mehrerer verschränkter Qubits in Superposition.</span><span class="sxs-lookup"><span data-stu-id="322dd-126">These algorithms exploit the way qubits encode information and the parallel nature of operating on multiple entangled qubits in superposition.</span></span>  

<span data-ttu-id="322dd-127">Bei klassischen Computern werden Informationen in Bits mit zwei möglichen Werten (1 oder 1) codiert.</span><span class="sxs-lookup"><span data-stu-id="322dd-127">Classical computers encode information in bits; each bit encoding two possible values, 0 or 1.</span></span>  <span data-ttu-id="322dd-128">Ein Qubit codiert zwei Werte gleichzeitig (0 und 1).</span><span class="sxs-lookup"><span data-stu-id="322dd-128">One qubit encodes two values simultaneously, 0 and 1.</span></span>  <span data-ttu-id="322dd-129">Zwei klassische Bits codieren einen von vier möglichen Werten: 00, 01, 10 oder 11. Zwei Qubits codieren dagegen gleichzeitig eine beliebige Superposition der vier Zustände. Bei einer Messung erhalten wir allerdings immer nur einen dieser Werte.</span><span class="sxs-lookup"><span data-stu-id="322dd-129">Two classical bits encode one of 4 possible values, (00, 01, 10, 11) whereas two qubits encode any superposition of the 4 states simultaneously, although we can obtain only one of those values when measuring.</span></span> <span data-ttu-id="322dd-130">Vier Qubits codieren gleichzeitig eine beliebige Superposition von 16 Werten. Dies setzt sich exponentiell so fort.</span><span class="sxs-lookup"><span data-stu-id="322dd-130">Four qubits encode any superposition of 16 values simultaneously, and so on, exponentially.</span></span>  <span data-ttu-id="322dd-131">100 Qubits können mehr Informationen codieren, als heutzutage in den größten Computersystemen zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="322dd-131">100 qubits can encode more information than is available in the largest computer systems today.</span></span>  

<span data-ttu-id="322dd-132">Wenn mehrere verschränkte Qubits zudem kohärent agieren, können sie mehrere Optionen gleichzeitig verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="322dd-132">Furthermore, when multiple entangled qubits act coherently, they can process multiple options simultaneously.</span></span> <span data-ttu-id="322dd-133">Verschränkte Qubits können Informationen in einem Bruchteil der Zeit verarbeiten, die selbst die schnellsten nicht quantengestützten Systeme benötigen würden.</span><span class="sxs-lookup"><span data-stu-id="322dd-133">Entangled qubits can process information in a fraction of the time it would take even the fastest non-quantum systems.</span></span>

<span data-ttu-id="322dd-134">Quantenalgorithmen werden bereits seit mehreren Jahrzehnten erforscht, um diese Quantenattribute nutzbar zu machen, und es wurden bereits zahlreiche innovative Techniken gefunden, um Aufgaben in einem Bruchteil der Zeit zu lösen, die bei Verwendung klassischer Methoden nötig wäre.</span><span class="sxs-lookup"><span data-stu-id="322dd-134">Harnessing these quantum attributes has been the pursuit of multiple decades of quantum algorithm research, and there are many innovative techniques that have been found that solve problems in a fraction of the time it takes to solve classically.</span></span>  

<span data-ttu-id="322dd-135">Einer der berühmtesten Quantenalgorithmen ist der _Shor-Algorithmus_ zur Faktorisierung, der das klassisch sperrige Problem der Faktorisierung einer großen Zahl in zwei Primzahlen schnell genug macht, um eine Gefahr für die klassische Kryptografie zu bilden.</span><span class="sxs-lookup"><span data-stu-id="322dd-135">One of the most famous quantum algorithms is _Shor's algorithm_ for factorization, which makes the classically intractable problem of factorization of a large number into two prime numbers fast enough to challenge traditional cryptography.</span></span>

<span data-ttu-id="322dd-136">Auf der eher konstruktiven Seite werden durch Überlagerung, Quantenverschränkung und die Eigenschaft der **Nichtkopierbarkeit** von Qubits (womit die Unmöglichkeit des unentdeckten Kopierens von Qubits bezeichnet wird) Algorithmen für die Verteilung sicherer kryptografischer Schlüssel möglich.</span><span class="sxs-lookup"><span data-stu-id="322dd-136">On the more constructive side, algorithms for secure cryptographic key distribution are made possible by superposition, quantum entanglement, and the **no cloning** property of qubits, meaning the inability for qubits to be copied without detection.</span></span>

<span data-ttu-id="322dd-137">Der _Grover-Algorithmus_ bietet eine Quantenalgorithmus-Technik, mit der sich beim Durchsuchen unstrukturierter Daten eine quadratische Beschleunigung erzielen lässt.</span><span class="sxs-lookup"><span data-stu-id="322dd-137">_Grover's algorithm_ highlights a quantum algorithm technique that provides a quadratic speed-up for searching unstructured data.</span></span>

## <a name="quantum-hardware"></a><span data-ttu-id="322dd-138">Quantenhardware</span><span class="sxs-lookup"><span data-stu-id="322dd-138">Quantum hardware</span></span>

<span data-ttu-id="322dd-139">In klassischen Computern entsprechen Bits Spannungsniveaus in den Siliziumschaltkreisen.</span><span class="sxs-lookup"><span data-stu-id="322dd-139">In classical computers, bits correspond to voltage levels in silicon circuits.</span></span> <span data-ttu-id="322dd-140">Die Hardware von Quantencomputern kann durch viele physikalische Umsetzungen von Qubits implementiert werden: Ionenfallen, Supraleitung, neutrale Atome, Elektronenspin, Lichtpolarisation, topologische Qubits.</span><span class="sxs-lookup"><span data-stu-id="322dd-140">Quantum computing hardware can be implemented by many different physical realizations of qubits: trapped ions, superconducting, neutral atoms, electron spin, light polarization, topological qubits.</span></span> <span data-ttu-id="322dd-141">Quantenhardware ist eine aufstrebende Technologie.</span><span class="sxs-lookup"><span data-stu-id="322dd-141">Quantum hardware is an emergent technology.</span></span> <span data-ttu-id="322dd-142">Qubits sind naturgemäß anfällig und verlieren bei der Interaktion mit ihrer Umgebung an Kohärenz.</span><span class="sxs-lookup"><span data-stu-id="322dd-142">Qubits are fragile by nature and become less coherent as they interact with their environment.</span></span> <span data-ttu-id="322dd-143">Daher muss ein ausgewogenes Verhältnis zwischen Systemgenauigkeit und Skalierbarkeit gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="322dd-143">Balancing fidelity of the system with scalability is needed.</span></span> <span data-ttu-id="322dd-144">Je größer der Maßstab (d.h. die Anzahl der Qubits), desto höher ist die Fehlerrate.</span><span class="sxs-lookup"><span data-stu-id="322dd-144">The larger the scale (that is, number of qubits), the higher the error rate.</span></span>

<span data-ttu-id="322dd-145">Microsoft entwickelt einen Quantencomputer auf der Grundlage topologischer Qubits.</span><span class="sxs-lookup"><span data-stu-id="322dd-145">Microsoft is developing a quantum computer based on topological qubits.</span></span> <span data-ttu-id="322dd-146">Wir glauben, dass ein topologisches Qubit weniger durch Änderungen in seiner Umgebung beeinflusst wird, was das Maß an externer Fehlerkorrektur verringert.</span><span class="sxs-lookup"><span data-stu-id="322dd-146">We believe a topological qubit will be less impacted by changes in its environment, therefore reducing the degree of external error correction.</span></span> <span data-ttu-id="322dd-147">Topologische Qubits zeichnen sich durch erhöhte Stabilität und Widerstandsfähigkeit gegenüber Umgebungsrauschen aus, was bedeutet, dass sie sich leichter skalieren lassen und länger zuverlässig bleiben.</span><span class="sxs-lookup"><span data-stu-id="322dd-147">Topological qubits feature increased stability and resistance to environmental noise, which means they can more readily scale and remain reliable longer.</span></span>

## <a name="quantum-computing--a-full-hardware-and-software-stack"></a><span data-ttu-id="322dd-148">Quantencomputing: ein vollständiger Hardware- und Softwarestapel</span><span class="sxs-lookup"><span data-stu-id="322dd-148">Quantum computing – a full hardware and software stack</span></span>

<span data-ttu-id="322dd-149">Das Quantenprogramm von Microsoft ist einzigartig, da wir uns auf die Skalierung jeder einzelnen Komponente des Systems konzentrieren, um echte Quantenvorteile zu liefern.</span><span class="sxs-lookup"><span data-stu-id="322dd-149">Microsoft's quantum program is unique in that we focus on scaling each and every component of the system to deliver real quantum impact.</span></span> <span data-ttu-id="322dd-150">Dieser ganzheitliche Ansatz umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="322dd-150">This comprehensive approach involves:</span></span>

* <span data-ttu-id="322dd-151">Aufbau eines Quantencomputers mit zuverlässigen, skalierbaren und fehlertoleranten topologischen Qubits</span><span class="sxs-lookup"><span data-stu-id="322dd-151">building a quantum computer using reliable, scalable, and fault-tolerant topological qubits,</span></span> 
* <span data-ttu-id="322dd-152">Entwicklung einer einzigartigen kryogenischen Steuerungsebene mit geringer Verlustleistung und Wärmeabgabe</span><span class="sxs-lookup"><span data-stu-id="322dd-152">engineering a unique cryogenic control plane with low power and heat dissipation,</span></span> 
* <span data-ttu-id="322dd-153">Entwicklung eines vollständigen Softwarestapels zur Programmierung des Quantencomputers und zur Steuerung des skalierbaren Systems.</span><span class="sxs-lookup"><span data-stu-id="322dd-153">developing a complete software stack to enable programming the quantum computer and controlling the system at scale.</span></span>

<span data-ttu-id="322dd-154">Das Open-Source-QDK (Quantum Development Kit) wurde eingeführt, um Quantenprogrammierung und die Entwicklung von Algorithmen zugänglicher zu machen.</span><span class="sxs-lookup"><span data-stu-id="322dd-154">The open source Quantum Development Kit (QDK) has been introduced to make quantum programming and algorithm development more accessible.</span></span> <span data-ttu-id="322dd-155">Unsere übergeordnete Programmiersprache namens Q# ist auf die Bewältigung der Herausforderungen im Bereich der Quantenprogrammierung ausgelegt.</span><span class="sxs-lookup"><span data-stu-id="322dd-155">Our high-level programming language, Q#, addresses the challenges of quantum programming.</span></span>  <span data-ttu-id="322dd-156">Q# ist als übergeordnete quantenorientierte Programmiersprache für die Entwicklung von Algorithmen und Anwendungen konzipiert.</span><span class="sxs-lookup"><span data-stu-id="322dd-156">We designed Q# as a high-level quantum-focused programming language focused on algorithm and application development.</span></span> <span data-ttu-id="322dd-157">Der Q#-Compiler ist in einen Softwarestapel integriert, der es ermöglicht, einen Quantenalgorithmus bis zu den primitiven Operationen eines Quantencomputers hinab zu kompilieren.</span><span class="sxs-lookup"><span data-stu-id="322dd-157">The Q# compiler is integrated in a software stack that enables a quantum algorithm to be compiled down to the primitive operations of a quantum computer.</span></span>  <span data-ttu-id="322dd-158">Bis zu einem bestimmten Maßstab (Anzahl Qubits) können Quantencomputer auf einem klassischen Computer simuliert werden.</span><span class="sxs-lookup"><span data-stu-id="322dd-158">Up to a certain scale (number of qubits), quantum computing can be simulated on a classical computer.</span></span> <span data-ttu-id="322dd-159">Mithilfe von Simulation können Sie heute beginnen, Quantenprogramme zu schreiben, die morgen auf Quantenhardware ausgeführt werden können.</span><span class="sxs-lookup"><span data-stu-id="322dd-159">Using simulation, you can start to write quantum programs today for running on quantum hardware tomorrow.</span></span>  <span data-ttu-id="322dd-160">Darüber hinaus stehen Beispiele, Bibliotheken und Lernübungen für Q# zur Verfügung, um Ihnen den Einstieg in die Quantenprogrammierung zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="322dd-160">We’ve also paired Q# with samples, libraries, and learning exercises to make it easy to begin quantum programming today.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="322dd-161">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="322dd-161">Next steps</span></span>

* [<span data-ttu-id="322dd-162">Was können Quantencomputer?</span><span class="sxs-lookup"><span data-stu-id="322dd-162">What can quantum computers do?</span></span>](xref:microsoft.quantum.overview.computers)
* [<span data-ttu-id="322dd-163">Einstieg in das Microsoft Quantum Development Kit</span><span class="sxs-lookup"><span data-stu-id="322dd-163">Get started with the Microsoft Quantum Development Kit</span></span>](xref:microsoft.quantum.welcome)
* <span data-ttu-id="322dd-164">Weitere Informationen zu [Konzepten des Quantencomputings](xref:microsoft.quantum.concepts.intro)</span><span class="sxs-lookup"><span data-stu-id="322dd-164">Read more about [Quantum computing concepts](xref:microsoft.quantum.concepts.intro)</span></span>