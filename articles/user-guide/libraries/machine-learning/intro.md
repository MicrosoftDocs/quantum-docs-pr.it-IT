---
title: Libreria di apprendimento automatico quantistico
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 65b0aa6a7f385765933d4d89ce34901f77cf76ec
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863091"
---
# <a name="introduction-to-quantum-machine-learning"></a>Introduzione a Quantum Machine Learning

## <a name="framework-and-goals"></a>Framework e obiettivi

La codifica quantistica e l'elaborazione delle informazioni è una potente alternativa ai classificatori quantistici di Machine Learning classici. In particolare, consente di codificare i dati nei registri Quantum che sono concisi rispetto al numero di funzionalità, impiegando sistematicamente il groviglio Quantum come risorsa computazionale e impiegando la misurazione quantistica per l'inferenza della classe.
Il classificatore Quantum incentrato sul circuito è una soluzione Quantum relativamente semplice che combina la codifica dei dati con un circuito Quantum rapidamente impigliante/districare seguito dalla misurazione per dedurre le etichette di classe degli esempi di dati.
L'obiettivo è quello di garantire la caratterizzazione classica e l'archiviazione dei circuiti oggetto, nonché la formazione quantistica/classica ibrida dei parametri del circuito anche per spazi di funzioni estremamente grandi.

## <a name="classifier-architecture"></a>Architettura di classificazione

La classificazione è un'attività di Machine Learning supervisionata, in cui l'obiettivo è quello di dedurre le etichette delle classi $ \{ y_1, y_2, \ldots, y_d \} $ di determinati esempi di dati. Il "set di dati di training" è una raccolta di esempi $ \mathcal{D} = \{ (x, y)} $ con etichette preassegnate note. Qui $x $ è un campione di dati e $y $ è l'etichetta nota denominata "Training label".
In modo simile ai metodi tradizionali, la classificazione quantistica è costituita da tre passaggi:
- codifica dei dati
- preparazione dello stato di un classificatore
- misurazione a causa della natura probabilistica della misurazione, questi tre passaggi devono essere ripetuti più volte. Sia la codifica che l'elaborazione dello stato di classificazione vengono eseguite tramite *circuiti Quantum*. Mentre il circuito di codifica è in genere basato sui dati e senza parametri, il circuito di classificazione contiene un set sufficiente di parametri impensabili. 

Nella soluzione proposta il circuito di classificazione è costituito da rotazioni a qubit singolo e rotazioni controllate da due qubit. I parametri disponibili qui sono gli angoli di rotazione. La rotazione e la rotazione controllata sono note come *universali* per il calcolo quantistico, il che significa che qualsiasi matrice di peso unitario può essere scomposta in un circuito abbastanza lungo costituito da tali controlli.

Nella versione proposta è supportato un solo circuito seguito da una singola stima di frequenza.
Quindi, la soluzione è un analogo Quantum di una macchina a vettori di supporto con un kernel polinomiale di basso livello.

![Perceptron multistrato e classificatore incentrato sul circuito](~/media/DLvsQCC.png)

Una progettazione di classificazione quantistica semplice può essere confrontata con una soluzione SVM (Support Vector Machine) tradizionale. L'inferenza per un campione di dati $x $ nel caso di SVM viene eseguita usando un formato del kernel ottimale $ \sum \ alpha_j k (x_j, x) $ dove $k $ è una determinata funzione kernel.

Al contrario, un classificatore Quantum usa il predittore $p (y │ x, U (\theta)) = 〈 U (\theta) x | M | U (\theta) x 〉 $, che è simile allo spirito ma tecnicamente piuttosto diverso. Pertanto, quando viene utilizzata una codifica di ampiezza semplice, $p (y │ x, U (\theta)) $ è un formato quadratico nelle ampiezze di $x $, ma i coefficienti di questo form non vengono più appresi in modo indipendente; sono invece aggregati dagli elementi della matrice del circuito $U (\theta) $, che in genere presenta un numero significativamente inferiore di parametri riconoscibili $ \theta $ rispetto alla dimensione del vettore $x $. Il grado polinomiale di $p (y │ x, U (\theta)) $ nelle funzionalità originali può essere aumentato a $2 ^ l $ usando una codifica del prodotto Quantum su $l $ copie di $x $.

L'architettura Esplora i circuiti relativamente superficiali, che devono quindi essere *rapidamente coinvolti* per acquisire tutte le correlazioni tra le funzionalità dei dati in tutti gli intervalli. Nella figura seguente è illustrato un esempio del componente del circuito più utile. Anche se un circuito con questa geometria è costituito solo da $3 n + 1 $ Gates, la matrice di peso unitaria calcolata garantisce una significativa relazione tra le funzionalità di $2 ^ n $.

![Interessare rapidamente il circuito Quantum su 5 qubits (con due livelli ciclici).](~/media/5-qubit-qccc.png)

Il circuito nell'esempio precedente è costituito da 6 qubit di controllo singolo $ (G_1, \ldots, G_5; G_ {16} ) $ e 10 2-qubits Gates $ (G_6, \ldots, G_ {15} ) $. Supponendo che ogni controllo sia definito con un parametro riconoscibile, sono disponibili 16 parametri disponibili, mentre la dimensione dello spazio di Hilbert di 5 qubit è 32. Tale geometria del circuito può essere facilmente generalizzata in qualsiasi $n registro $-qubit, quando $n $ è dispari, producendo circuiti con $3 n + 1 $ parametri per lo spazio delle funzionalità $2 ^ n $-dimensional.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Training del classificatore come attività di apprendimento supervisionato

Il training di un modello di classificazione comporta l'individuazione di valori ottimali dei parametri operativi, in modo da massimizzare la probabilità media di dedurre le etichette di training corrette tra gli esempi di training.
In questo caso, ci occupiamo solo della classificazione a due livelli, ad esempio il caso di $d = $2 e solo due classi con le etichette $y _1, y_2 $.

> [!NOTE]
> Uno dei principi per generalizzare i metodi a un numero arbitrario di classi consiste nel sostituire qubits con qudits, ad esempio le unità Quantum con $d $ base States e la misurazione bidirezionale con $d misurazione $-Way.

### <a name="likelihood-as-the-training-goal"></a>Probabilità dell'obiettivo di training

Considerato un circuito Quantum $U (\theta) $, dove $ \theta $ è un vettore di parametri e indicante la misurazione finale per $M $, la probabilità media dell'inferenza dell'etichetta corretta è $ $ \begin{align} \mathcal{L} (\theta) = \frac {1} {| \mathcal{D} |} \left (\ Sum_ {(x, y_1) \In\mathcal{D}} P (M = y_1 | U (\theta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\theta) x) \right) \end{align} $ $ where $P (M = y | z) $ è la probabilità di misurare $y $ nello stato quantum $z $.
In questo caso è sufficiente comprendere che la funzione di probabilità $ \mathcal{L} (\theta) $ è smussata in $ \theta $ e il relativo derivato in qualsiasi $ \ theta_j $ può essere calcolato essenzialmente dallo stesso protocollo Quantum usato per calcolare la funzione di probabilità stessa. In questo modo è possibile ottimizzare $ \mathcal{L} (\theta) $ per Descent gradient.

### <a name="classifier-bias-and-training-score"></a>Distorsione del classificatore e Punteggio di training

Dato alcuni valori intermedi (o finali) dei parametri in $ \theta $, è necessario identificare un singolo valore reale $b $ know come bias di *classificazione* per eseguire l'inferenza. La regola di inferenza delle etichette funziona nel modo seguente: 
- A un esempio $x $ viene assegnata un'etichetta $y _2 $ if e solo se $P (M = y_2 | U (\theta) x) + b > $0,5 (RULE1). in caso contrario, viene assegnata l'etichetta $y _1 $)

Ovviamente $b $ deve essere compreso nell'intervallo $ (-0,5, + 0,5) $ per essere significativo.

Un case di training $ (x, y) \in \mathcal{D} $ è considerato una *classificazione errata* in base alla distorsione $b $ se l'etichetta dedotta per $x $ come per Rule1 è effettivamente diversa da $y $. Il numero complessivo di classificazioni non configurate è il *Punteggio di training* del classificatore data la distorsione $b $. La distorsione di classificazione *ottimale* $b $ riduce al minimo il Punteggio di training. È facile vedere che, date le stime di probabilità pre-calcolate $ \{ P (M = y_2 | U (\theta) x) | (x, *) \in\mathcal{D} \} $, la distorsione ottimale del classificatore è disponibile tramite ricerca binaria nell'intervallo $ (-0.5, + 0,5) $ facendo al massimo $ \ Log_2 (| \mathcal{D} |) $ Steps.

### <a name="reference"></a>Informazioni di riferimento

Queste informazioni dovrebbero essere sufficienti per iniziare a giocare con il codice. Tuttavia, per altre informazioni su questo modello, vedere la proposta originale: [ *"classificatori Quantum incentrati sul circuito", Maria Schuld, Alex Bocharov, Krysta Svore e Nathan Wiebe*](https://arxiv.org/abs/1804.00633)

Oltre all'esempio di codice visualizzato nei passaggi successivi, è anche possibile iniziare a esplorare la classificazione quantistica in [questa esercitazione](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/QuantumClassification) 
