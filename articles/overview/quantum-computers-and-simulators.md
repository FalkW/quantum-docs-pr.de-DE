---
title: Quantencomputer und -simulatoren
description: Hier finden Sie Informationen zu Quantenhardware und Quantensimulatoren sowie zur Funktionsweise von Quantenoperationen.
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.simulators
ms.openlocfilehash: 04f90e9f88cf17259f96532617ef6f092b56b859
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2020
ms.locfileid: "83430746"
---
# <a name="quantum-computers-and-quantum-simulators"></a><span data-ttu-id="d6c2e-103">Quantencomputer und -simulatoren</span><span class="sxs-lookup"><span data-stu-id="d6c2e-103">Quantum computers and quantum simulators</span></span>

<span data-ttu-id="d6c2e-104">Die Entwicklung von Quantencomputern steckt noch in den Kinderschuhen.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-104">Quantum computers are still in the infancy of their development.</span></span> <span data-ttu-id="d6c2e-105">Hardware und Wartung sind teuer, und die meisten Systeme befinden sich in Universitäten und Forschungslabors.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-105">The hardware and maintenance are expensive, and most systems are located in universities and research labs.</span></span> <span data-ttu-id="d6c2e-106">Die Entwicklung der Technologie schreitet jedoch voran, und inzwischen ist eingeschränkter öffentlicher Zugriff auf einige Systeme verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-106">The technology is advancing, though, and limited public access to some systems is available.</span></span>

<span data-ttu-id="d6c2e-107">Bei Quantensimulatoren handelt es sich um Softwareprogramme, die auf klassischen Computern ausgeführt werden und das Ausführen und Testen von Quantenprogrammen in einer Umgebung ermöglichen, die die Reaktion von Qubits auf verschiedene Operationen vorhersagt.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-107">Quantum simulators are software programs that run on classical computers and make it possible to run and test quantum programs in an environment that predicts how qubits will react to different operations.</span></span>

## <a name="quantum-hardware"></a><span data-ttu-id="d6c2e-108">Quantenhardware</span><span class="sxs-lookup"><span data-stu-id="d6c2e-108">Quantum hardware</span></span>

<span data-ttu-id="d6c2e-109">Ein Quantencomputer besteht aus drei Hauptkomponenten: einem Bereich für die Qubits, einer Methode für die Signalübertragung an die Qubits sowie einem klassischen Computer zum Ausführen eines Programms und zum Senden von Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-109">A quantum computer has three primary parts: an area that houses the qubits, a method for transferring signals to the qubits, and a classical computer to run a program and send instructions.</span></span>

- <span data-ttu-id="d6c2e-110">Das für Qubits verwendete Quantenmaterial ist fragil und höchst empfindlich gegenüber Umwelteinflüssen.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-110">The quantum material used for qubits is fragile and highly sensitive to environmental interferences.</span></span> <span data-ttu-id="d6c2e-111">Bei einigen Methoden zur Speicherung von Qubits wird die Einheit, die die Qubits enthält, auf eine Temperatur knapp über dem absoluten Nullpunkt gekühlt, um die Kohärenz zu maximieren.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-111">For some methods of qubit storage, the unit that houses the qubits is kept at a temperature just above absolute zero to maximize their coherence.</span></span> <span data-ttu-id="d6c2e-112">Bei anderen Arten von Einheiten für Qubits wird eine Vakuumkammer verwendet, um Schwingungen zu minimieren und die Qubits zu stabilisieren.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-112">Other types of qubit housing use a vacuum chamber to help minimize vibrations and stabilize the qubits.</span></span>  
- <span data-ttu-id="d6c2e-113">Signale können auf verschiedene Weise an die Qubits gesendet werden – etwa mithilfe von Mikrowellen, per Laser oder mittels Stromspannung.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-113">Signals can be sent to the qubits using a variety of methods including microwaves, laser, and voltage.</span></span>

<span data-ttu-id="d6c2e-114">Damit ein Quantencomputer ordnungsgemäß funktioniert, muss eine Vielzahl von Herausforderungen bewältigt werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-114">Quantum computers face a multitude of challenges to operate correctly.</span></span> <span data-ttu-id="d6c2e-115">Die Fehlerkorrektur ist bei Quantencomputern ein erhebliches Problem, und die Fehlerrate erhöht sich mit zunehmender Qubit-Anzahl (also beim Hochskalieren).</span><span class="sxs-lookup"><span data-stu-id="d6c2e-115">Error correction in quantum computers is a significant issue, and scaling up (adding more qubits) increases the error rate.</span></span> <span data-ttu-id="d6c2e-116">Aufgrund dieser Einschränkungen sind wir noch weit von einem Quanten-PC für den eigenen Schreibtisch entfernt. Ein für kommerzielle Zwecke geeigneter und in einer Laborumgebung betriebener Quantencomputer ist allerdings bereits vorstellbar.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-116">Because of these limitations, a quantum PC for your desktop is far in the future, but a commercially-viable lab-based quantum computer is closer.</span></span>

## <a name="quantum-simulators"></a><span data-ttu-id="d6c2e-117">Quantensimulatoren</span><span class="sxs-lookup"><span data-stu-id="d6c2e-117">Quantum simulators</span></span>

<span data-ttu-id="d6c2e-118">Mit auf klassischen Computern ausgeführten Quantensimulatoren lässt sich das Ausführen von Quantenalgorithmen auf einem Quantensystem simulieren.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-118">Quantum simulators that run on classical computers allow you to simulate the execution of quantum algorithms on a quantum system.</span></span>  <span data-ttu-id="d6c2e-119">Das Quantum Development Kit (QDK) von Microsoft enthält einen Vektorsimulator für den vollständigen Zustand sowie weitere spezialisierte Quantensimulatoren.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-119">Microsoft’s Quantum Development Kit (QDK) includes a full-state vector simulator along with other specialized quantum simulators.</span></span>

## <a name="topological-qubit"></a><span data-ttu-id="d6c2e-120">Topologisches Qubit</span><span class="sxs-lookup"><span data-stu-id="d6c2e-120">Topological qubit</span></span>

<span data-ttu-id="d6c2e-121">Microsoft entwickelt einen Quantencomputer auf der Grundlage topologischer Qubits.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-121">Microsoft is developing a quantum computer based on topological qubits.</span></span> <span data-ttu-id="d6c2e-122">Ein topologisches Qubit wird weniger durch Veränderungen in seiner Umgebung beeinflusst, was das Maß an erforderlicher externer Fehlerkorrektur verringert.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-122">A topological qubit will be less impacted by changes in its environment, therefore reducing the degree of external error correction required.</span></span>

<span data-ttu-id="d6c2e-123">Topologische Qubits zeichnen sich durch erhöhte Stabilität und Widerstandsfähigkeit gegenüber Umgebungsrauschen aus, was bedeutet, dass sie sich leichter skalieren lassen und länger zuverlässig bleiben.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-123">Topological qubits feature increased stability and resistance to environmental noise, which means they can more readily scale and remain reliable longer.</span></span>

## <a name="microsoft-and-quantum-hardware-partnerships"></a><span data-ttu-id="d6c2e-124">Microsoft und Partnerschaften für Quantenhardware</span><span class="sxs-lookup"><span data-stu-id="d6c2e-124">Microsoft and quantum hardware partnerships</span></span>

<span data-ttu-id="d6c2e-125">Microsoft arbeitet mit den Quantenhardwareherstellern IonQ, Honeywell und QCI zusammen, um Entwicklern in Zukunft den Zugriff auf Quantencomputer zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-125">Microsoft is partnering with quantum hardware manufacturers IonQ, Honeywell, and QCI to make quantum computers accessible to developers in the future.</span></span> <span data-ttu-id="d6c2e-126">Über die Azure Quantum-Plattform können Entwickler das Quantum Development Kit (QDK) von Microsoft sowie Q# verwenden, um Quantenprogramme zu schreiben und remote auszuführen.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-126">Leveraging the Azure Quantum platform, developers will be able to use Microsoft’s Quantum Development Kit (QDK) and Q# to write quantum programs and run them remotely.</span></span>

## <a name="quantum-computations"></a><span data-ttu-id="d6c2e-127">Quantenberechnungen</span><span class="sxs-lookup"><span data-stu-id="d6c2e-127">Quantum computations</span></span>

<span data-ttu-id="d6c2e-128">Das Ausführen von Berechnungen auf einem Quantencomputer oder in einem Quantensimulator basiert auf einem einfachen Prozess:</span><span class="sxs-lookup"><span data-stu-id="d6c2e-128">Performing computations on a quantum computer or quantum simulator follow a basic process:</span></span>

- <span data-ttu-id="d6c2e-129">Zugreifen auf die Qubits</span><span class="sxs-lookup"><span data-stu-id="d6c2e-129">Access the qubits</span></span>
- <span data-ttu-id="d6c2e-130">Initialisieren der Qubits, sodass sie den gewünschten Zustand aufweisen</span><span class="sxs-lookup"><span data-stu-id="d6c2e-130">Initialize the qubits to the desired state</span></span>
- <span data-ttu-id="d6c2e-131">Durchführen von Operationen, um die Zustände der Qubits zu transformieren</span><span class="sxs-lookup"><span data-stu-id="d6c2e-131">Perform operations to transform the states of the qubits</span></span>
- <span data-ttu-id="d6c2e-132">Messen der neuen Zustände der Qubits</span><span class="sxs-lookup"><span data-stu-id="d6c2e-132">Measure the new states of the qubits</span></span>

<span data-ttu-id="d6c2e-133">Für die Initialisierung und Transformierung von Qubits werden **Quantenoperationen** (manchmal auch als Quantengatter bezeichnet) verwendet.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-133">Initializing and transforming qubits is done using **quantum operations** (sometimes called quantum gates).</span></span> <span data-ttu-id="d6c2e-134">Quantenoperationen sind vergleichbar mit Logikoperationen aus dem klassischen Computing (beispielsweise AND, OR, NOT oder XOR).</span><span class="sxs-lookup"><span data-stu-id="d6c2e-134">Quantum operations are similar to logic operations in classical computing, such as AND, OR, NOT, and XOR.</span></span> <span data-ttu-id="d6c2e-135">Die Komplexität reicht dabei von einfachen Operationen (etwa im Falle eines Qubits, dessen Zustand von 1 in 0 geändert wird, oder im Falle der Verschränkung eines Qubit-Paars) bis hin zur Verwendung einer Reihe von Operationen, um die Wahrscheinlichkeit eines bestimmten Ergebnisses beim Kollaps eines superponierten Qubits zu beeinflussen.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-135">An operation can be as basic as flipping a qubit's state from 1 to 0 or entangling a pair of qubits, to using multiple operations in series to affect the probability of a superposed qubit collapsing one way or the other.</span></span>

> [!NOTE] 
> <span data-ttu-id="d6c2e-136">Die [Q#-Bibliotheken](xref:microsoft.quantum.libraries) enthalten integrierte Operationen, die komplexe Kombinationen von untergeordneten Quantenoperationen definieren.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-136">The [Q# libraries](xref:microsoft.quantum.libraries) provide built-in operations that define complex combinations of lower-level quantum operations.</span></span> <span data-ttu-id="d6c2e-137">Mithilfe der Bibliotheksoperationen können Sie Qubits transformieren und komplexere benutzerdefinierte Operationen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-137">You can use the library operations to transform qubits and to create more complex user-defined operations.</span></span>  

<span data-ttu-id="d6c2e-138">Die Messung des Ergebnisses der Berechnung liefert zwar eine Antwort, bei einigen Quantenalgorithmen ist das aber nicht unbedingt die richtige Antwort.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-138">Measuring the result of the computation tells us an answer, but for some quantum algorithms, not necessarily the correct answer.</span></span> <span data-ttu-id="d6c2e-139">Da das Ergebnis einiger Quantenalgorithmen auf der Wahrscheinlichkeit basiert, die durch die Quantenoperationen konfiguriert wurde, werden diese Berechnungen mehrmals ausgeführt, um eine Wahrscheinlichkeitsverteilung zu erhalten und die Genauigkeit der Ergebnisse zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-139">Because the result of some quantum algorithms is based on the probability that was configured by the quantum operations, these computations are run multiple times to get a probability distribution and refine the accuracy of the results.</span></span>  <span data-ttu-id="d6c2e-140">Die Gewissheit, dass eine Operation eine korrekte Antwort geliefert hat, wird als Quantenverifizierung bezeichnet und ist eine erhebliche Herausforderung beim Quantencomputing.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-140">Assurance that an operation returned a correct answer is known as quantum verification and is a significant challenge in quantum computing.</span></span>

## <a name="summary"></a><span data-ttu-id="d6c2e-141">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="d6c2e-141">Summary</span></span>

<span data-ttu-id="d6c2e-142">Beim Quantencomputing werden zum Teil die gleichen Konzepte genutzt wie beim klassischen Computing, es kommen jedoch auch einige neue Dinge hinzu.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-142">Quantum computing shares some of the same concepts as classical computing but adds a few new twists.</span></span> <span data-ttu-id="d6c2e-143">Im Anschluss finden Sie noch einmal einige wichtige Punkte:</span><span class="sxs-lookup"><span data-stu-id="d6c2e-143">Here are some key takeaways:</span></span>

- <span data-ttu-id="d6c2e-144">Quantenhardware ist teuer und empfindlich, weshalb zum Schreiben und Testen von Programmen Quantensimulatoren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-144">Quantum hardware is expensive and fragile to work with, so quantum simulators are used to write and test programs.</span></span>
- <span data-ttu-id="d6c2e-145">Sowohl klassische Computer als auch Quantencomputer nutzen Logikoperationen (oder -gatter) zur Vorbereitung von Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-145">Both classical and quantum computers use logic operations (or gates) to prepare computations.</span></span>
- <span data-ttu-id="d6c2e-146">Bei Quantenberechnungen werden Wahrscheinlichkeiten zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-146">Quantum computations return probabilities.</span></span>

<span data-ttu-id="d6c2e-147">Fortschritte bei der Quantenhardware und bei Quantentechniken führen zu schnellen Veränderungen in diesem Bereich.</span><span class="sxs-lookup"><span data-stu-id="d6c2e-147">Advancements in quantum hardware and techniques is rapidly changing the field.</span></span> <span data-ttu-id="d6c2e-148">Informationen zu einigen aktuellen Entwicklungen finden Sie [hier](https://phys.org/search/?search=quantum+computer&s=0).</span><span class="sxs-lookup"><span data-stu-id="d6c2e-148">Here are just a few of the [current developments](https://phys.org/search/?search=quantum+computer&s=0).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d6c2e-149">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d6c2e-149">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d6c2e-150">Was sind die Programmiersprache Q# und das QDK?</span><span class="sxs-lookup"><span data-stu-id="d6c2e-150">What is the Q# programming language and QDK?</span></span>](xref:microsoft.quantum.overview.q-sharp)