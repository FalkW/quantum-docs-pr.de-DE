---
title: Beispiele der Quantenchemie | Microsoft-Dokumentation
description: Beispiele der Quantenchemie in der Dokumentation
author: guanghaolow
ms.author: gulow
ms.date: 10/23/2018
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.examples
ms.openlocfilehash: 586ea98321ff71947df8d81a2141a8b050dbd9ed
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2019
ms.locfileid: "72960398"
---
# <a name="quantum-chemistry-examples"></a><span data-ttu-id="89eb9-103">Beispiele der Quantenchemie</span><span class="sxs-lookup"><span data-stu-id="89eb9-103">Quantum chemistry examples</span></span>

<span data-ttu-id="89eb9-104">In Konzepten der Quantenchemie wurden Beispiele für Fermion-Hamiltonoperator manuell konstruiert.</span><span class="sxs-lookup"><span data-stu-id="89eb9-104">In the quantum chemistry concepts, we manually constructed example fermion Hamiltonians.</span></span> <span data-ttu-id="89eb9-105">Nun werden die Chemiesimulationsalgorithmen, die unter [Simulieren von hamiltonschen Dynamiken](xref:microsoft.quantum.libraries.standard.algorithms) beschrieben werden, mit der [Quantenphasenschätzung](xref:microsoft.quantum.libraries.characterization) in der kanonischen Bibliothek kombiniert.</span><span class="sxs-lookup"><span data-stu-id="89eb9-105">We now combine the chemistry simulation algorithms outlined in [Simulating Hamiltonian dynamics](xref:microsoft.quantum.libraries.standard.algorithms) with [quantum phase estimation](xref:microsoft.quantum.libraries.characterization) in the canon library.</span></span> <span data-ttu-id="89eb9-106">Diese Kombination ermöglicht Schätzungen des Energieniveaus im dargestellten Molekül. Dies ist einer der wichtigsten Anwendungsfälle von Quantenchemie in einem Quantencomputer.</span><span class="sxs-lookup"><span data-stu-id="89eb9-106">This combination allows us to obtain  estimates of energy levels in the represented molecule, which is one of the key applications of quantum chemistry on a quantum computer.</span></span> 

<span data-ttu-id="89eb9-107">Anstatt die Regeln zu Hamiltonoperatoren einzeln aufzuführen, arbeiten Sie sich durch Beispiele, die die Durchführung von Quantenchemieexperimenten nach Maß ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="89eb9-107">Instead of specifying terms of the Hamiltonian one-by-one, we also work through some examples that allow us to perform quantum chemistry experiments at scale.</span></span> <span data-ttu-id="89eb9-108">Sie Beginnen mit Beispielen, in denen ein chemischer Hamiltonoperator geladen wird, der im [Broombridge-Schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="89eb9-108">We begin with examples that load a chemistry Hamiltonian encoded in the [Broombridge schema](xref:microsoft.quantum.libraries.chemistry.schema.broombridge).</span></span>

<span data-ttu-id="89eb9-109">Mit Molekülen, die für die Simulation im [Simulator für vollständige Zustände](xref:microsoft.quantum.machines.full-state-simulator) zu groß sind, kann dennoch interessante Wissenschaft durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="89eb9-109">For molecules that are too large to simulate on the [full state simulator](xref:microsoft.quantum.machines.full-state-simulator), interesting science can still be performed.</span></span> <span data-ttu-id="89eb9-110">Beispielsweise können die Ressourcenkosten zum Durchführen umfassender Chemiesimulationen immer noch mithilfe des [Ablaufverfolgungssimulators](xref:microsoft.quantum.machines.qc-trace-simulator.intro) ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="89eb9-110">For instance, the resource costs of performing large chemistry simulations may still be evaluated by targeting the [trace simulator](xref:microsoft.quantum.machines.qc-trace-simulator.intro).</span></span>

<span data-ttu-id="89eb9-111">Als Nächstes werden einige interessante Anwendungsfälle der Chemiesimulationsbibliothek mithilfe einiger Beispiele veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="89eb9-111">Let us now illustrate interesting applications of the chemistry simulation library through a few of the provided samples.</span></span>