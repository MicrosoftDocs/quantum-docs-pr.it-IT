---
title: Librerie di Quantum Development Kit
description: Panoramica delle librerie standard, di chimica e numerica incluse nel Microsoft Quantum Development Kit.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries
no-loc:
- Q#
- $$v
ms.openlocfilehash: d61fe459362fdb5f3550768a26b34656a8a538a7
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869104"
---
# <a name="overview-of-no-locq-libraries"></a><span data-ttu-id="b169d-103">Panoramica delle librerie Q#</span><span class="sxs-lookup"><span data-stu-id="b169d-103">Overview of Q# Libraries</span></span>
<span data-ttu-id="b169d-104">Il kit di sviluppo Microsoft Quantum (QDK) include diverse librerie per semplificare lo sviluppo di applicazioni quantistiche in Q#.</span><span class="sxs-lookup"><span data-stu-id="b169d-104">The Quantum Development Kit is provided with several libraries to make it easier to develop quantum applications in Q#.</span></span>
<span data-ttu-id="b169d-105">Questa sezione della documentazione descrive queste librerie e spiega come usarle nei programmi.</span><span class="sxs-lookup"><span data-stu-id="b169d-105">In this section of the documentation, we describe these libraries and how to use them in your programs.</span></span>

- <span data-ttu-id="b169d-106">[**Librerie standard**](xref:microsoft.quantum.libraries.standard.intro): questa sezione descrive il preludio, che definisce l'interfaccia tra i programmi Q# e i computer di destinazione, e il canone, una libreria Q# che fornisce operazioni e funzioni generali da usare durante la scrittura di programmi Q#.</span><span class="sxs-lookup"><span data-stu-id="b169d-106">[**Standard libraries**](xref:microsoft.quantum.libraries.standard.intro): This section describes the prelude, which defines the interface between Q# programs and target machines, and the canon, a Q# library that provides general-purpose operations and functions for use in writing Q# programs.</span></span>
- <span data-ttu-id="b169d-107">[**Libreria di chimica quantistica**](xref:microsoft.quantum.chemistry.concepts.intro): questa sezione descrive la libreria di chimica quantistica, che fornisce un modello di dati per il caricamento delle rappresentazioni delle hamiltoniane di particelle fermioniche e delle operazioni e funzioni di simulazione quantistica che agiscono su queste rappresentazioni.</span><span class="sxs-lookup"><span data-stu-id="b169d-107">[**Quantum chemistry library**](xref:microsoft.quantum.chemistry.concepts.intro): This section describes the quantum chemistry library, which provides a data model for loading representations of fermionic Hamiltonians and quantum simulation operations and functions which act on these representations.</span></span>
- <span data-ttu-id="b169d-108">[**Libreria numerica quantistica**](xref:microsoft.quantum.numerics.intro): questa sezione descrive la libreria numerica quantistica, che fornisce le implementazioni per una serie di funzioni matematiche.</span><span class="sxs-lookup"><span data-stu-id="b169d-108">[**Quantum numerics library**](xref:microsoft.quantum.numerics.intro): This section describes the quantum numerics library, which provides implementations for a host of mathematical functions.</span></span> <span data-ttu-id="b169d-109">Supporta le rappresentazioni di numeri interi (con e senza segno) e a virgola fissa.</span><span class="sxs-lookup"><span data-stu-id="b169d-109">It supports integer (signed & unsigned) and fixed-point representations.</span></span>
- <span data-ttu-id="b169d-110">[**Libreria di Machine Learning quantistico**](xref:microsoft.quantum.machine-learning.concepts.intro): questa sezione descrive la libreria di Machine Learning quantistico, che fornisce un'implementazione dei classificatori sequenziali che sfruttano i vantaggi del calcolo quantistico per comprendere i dati.</span><span class="sxs-lookup"><span data-stu-id="b169d-110">[**Quantum machine learning library**](xref:microsoft.quantum.machine-learning.concepts.intro): This section describes the quantum machine learning library, which provides an implementation of the sequential classifiers that take advantage of quantum computing to understand data.</span></span>

<span data-ttu-id="b169d-111">Le origini delle librerie e gli esempi di codice sono scaricabili da GitHub.</span><span class="sxs-lookup"><span data-stu-id="b169d-111">Sources of the libraries as well as code samples can be obtained from GitHub.</span></span>
<span data-ttu-id="b169d-112">Per altre informazioni, vedere [Licenze](xref:microsoft.quantum.libraries.licensing).</span><span class="sxs-lookup"><span data-stu-id="b169d-112">See [Licensing](xref:microsoft.quantum.libraries.licensing) for further information.</span></span> <span data-ttu-id="b169d-113">Tenere presente che i riferimenti a pacchetti ("file binari") sono disponibili anche per le librerie e costituiscono un'alternativa per includere le librerie nei progetti.</span><span class="sxs-lookup"><span data-stu-id="b169d-113">Note that package references ("binaries") are available also for the libraries and offer another way of including the libraries in projects.</span></span>
<span data-ttu-id="b169d-114">È possibile ottenere tali riferimenti tramite [NuGet](https://nuget.org).</span><span class="sxs-lookup"><span data-stu-id="b169d-114">A convenient way of obtaining them is via [NuGet](https://nuget.org).</span></span>
