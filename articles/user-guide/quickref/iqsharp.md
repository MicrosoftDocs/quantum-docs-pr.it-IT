---
title: Comandi magic di IQ#
description: 'Pagina di riferimento rapido per i comandi IQ # Magic con i notebook Q # Jupyter'
author: gillenhaalb
ms.author: a-gibec@microsoft.com
ms.date: 03/05/2020
uid: microsoft.quantum.guide.quickref.iqsharp
ms.openlocfilehash: 0cd1a2289132e2760a21fd9d4f4083696353e271
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83431020"
---
# <a name="iq-magic-commands"></a><span data-ttu-id="c9f7e-103">Comandi magic di IQ#</span><span class="sxs-lookup"><span data-stu-id="c9f7e-103">IQ# Magic Commands</span></span>

### <a name="general"></a><span data-ttu-id="c9f7e-104">Generale</span><span class="sxs-lookup"><span data-stu-id="c9f7e-104">General</span></span>

- <span data-ttu-id="c9f7e-105">`%config`: Ottiene o imposta le preferenze di configurazione.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-105">`%config`: Sets or gets configuration preferences.</span></span>
- <span data-ttu-id="c9f7e-106">`%estimate`: Esegue una determinata funzione o operazione nel computer di destinazione QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-106">`%estimate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="c9f7e-107">`%lsmagic`: Restituisce un elenco di tutti i comandi Magic attualmente disponibili.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-107">`%lsmagic`: Returns a list of all currently available magic commands.</span></span>
- <span data-ttu-id="c9f7e-108">`%package`: Consente di caricare un pacchetto NuGet.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-108">`%package`: Provides the ability to load a Nuget package.</span></span>
- <span data-ttu-id="c9f7e-109">`%performance`: Riporta le metriche delle prestazioni correnti per questo kernel.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-109">`%performance`: Reports current performance metrics for this kernel.</span></span>
- <span data-ttu-id="c9f7e-110">`%simulate`: Esegue una determinata funzione o operazione nel computer di destinazione QuantumSimulator.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-110">`%simulate`: Runs a given function or operation on the QuantumSimulator target machine.</span></span>
- <span data-ttu-id="c9f7e-111">`%toffoli`: Esegue una determinata funzione o operazione nel computer di destinazione del simulatore ToffoliSimulator.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-111">`%toffoli`: Runs a given function or operation on the ToffoliSimulator simulator target machine.</span></span>
- <span data-ttu-id="c9f7e-112">`%who`: Fornisce azioni correlate all'area di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-112">`%who`: Provides actions related to the current workspace.</span></span>
- <span data-ttu-id="c9f7e-113">`%workspace`: Restituisce un elenco di tutte le operazioni e le funzioni definite nella sessione corrente, in modo interattivo o caricato dall'area di lavoro corrente.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-113">`%workspace`: Returns a list of all operations and functions defined in the current session, either interactively or loaded from the current workspace.</span></span>

### <a name="chemistry"></a><span data-ttu-id="c9f7e-114">Chimica</span><span class="sxs-lookup"><span data-stu-id="c9f7e-114">Chemistry</span></span>

- <span data-ttu-id="c9f7e-115">`%chemistry.broombridge`: Carica e restituisce la rappresentazione di un problema di struttura elettronica Broombridge da un file con estensione YAML specificato.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-115">`%chemistry.broombridge`: Loads and returns Broombridge electronic structure problem representation from a given .yaml file.</span></span>
- <span data-ttu-id="c9f7e-116">`%chemistry.encode`: Codifica un'Hamiltoniana fermione in un formato utilizzabile da Q #.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-116">`%chemistry.encode`: Encodes a fermion Hamiltonian to a format consumable by Q#.</span></span>
- <span data-ttu-id="c9f7e-117">`%chemistry.fh.add_terms`: Aggiunge termini a un'Hamiltoniana fermione.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-117">`%chemistry.fh.add_terms`: Adds terms to a fermion Hamiltonian.</span></span>
- <span data-ttu-id="c9f7e-118">`%chemistry.fh.load`: Carica l'Hamiltoniana fermione per un problema di struttura elettronica.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-118">`%chemistry.fh.load`: Loads the fermion Hamiltonian for an electronic structure problem.</span></span> <span data-ttu-id="c9f7e-119">Il problema viene caricato da un file o passato come argomento.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-119">The problem is loaded from a file or passed as an argument.</span></span>
- <span data-ttu-id="c9f7e-120">`%chemistry.inputstate.load`: Carica un problema di struttura elettronica Broombridge e restituisce lo stato di input selezionato.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-120">`%chemistry.inputstate.load`: Loads Broombridge electronic structure problem and returns selected input state.</span></span>

### <a name="from-microsoftquantumkatas-package"></a><span data-ttu-id="c9f7e-121">Dal pacchetto Microsoft. Quantum. Katas</span><span class="sxs-lookup"><span data-stu-id="c9f7e-121">From Microsoft.Quantum.Katas package</span></span>

- <span data-ttu-id="c9f7e-122">`%kata`: Esegue un singolo test e segnala se il test è stato superato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-122">`%kata`: Executes a single test, and reports whether the test passed successfully.</span></span>
- <span data-ttu-id="c9f7e-123">`%check_kata`: Verifica l'implementazione di riferimento per un singolo test di Kata.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-123">`%check_kata`: Checks the reference implementation for a single kata's test.</span></span>
    <span data-ttu-id="c9f7e-124">In particolare, sostituisce l'implementazione di riferimento per una singola attività nella cella e segnala se il test è stato superato correttamente.</span><span class="sxs-lookup"><span data-stu-id="c9f7e-124">Specifically, it substitutes the reference implementation for a single task into the cell, and reports whether the test passed successfully.</span></span>
