---
title: Introduzione alla libreria per il calcolo numerico quantistico | Microsoft Docs
description: Introduzione alla libreria per il calcolo numerico quantistico
author: thomashaener
ms.author: thhaner
ms.date: 5/14/2019
ms.topic: conceptual
uid: microsoft.quantum.numerics.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 017fd075596e7b5fb7107d3bc5f149b77dc4e504
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854015"
---
# <a name="introduction-to-the-quantum-numerics-library"></a>Introduzione alla libreria per il calcolo numerico quantistico

Molti algoritmi quantistici si basano su [oracoli](xref:microsoft.quantum.concepts.oracles) che valutano le funzioni matematiche in base a una sovrapposizione di input.
Il componente principale dell'algoritmo di Shor, ad esempio, valuta $f(x) = a^x\operatorname{mod} N$ tale che $a$ è un numero fisso, $N$ il numero da fattorizzare e $x$ un numero intero da $2n$-qubit in una sovrapposizione uniforme su tutte le stringhe da $2n$-bit.

Per eseguire l'algoritmo di Shor in un computer quantistico reale, questa funzione deve essere scritta in termini di operazioni native del computer di destinazione.
Usando la rappresentazione binaria di $x$ con $x_i$ indicante il bit $i$-esimo a partire dal bit meno significativo, $f(x)$ può essere scritta come $f(x) = a^{\sum_{i=0}^{2n-1} x_i 2^i} \operatorname{mod} N$.
A sua volta, questa formula può essere scritta come prodotto (mod N) di termini $a^{2^i x_i}=(a^{2^i})^{x_i}$. È quindi possibile implementare la funzione $f(x)$ usando una sequenza di moltiplicazioni (modulari) $2n$ per $a^{2^i}$ a condizione che $x_i$ sia diverso da zero. Le costanti $a^{2^i}$ possono essere precalcolate e ridotte del modulo N prima di eseguire l'algoritmo.

Questa sequenza di moltiplicazioni modulari controllate può essere ulteriormente semplificata. Ogni moltiplicazione può essere eseguita usando una sequenza di addizioni modulari controllate $n$, dove ogni addizione modulare può essere creata da un'addizione normale e un operatore di comparazione.


Dal momento che sono necessari numerosi passaggi per giungere a una reale implementazione, è estremamente utile avere a disposizione queste funzionalità fin dall'inizio.
Per questo motivo, Quantum Development Kit fornisce il supporto per un'ampia gamma di funzionalità di calcolo numerico.


## <a name="functionality"></a>Funzionalità

Oltre all'aritmetica degli interi citata finora, la libreria per il calcolo numerico fornisce:

- Funzionalità relative agli interi con o senza segno (moltiplicazione, quadrato, divisione con resto, inversione e così via) con uno o due numeri interi quantistici come input.
- Funzionalità relative ai numeri a virgola fissa (addizione/sottrazione, moltiplicazione, quadrato, 1/x, valutazione polinomiale) con uno o due numeri a virgola fissa quantistici come input.

## <a name="getting-started"></a>Introduzione

> [!div class="nextstepaction"]
> [Informazioni sull'uso della libreria per il calcolo numerico](xref:microsoft.quantum.numerics.usage)
