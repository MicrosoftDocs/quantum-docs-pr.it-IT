---
title: Linguaggio di programmazione Q# | Microsoft Docs
description: Linguaggio di programmazione Q#
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.language.intro
ms.openlocfilehash: d8759b9f043d2e13f4b0c97d54bd824c7e87d6de
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2019
ms.locfileid: "73035266"
---
# <a name="the-q-programming-language"></a><span data-ttu-id="d5273-103">Linguaggio di programmazione Q#</span><span class="sxs-lookup"><span data-stu-id="d5273-103">The Q# Programming Language</span></span>

# <a name="introduction"></a><span data-ttu-id="d5273-104">Introduzione</span><span class="sxs-lookup"><span data-stu-id="d5273-104">Introduction</span></span>

<span data-ttu-id="d5273-105">Un modello naturale per il calcolo quantistico consiste nel considerare il computer quantistico come un coprocessore, simile a quello usato per GPU, FPGA e altri processori aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="d5273-105">A natural model for quantum computation is to treat the quantum computer as a coprocessor, similar to that used for GPUs, FPGAs, and other adjunct processors.</span></span>
<span data-ttu-id="d5273-106">La logica di controllo principale esegue il codice classico in un computer "host" classico.</span><span class="sxs-lookup"><span data-stu-id="d5273-106">The primary control logic runs classical code on a classical "host" computer.</span></span>
<span data-ttu-id="d5273-107">Quando appropriato e necessario, il programma host può richiamare una subroutine che viene eseguita nel processore aggiuntivo.</span><span class="sxs-lookup"><span data-stu-id="d5273-107">When appropriate and necessary, the host program can invoke a subroutine that runs on the adjunct processor.</span></span>
<span data-ttu-id="d5273-108">Al termine della subroutine, il programma host ottiene l'accesso ai risultati della subroutine.</span><span class="sxs-lookup"><span data-stu-id="d5273-108">When the subroutine completes, the host program gets access to the subroutine's results.</span></span>

<span data-ttu-id="d5273-109">Q# (Q-Sharp) è un linguaggio di programmazione specifico di dominio usato per esprimere gli algoritmi quantistici.</span><span class="sxs-lookup"><span data-stu-id="d5273-109">Q# (Q-sharp) is a domain-specific programming language used for expressing quantum algorithms.</span></span>
<span data-ttu-id="d5273-110">Deve essere usato per la scrittura di subroutine che vengono eseguite su un processore quantistico aggiuntivo, sotto il controllo di un computer e un programma host classico.</span><span class="sxs-lookup"><span data-stu-id="d5273-110">It is to be used for writing subroutines that execute on an adjunct quantum processor, under the control of a classical host program and computer.</span></span>
<span data-ttu-id="d5273-111">Fintanto che i processori quantistici non sono ampiamente disponibili, le subroutine Q# vengono eseguite in un simulatore.</span><span class="sxs-lookup"><span data-stu-id="d5273-111">Until quantum processors are widely available, Q# subroutines execute on a simulator.</span></span>

<span data-ttu-id="d5273-112">Q# fornisce un set ridotto di tipi primitivi, insieme a due modi (matrici e tuple) per la creazione di nuovi tipi strutturati.</span><span class="sxs-lookup"><span data-stu-id="d5273-112">Q# provides a small set of primitive types, along with two ways (arrays and tuples) for creating new, structured types.</span></span>
<span data-ttu-id="d5273-113">Supporta un modello procedurale di base per la scrittura di programmi, con cicli e istruzioni if/then (se/allora).</span><span class="sxs-lookup"><span data-stu-id="d5273-113">It supports a basic procedural model for writing programs, with loops and if/then statements.</span></span>
<span data-ttu-id="d5273-114">I costrutti di primo livello in Q# sono tipi, operazioni e funzioni definiti dall'utente.</span><span class="sxs-lookup"><span data-stu-id="d5273-114">The top-level constructs in Q# are user defined types, operations, and functions.</span></span>

<span data-ttu-id="d5273-115">Le sezioni seguenti illustrano in dettaglio:</span><span class="sxs-lookup"><span data-stu-id="d5273-115">The following sections detail:</span></span>
- [<span data-ttu-id="d5273-116">Modello di tipo</span><span class="sxs-lookup"><span data-stu-id="d5273-116">The Type Model</span></span>](xref:microsoft.quantum.language.type-model)
- [<span data-ttu-id="d5273-117">Espressioni</span><span class="sxs-lookup"><span data-stu-id="d5273-117">Expressions</span></span>](xref:microsoft.quantum.language.expressions)
- [<span data-ttu-id="d5273-118">Istruzioni</span><span class="sxs-lookup"><span data-stu-id="d5273-118">Statements</span></span>](xref:microsoft.quantum.language.statements)
- [<span data-ttu-id="d5273-119">Struttura dei file</span><span class="sxs-lookup"><span data-stu-id="d5273-119">File Structure</span></span>](xref:microsoft.quantum.language.file-structure)

# <a name="conventions"></a><span data-ttu-id="d5273-120">Convenzioni</span><span class="sxs-lookup"><span data-stu-id="d5273-120">Conventions</span></span>

<span data-ttu-id="d5273-121">Stiamo lavorando per garantire che i segni di punteggiatura comuni vengano usati in modo coerente in tutte le situazioni.</span><span class="sxs-lookup"><span data-stu-id="d5273-121">We are working to ensure that common punctuation marks are used consistently in all situations.</span></span>
<span data-ttu-id="d5273-122">Questo ha l'obiettivo di facilitare l'apprendimento e la lettura di Q#, dal momento che tali segni hanno sempre lo stesso significato e lo stesso concetto è sempre rappresentato nel medesimo modo.</span><span class="sxs-lookup"><span data-stu-id="d5273-122">We expect that this will make Q# easier to learn and to read because these marks always mean the same thing, and the same concept is always represented the same way.</span></span>

<span data-ttu-id="d5273-123">In particolare:</span><span class="sxs-lookup"><span data-stu-id="d5273-123">Specifically:</span></span>

- <span data-ttu-id="d5273-124">Il punto e virgola, `;`, viene usato per terminare un'istruzione o una direttiva a riga singola.</span><span class="sxs-lookup"><span data-stu-id="d5273-124">The semi-colon, `;`, is used to end a statement or single-line directive.</span></span>
  <span data-ttu-id="d5273-125">Non viene usato per altri scopi.</span><span class="sxs-lookup"><span data-stu-id="d5273-125">It is not used for any other purpose.</span></span>
- <span data-ttu-id="d5273-126">La virgola, `,`, viene usata per separare gli elementi di una sequenza.</span><span class="sxs-lookup"><span data-stu-id="d5273-126">The comma, `,`, is used to separate elements of a sequence.</span></span> <span data-ttu-id="d5273-127">Viene usata per i valori letterali tupla, i valori letterali matrice, gli elenchi di argomenti, le definizioni di tuple e gli elenchi di tipi.</span><span class="sxs-lookup"><span data-stu-id="d5273-127">It is used for tuple literals, array literals, argument lists, tuple definitions, and type lists.</span></span> <span data-ttu-id="d5273-128">**A seguito di una modifica rispetto alle versioni precedenti, `;` non è più supportato come separatore di valori letterali matrice.**</span><span class="sxs-lookup"><span data-stu-id="d5273-128">**In a change from earlier versions, `;` is no longer supported as an array literal separator.**</span></span>
- <span data-ttu-id="d5273-129">I due punti, `:`, vengono usati per introdurre un'annotazione di tipo</span><span class="sxs-lookup"><span data-stu-id="d5273-129">The colon, `:`, is used to introduce a type annotation.</span></span> <span data-ttu-id="d5273-130">e sono principalmente usati nelle firme chiamabili.</span><span class="sxs-lookup"><span data-stu-id="d5273-130">It is primarily used in callable signatures.</span></span>
  <span data-ttu-id="d5273-131">Poiché i due punti introducono sempre una firma del tipo, l'operatore condizionale ternario introdotto nella versione 0.3 usa una barra verticale, `|`, per separare i valori true e false. Di conseguenza, Q# usa `cond ? tval | fval` anziché i due punti come separatore, come in C.</span><span class="sxs-lookup"><span data-stu-id="d5273-131">Because colon always introduces a type signature, the ternary conditional operator introduced in 0.3 uses a vertical bar, `|`, to separate the true and false values; thus, Q# uses `cond ? tval | fval` instead of the colon as separator as in C.</span></span>
  
