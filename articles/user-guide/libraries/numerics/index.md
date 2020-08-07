---
title: Introduzione alla libreria per il calcolo numerico quantistico | Microsoft Docs
description: Introduzione alla libreria per il calcolo numerico quantistico
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: article
uid: microsoft.quantum.numerics.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: dc6407d9775ad8a401036912abd0b70033796144
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868781"
---
# <a name="introduction-to-the-quantum-numerics-library"></a><span data-ttu-id="4ecfa-103">Introduzione alla libreria per il calcolo numerico quantistico</span><span class="sxs-lookup"><span data-stu-id="4ecfa-103">Introduction to the Quantum Numerics Library</span></span>

<span data-ttu-id="4ecfa-104">Molti algoritmi quantistici si basano su [oracoli](xref:microsoft.quantum.concepts.oracles) che valutano le funzioni matematiche in base a una sovrapposizione di input.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-104">Many quantum algorithms rely on [oracles](xref:microsoft.quantum.concepts.oracles) that evaluate mathematical functions on a superposition of inputs.</span></span>
<span data-ttu-id="4ecfa-105">Il componente principale dell'algoritmo di Shor, ad esempio, valuta $f(x) = a^x\operatorname{mod} N$ tale che $a$ è un numero fisso, $N$ il numero da fattorizzare e $x$ un numero intero da $2n$-qubit in una sovrapposizione uniforme su tutte le stringhe da $2n$-bit.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-105">The main component of Shor's algorithm, for example, evaluates $f(x) = a^x\operatorname{mod} N$ for a fixed $a$, the number to factor $N$, and $x$ a $2n$-qubit integer in a uniform superposition over all $2n$-bit strings.</span></span>

<span data-ttu-id="4ecfa-106">Per eseguire l'algoritmo di Shor in un computer quantistico reale, questa funzione deve essere scritta in termini di operazioni native del computer di destinazione.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-106">To run Shor's algorithm on an actual quantum computer, this function has to be written in terms of the native operations of the target machine.</span></span>
<span data-ttu-id="4ecfa-107">Usando la rappresentazione binaria di $x$ con $x_i$ indicante il bit $i$-esimo a partire dal bit meno significativo, $f(x)$ può essere scritta come $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-107">Using the binary representation of $x$ with $x_i$ denoting the $i$-th bit counting from the least-significant bit, $f(x)$ can be written as $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.</span></span>
<span data-ttu-id="4ecfa-108">A sua volta, questa formula può essere scritta come prodotto (mod N) di termini $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-108">In turn, this can be written as a product (mod N) of terms $a^{2^i x_i}=(a^{2^i})^{x_i}$.</span></span> <span data-ttu-id="4ecfa-109">È quindi possibile implementare la funzione $f(x)$ usando una sequenza di moltiplicazioni (modulari) $2n$ per $a^{2^i}$ a condizione che $x_i$ sia diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-109">The function $f(x)$ can thus be implemented using a sequence of $2n$ (modular) multiplications by $a^{2^i}$ conditional on $x_i$ being nonzero.</span></span> <span data-ttu-id="4ecfa-110">Le costanti $a^{2^i}$ possono essere precalcolate e ridotte del modulo N prima di eseguire l'algoritmo.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-110">The constants $a^{2^i}$ can be precomputed and reduced modulo N before running the algorithm.</span></span>

<span data-ttu-id="4ecfa-111">Questa sequenza di moltiplicazioni modulari controllate può essere ulteriormente semplificata. Ogni moltiplicazione può essere eseguita usando una sequenza di addizioni modulari controllate $n$, dove ogni addizione modulare può essere creata da un'addizione normale e un operatore di comparazione.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-111">This sequence of controlled modular multiplications can be simplified further: Each multiplication can be performed using a sequence of $n$ controlled modular additions; and each modular addition can be built from a regular addition and a comparator.</span></span>


<span data-ttu-id="4ecfa-112">Dal momento che sono necessari numerosi passaggi per giungere a una reale implementazione, è estremamente utile avere a disposizione queste funzionalità fin dall'inizio.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-112">Given that so many steps are necessary to arrive at an actual implementation, it would be extremely helpful to have such functionality available from the start.</span></span>
<span data-ttu-id="4ecfa-113">Per questo motivo, Quantum Development Kit fornisce il supporto per un'ampia gamma di funzionalità di calcolo numerico.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-113">This is why the Quantum Development Kit provides support for a wide range of numerics functionality.</span></span>


## <a name="functionality"></a><span data-ttu-id="4ecfa-114">Funzionalità</span><span class="sxs-lookup"><span data-stu-id="4ecfa-114">Functionality</span></span>

<span data-ttu-id="4ecfa-115">Oltre all'aritmetica degli interi citata finora, la libreria per il calcolo numerico fornisce:</span><span class="sxs-lookup"><span data-stu-id="4ecfa-115">Besides the integer arithmetic mentioned thus far, the numerics library provides</span></span>

- <span data-ttu-id="4ecfa-116">Funzionalità relative agli interi con o senza segno (moltiplicazione, quadrato, divisione con resto, inversione e così via) con uno o due numeri interi quantistici come input.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-116">(Un)signed integer functionality (multiply, square, division with remainder, inversion, ...) with one or two quantum integer numbers as input</span></span>
- <span data-ttu-id="4ecfa-117">Funzionalità relative ai numeri a virgola fissa (addizione/sottrazione, moltiplicazione, quadrato, 1/x, valutazione polinomiale) con uno o due numeri a virgola fissa quantistici come input.</span><span class="sxs-lookup"><span data-stu-id="4ecfa-117">Fixed-point functionality (add / subtract, multiply, square, 1/x, polynomial evaluation) with one or two quantum fixed-point numbers as input</span></span>

## <a name="getting-started"></a><span data-ttu-id="4ecfa-118">Introduzione</span><span class="sxs-lookup"><span data-stu-id="4ecfa-118">Getting started</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="4ecfa-119">Informazioni sull'uso della libreria per il calcolo numerico</span><span class="sxs-lookup"><span data-stu-id="4ecfa-119">Learn about using the numerics library</span></span>](xref:microsoft.quantum.numerics.usage)
