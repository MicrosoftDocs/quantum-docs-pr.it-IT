---
title: Modelli Quantum per sistemi elettronici
description: Informazioni sul modo in cui i sistemi elettronici molecolari vengono simulati usando la modellazione quantistica.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 9f9fc37944dd76026c2641d9cdf126e71053a598
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904418"
---
# <a name="quantum-models-for-electronic-systems"></a>Modelli Quantum per sistemi elettronici

Per simulare i sistemi elettronici, è necessario innanzitutto specificare l'hamiltoniana, che è possibile trovare nella procedura di quantizzazione canonica descritta in precedenza.
In particolare, per $N _e $ Electrons con momenta $p _i $ (in tre dimensioni) e di massa $m _E $ e position vectors $x _i $ insieme ai nuclei con addebiti $Z _K e $ nelle posizioni $y _k $, l'operatore Hamiltoniana legge \begin{Equation} \hat{H} = \sum\_{i = 1} ^ {N\_e} \frac{\hat{p}\_i ^ 2} {2m\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e ^ 2} {| \hat{x}\_i-\hat{x}\_j |}-\sum\_{i , k} \frac{Z\_ke ^ 2} {| \hat{x}\_i-{y}\_k |} + \frac{1}{2} \ sum_ {k\ne k '} \frac{Z\_kZ\_{k '} e ^ 2} {| y\_k-y\_k ' |}. \label{EQ: Ham} \end{Equation} gli operatori momenta $ \hat{p}\_i ^ 2 $ possono essere visualizzati nello spazio reale come operatori laplaciano, ad esempio $ \hat{p}\_i ^ 2 =-\partial\_{x\_i} ^ 2-\partial\_{y\_i} ^ 2-\partial\_{z\_i} ^ 2 $.
In questo esempio è stato creato il presupposto semplificato che i nuclei sono inattivi per la molecola.
Questa operazione è nota come approssimazione del Born-Oppenheimer e tende a essere valida per lo spettro energetico a basso consumo di $ \hat{H} $ poiché la massa degli elettroni è circa $1/1836 $ la massa di un protone.
Questo operatore Hamiltoniana può essere facilmente individuato scrivendo l'energia per un sistema di $N\_e $ elettroni e applicando il processo di quantizzazione canonico descritto in [Quantum Dynamics](xref:microsoft.quantum.chemistry.concepts.quantumdynamics).

Per costruire la rappresentazione della matrice unitaria per $e ^ {-i\hat {H} t} $, è necessario rappresentare l'operatore $ \hat{H} $ come matrice.
A tale proposito, è necessario scegliere un sistema di coordinate o una base per rappresentare il problema in.
Se ad esempio $ \ psi_j $ sono un set di funzioni di base ortogonali per il $N _e $ Electrons, è possibile definire la matrice

\begin{Equation} H\_{i, j} = \int\_{-\infty} ^ \infty\int\_{-\infty} ^ \infty \psi ^ {\*}\_i (x\_1) \hat{H} \psi\_j (x\_2) \dd ^ 3x\_1 \dd ^ 3x\_2. \ etichetta {EQ: discreteHam} \end{Equation}

Anche se, in linea di principio, l'operatore $ \hat{H} $ non è associato e non agisce su uno spazio dimensionale finito, la matrice con gli elementi $H\_\{i, j\}$ sopra.
Questo significa che gli errori vengono generati selezionando troppo piccolo di un set di basi; Tuttavia, la scelta di una grande base può rendere la simulazione della dinamica chimica non praticabile.
Per questo motivo, la scelta di una base in grado di rappresentare brevemente il problema è essenziale per la risoluzione del problema di struttura elettronica.

Esistono molte basi appropriate che è possibile usare e la scelta di una buona base per adattarsi al problema è la maggior parte dell'arte della chimica quantistica.
Probabilmente i set di base più semplici sono le soluzioni di tipo Slater-Type-Orbits (con ortogonalità) all'equazione Schrödinger (ovvero autofunzioni di $ \hat{H} $) per gli atomi simili a idrogeno.
È possibile usare altri set di base, ad esempio le fluttuazioni del piano o gli orbitali spaziali reali, e per informazioni più dettagliate si fa riferimento al lettore curioso al testo standard ["Molecular Electronic-Structure Theory"](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) di Helgaker.

Anche se gli stati usati nel modello precedente possono sembrare arbitrari, i meccanici quantistici inseriscono restrizioni sugli Stati che è possibile trovare nella natura.
In particolare, tutti gli Stati del quantum elettronico validi devono essere anti-simmetrico in scambio di etichette elettrone.
Ovvero, se $ \psi (x_1, x_2) $ era la funzione Wave per lo stato del quantum comune di due elettroni, è necessario che $ $ \psi (x_1, x_2) =-\psi (x_2, x_1).
$ $ Il principio di esclusione di Pauli che impedisce a due elettroni di trovarsi nello stesso stato del quantum è, in modo affascinante, una conseguenza diretta di questa legge, come si può intuire dal fatto che se si scambiano due elettroni situati nella stessa posizione $ \psi (x_1, x_1) \mapsto \psi ( x_1, x_1) \ne-\psi (x_1, x_1) $ a meno che $ \psi (x_1, x_1) = 0 $.
Pertanto, è necessario scegliere gli stati iniziali per rispettare questa proprietà anti-simmetria e che a loro volta non hanno mai due elettroni nello stesso stato.
Questo è fondamentale per la struttura elettronica perché impedisce a più elettroni di trovarsi nello stesso stato e, a sua volta, consente ai computer Quantum di usare un singolo bit Quantum per archiviare il numero di elettroni in uno stato quantico specifico.

Sebbene la meccanica quantistica possa essere simulata in un computer Quantum discretizzazione questi Stati, la maggior parte del lavoro nel campo ha evitato questo approccio, perché richiede molti qubits per archiviare gli Stati ed è necessaria una procedura di preparazione dello stato complessa per preparare un stato iniziale anti-simmetrico.
Fortunatamente, tuttavia, questi problemi possono essere eluso visualizzando il problema di simulazione da un'altra prospettiva.
