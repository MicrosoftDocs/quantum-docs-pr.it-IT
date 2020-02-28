---
title: Libreria Quantum Machine Learning
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.introduction
ms.openlocfilehash: 4c42612fee3a58e15368677bb2c77a70c5680f45
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909790"
---
# <a name="introduction-to-quantum-machine-learning"></a>Introduzione a Quantum Machine Learning

## <a name="framework-and-goals"></a>Framework e obiettivi

La codifica quantistica e l'elaborazione delle informazioni è una potente alternativa ai classificatori quantistici di Machine Learning classici, in particolare codificare i dati nei registri Quantum che sono concisi rispetto al numero di funzionalità, impiegano sistematicamente i quantum l'intreccio come risorsa computazionale e usare la misurazione quantistica per l'inferenza della classe.
Il classificatore Quantum incentrato sul circuito è una soluzione Quantum relativamente semplice che combina la codifica dei dati con un circuito Quantum rapidamente impigliante/districare seguito dalla misurazione per dedurre le etichette di classe degli esempi di dati.
L'obiettivo è quello di garantire la caratterizzazione classica e l'archiviazione dei circuiti oggetto, nonché la formazione quantistica/classica ibrida dei parametri del circuito anche per spazi di funzioni estremamente grandi.

## <a name="classifier-architecture"></a>Architettura di classificazione

La classificazione è un'attività di Machine Learning supervisionata, in cui l'obiettivo è quello di dedurre le etichette delle classi $\{y_1, y_2, \ldots, y_d\}$ di alcuni esempi di dati. Il "set di dati di training" è una raccolta di esempi $ \mathcal{D} =\{(x, y)} $ con etichette preassegnate note. Qui $x $ è un campione di dati e $y $ è l'etichetta nota denominata "Training label".
In modo simile ai metodi tradizionali, la classificazione quantistica è costituita da tre passaggi:
- codifica dei dati
- preparazione dello stato di un classificatore
- misurazione a causa della natura probabilistica della misurazione, questi tre passaggi devono essere ripetuti più volte. La misura può essere considerata come un equivalente quantistico di attivazione non lineare.
Sia la codifica che l'elaborazione dello stato di classificazione vengono eseguite tramite *circuiti Quantum*. Mentre il circuito di codifica è in genere basato sui dati e senza parametri, il circuito di classificazione contiene un set sufficiente di parametri impensabili. 

Nella soluzione proposta il circuito di classificazione è costituito da rotazioni a qubit singolo e rotazioni controllate da due qubit. I parametri disponibili qui sono gli angoli di rotazione. La rotazione e la rotazione controllata sono note come *universali* per il calcolo quantistico, il che significa che qualsiasi matrice di peso unitario può essere scomposta in un circuito abbastanza lungo costituito da tali controlli.

![Perceptron multistrato e classificatore incentrato sul circuito](~/media/DLvsQCC.png)

È possibile confrontare questo modello con un perceptron multistrato per ottenere una migliore comprensione della struttura di base. In perceptron il predittore $p (y | x, \theta) $ è con parametri dal set di pesi $ \theta $ che determinano le funzioni lineari che connettono le funzioni di attivazione non lineari (neuroni). Questi parametri possono essere sottoposti a training per creare il modello. A livello di output è possibile ottenere la probabilità che un campione appartenga a una classe usando funzioni di attivazione non lineari come Softmax. Nel classificatore incentrato sul circuito il predittore è con parametri dagli angoli di rotazione delle rotazioni controllate da qubit e due qubit del circuito del modello. Analogamente, questi parametri possono essere sottoposti a training da una versione ibrida Quantum/classica dell'algoritmo di discesa sfumatura. Per calcolare l'output, anziché usare funzioni di attivazione non lineari, la probabilità della classe viene ottenuta leggendo misure ripetute su un qubit specifico dopo le rotazioni controllate. Per codificare i dati classici in uno stato quantico, viene usato un circuito di codifica controllabile per la preparazione dello stato.

L'architettura Esplora i circuiti relativamente superficiali, che devono quindi essere *rapidamente coinvolti* per acquisire tutte le correlazioni tra le funzionalità dei dati in tutti gli intervalli. Nella figura seguente è illustrato un esempio del componente del circuito più utile. Anche se un circuito con questa geometria è costituito solo da $3 n + 1 $ Gates, la matrice di peso unitaria calcolata garantisce una significativa relazione tra le funzionalità di $2 ^ n $.

![Interessare rapidamente il circuito Quantum su 5 qubits (con due livelli ciclici).](~/media/5-qubit-qccc.png)

Il circuito nell'esempio precedente è costituito da 6 qubit di controllo singolo $ (G_1, \ldots, G_5; G_{16}) $ e 10 2-qubits Gates $ (G_6, \ldots, G_{15}) $. Supponendo che ogni controllo sia definito con un parametro riconoscibile, sono disponibili 16 parametri disponibili, mentre la dimensione dello spazio di Hilbert di 5 qubit è 32. Tale geometria del circuito può essere facilmente generalizzata in qualsiasi $n registro $-qubit, quando $n $ è dispari, producendo circuiti con $3 n + 1 $ parametri per lo spazio delle funzionalità $2 ^ n $-dimensional.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Training del classificatore come attività di apprendimento supervisionato

Il training di un modello di classificazione comporta l'individuazione di valori ottimali dei parametri operativi, in modo da massimizzare la probabilità media di dedurre le etichette di training corrette tra gli esempi di training.
In questo caso, ci occupiamo solo della classificazione a due livelli, ad esempio il caso di $d = $2 e solo due classi con le etichette $y _1, y_2 $.

> [!NOTE]
> Uno dei principi per generalizzare i metodi a un numero arbitrario di classi consiste nel sostituire qubits con qudits, ad esempio le unità Quantum con $d $ base States e la misurazione bidirezionale con $d misurazione $-Way.

### <a name="likelihood-as-the-training-goal"></a>Probabilità dell'obiettivo di training

Considerato un circuito Quantum $U (\theta) $, dove $ \theta $ è un vettore di parametri e indicante la misurazione finale per $M $, la probabilità media dell'inferenza dell'etichetta corretta è $ $ \begin{align} \mathcal{L} (\theta) = \frac{1}{| \mathcal{D} |} \left (\ sum_ {(x, y_1) \in\mathcal{D}} P (M = y_1 | U (\theta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\theta) x) \right) \end{align} $ $ where $P (M = y | z) $ è la probabilità di misurare $y $ nello stato quantum $z $.
In questo caso è sufficiente comprendere che la funzione di probabilità $ \mathcal{L} (\theta) $ è smussata in $ \theta $ e il relativo derivato in qualsiasi $ \ theta_j $ può essere calcolato essenzialmente dallo stesso protocollo Quantum usato per calcolare la funzione di probabilità stessa. In questo modo è possibile ottimizzare $ \mathcal{L} (\theta) $ per Descent gradient.

### <a name="classifier-bias-and-training-score"></a>Distorsione del classificatore e Punteggio di training

Dato alcuni valori intermedi (o finali) dei parametri in $ \theta $, è necessario identificare un singolo valore reale $b $ know come bias di *classificazione* per eseguire l'inferenza. La regola di inferenza delle etichette funziona nel modo seguente: 
- A un esempio $x $ viene assegnata un'etichetta $y _2 $ if e solo se $P (M = y_2 | U (\theta) x) + b > $0,5 (RULE1). in caso contrario, viene assegnata l'etichetta $y _1 $)

Ovviamente $b $ deve essere compreso nell'intervallo $ (-0,5, + 0,5) $ per essere significativo.

Un case di training $ (x, y) \in \mathcal{D} $ è considerato una *classificazione errata* in base alla distorsione $b $ se l'etichetta dedotta per $x $ come per Rule1 è effettivamente diversa da $y $. Il numero complessivo di classificazioni non configurate è il *Punteggio di training* del classificatore data la distorsione $b $. La distorsione di classificazione *ottimale* $b $ riduce al minimo il Punteggio di training. È facile vedere che, date le stime di probabilità pre-calcolate $\{ P (M = y_2 | U (\theta) x) | (x, *) \in\mathcal{D} \}$, la distorsione ottimale del classificatore è disponibile nella ricerca binaria nell'intervallo $ (-0.5, + 0,5) $ facendo al massimo $ \ log_2 (| \mathcal{D} |) $ Steps.

### <a name="reference"></a>Riferimento

Queste informazioni dovrebbero essere sufficienti per iniziare a giocare con il codice. Tuttavia, per altre informazioni su questo modello, vedere la proposta originale: [ *"classificatori Quantum incentrati sul circuito", Maria Schuld, Alex Bocharov, Krysta Svore e Nathan Wiebe*](https://arxiv.org/abs/1804.00633)
