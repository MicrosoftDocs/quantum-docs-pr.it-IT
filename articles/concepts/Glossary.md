---
title: Glossario dell'informatica quantistica
description: Un glossario di termini, azioni e oggetti comuni utilizzati nell'informatica quantistica.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: ee78515a0f47730b7d3df10da0853c5b8a7f6624
ms.sourcegitcommit: 7d350db4b5e766cd243633aee7d0a839b6274bd6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "81482213"
---
# <a name="quantum-computing-glossary"></a>Glossario dell'informatica quantistica

## <a name="adjoint"></a>Adiacente

La complessa trasposizione coniugata di [un'operazione](xref:microsoft.quantum.glossary#operation). Per le operazioni che implementano un operatore [unitario,](xref:microsoft.quantum.glossary#unitary-operator) l'adiacente è l'inverso dell'operazione ed è indicato da un simbolo del pugnale. Se, ad esempio, l'operazione rappresenta l'operatore `U` unitario $U, rappresenta `Adjoint U` $U. Per ulteriori informazioni, vedere [Adjoint](xref:microsoft.quantum.language.file-structure#adjoint).

## <a name="ancilla"></a>Ancilla

Un [qubit](xref:microsoft.quantum.glossary#qubit) che funge da memoria temporanea per un computer quantistico e viene allocato e deallocato in base alle esigenze.  Per ulteriori informazioni, consultate [Qubit multipli](xref:microsoft.quantum.concepts.multiple-qubits).

## <a name="bell-state"></a>Stato Bell

Uno dei quattro [stati quantici](xref:microsoft.quantum.glossary#quantum-state) specifici che si [implascano](xref:microsoft.quantum.glossary#entanglement) al massimo di due qubit. I quattro stati sono definiti beta_ , beta_ , ij , ( , mathbb , I , Otimes{00} X ,{11}i , j{2}) , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , , Uno stato Bell è noto anche come [coppia EPR](xref:microsoft.quantum.glossary#epr-pair).

## <a name="bloch-sphere"></a>Sfera di Bloch

Rappresentazione grafica di uno [stato quantico](xref:microsoft.quantum.glossary#quantum-state) a singolo[qubit](xref:microsoft.quantum.glossary#qubit) come punto in una sfera di unità tridimensionale. Per ulteriori informazioni, consultate [Visualizzazione di Qubit e trasformazioni mediante la sfera Bloch](xref:microsoft.quantum.concepts.qubit#visualizing-qubits-and-transformations-using-the-bloch-sphere).

## <a name="callable"></a>Callable

[Un'operazione](xref:microsoft.quantum.glossary#operation) o una [funzione](xref:microsoft.quantum.glossary#function) nel linguaggio Q. Per ulteriori informazioni, vedere [Tipi di operazione e funzione](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="clifford-group"></a>Gruppo Clifford

Insieme di operazioni che occupano gli ottanti della [sfera Bloch](xref:microsoft.quantum.glossary#bloch-sphere) e le permutazioni degli effetti degli [operatori Pauli](xref:microsoft.quantum.glossary#pauli-operators). Tra queste sono le operazioni [$X](xref:microsoft.quantum.intrinsic.x), [$Y](xref:microsoft.quantum.intrinsic.y) [, $Z](xref:microsoft.quantum.intrinsic.z), [$H](xref:microsoft.quantum.intrinsic.h) e [$S](xref:microsoft.quantum.intrinsic.s).

## <a name="controlled"></a>Controllato

Operazione [quantistica](xref:microsoft.quantum.glossary#operation) che accetta uno o più [qubit](xref:microsoft.quantum.glossary#qubit) come attivatori per l'operazione di destinazione. Per ulteriori informazioni, vedere [Controllato](xref:microsoft.quantum.language.type-model#controlled).

## <a name="dirac-notation"></a>Notazione Dirac

Una scorciatoia simbolica che semplifica la rappresentazione degli [stati quantistici,](xref:microsoft.quantum.glossary#quantum-state)detta anche notazione *bra-ket.*  La parte del *reggiseno* rappresenta un vettore di riga, ad esempio " sbra " , A , "A" , "inizio" 1A , A , _1 , & A , _2 \\ \\ , "end" e *"ket"* e la parte di ket rappresenta un vettore di colonna, "ket" B " " . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . . Per ulteriori informazioni, vedere [Dirac Notation](xref:microsoft.quantum.concepts.dirac).

## <a name="eigenvalue"></a>Autovalore

Il fattore con cui la grandezza di un [eigenvector](xref:microsoft.quantum.glossary#eigenvector) di una determinata trasformazione viene modificato dall'applicazione della trasformazione.  Data una matrice quadrata $M e un eigenvector $v, quindi $Mv , dove $c è l'eigenvalue e può essere un numero complesso di qualsiasi argomento. Per ulteriori informazioni, consultate [Concetti di matrici avanzate.](xref:microsoft.quantum.concepts.matrix-advanced)

## <a name="eigenvector"></a>Eigenvector

Vettore la cui direzione è invariata da una determinata trasformazione e la cui grandezza viene modificata da un fattore corrispondente [all'eigenvalue](xref:microsoft.quantum.glossary#eigenvalue)di tale vettore. Data una matrice quadrata $M e un eigenvalue $c, quindi $Mv , dove $v è un eigenvector della matrice e può essere un numero complesso di qualsiasi argomento. Per ulteriori informazioni, consultate [Concetti di matrici avanzate.](xref:microsoft.quantum.concepts.matrix-advanced)

## <a name="entanglement"></a>Entanglement

Le particelle quantistiche, come [i qubit,](xref:microsoft.quantum.glossary#qubit)possono essere collegate o *impigliate* in modo che non possano essere descritte indipendentemente l'una dall'altra. I loro risultati di misurazione sono correlati anche quando sono separati infinitamente lontani. L'intrappolamento è essenziale per [misurare](xref:microsoft.quantum.glossary#measurement) [lo stato](xref:microsoft.quantum.glossary#quantum-state) di un qubit.  Per ulteriori informazioni, consultate [Concetti di matrici avanzate.](xref:microsoft.quantum.concepts.matrix-advanced)

## <a name="epr-pair"></a>Coppia EPR

Uno dei quattro [stati quantici](xref:microsoft.quantum.glossary#quantum-state) specifici per massimo intrecciati di due [qubit](xref:microsoft.quantum.glossary#qubit). I quattro stati sono definiti, ovvero il valore di beta_,{1} l'ideJ, ovvero il valore di{00} "mathbb" ("mathbb", "otimes X"i", j") /"sqrt".{11}{2} Una coppia EPR è anche nota come [stato Bell](xref:microsoft.quantum.glossary#bell-state)

## <a name="evolution"></a>Evoluzione

Come cambia [uno stato quantistico](xref:microsoft.quantum.glossary#quantum-state) nel tempo. Per ulteriori informazioni, vedere [Esponenziali di matrici](xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials).

## <a name="function"></a>Funzione
Un tipo di subroutine nel linguaggio Q , che è puramente classico (non-quantum). Mentre le funzioni vengono utilizzate all'interno di algoritmi quantistici, non possono agire sui [qubit](xref:microsoft.quantum.glossary#qubit) o sulle [operazioni](xref:microsoft.quantum.glossary#operation)di chiamata. Per ulteriori informazioni, vedere [Tipi di operazione e funzione](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="gate"></a>Cancello

Termine legacy per [un'operazione](xref:microsoft.quantum.glossary#operation)quantistica, basato sul concetto di porte logiche classiche. Un [circuito quantistico](xref:microsoft.quantum.glossary#quantum-circuit-diagram) è una rete di porte (o operazioni), basate sul concetto simile di circuiti logici classici.

## <a name="global-phase"></a>Fase globale

Quando due [stati](xref:microsoft.quantum.glossary#quantum-state) sono identici a un multiplo di un numero complesso $e, ovvero "i", si dice che differiscano fino a una fase globale. A differenza delle fasi locali, le fasi globali non possono essere osservate attraverso [alcuna misura.](xref:microsoft.quantum.glossary#measurement) Per ulteriori informazioni, vedere [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="hadamard"></a>Hadamard

L'operazione Hadamard (nota anche come porta o trasformazione di Hadamard) agisce su un singolo [qubit](xref:microsoft.quantum.glossary#qubit) e{1}la mette in una [sovrapposizione](xref:microsoft.quantum.glossary#superposition) uniforme di{0}.{0} In Q, questa operazione viene applicata [`H`](xref:microsoft.quantum.intrinsic.h) dall'operazione predefinita.

## <a name="immutable"></a>Non modificabile

Variabile il cui valore non può essere modificato. Viene creata una variabile non modificabile `let` in Q , usando la parola chiave . Per dichiarare le variabili che *possono* essere modificate, `set` utilizzare la parola chiave [mutable](xref:microsoft.quantum.glossary#immutable) per dichiarare e la parola chiave per modificare il valore. 

## <a name="measurement"></a>Misura

Manipolazione di un [qubit](xref:microsoft.quantum.glossary#qubit) (o set di qubit) che produce il risultato di un'osservazione, ottenendo in effetti un bit classico. Per ulteriori informazioni, vedere [Qubit](xref:microsoft.quantum.concepts.qubit#measuring-a-qubit).

## <a name="mutable"></a>Modificabile

Variabile il cui valore può essere modificato dopo la creazione. Una variabile modificabile in Q `mutable` , viene dichiarata `set` utilizzando la parola chiave e modificata utilizzando la parola chiave . Le variabili `let` create con la parola chiave non sono [modificabili](xref:microsoft.quantum.glossary#immutable) e il relativo valore non può essere modificato.

## <a name="namespace"></a>Spazio dei nomi

Etichetta per un insieme di nomi correlati (ad esempio, [operazioni,](xref:microsoft.quantum.glossary#operation) [funzioni](xref:microsoft.quantum.glossary#function)e [tipi definiti dall'utente).](xref:microsoft.quantum.glossary#user-defined-type) Ad esempio, lo spazio dei nomi [Microsoft.Quantum.Preparation](xref:microsoft.quantum.preparation) etichetta tutti i simboli definiti nella libreria standard che consentono di preparare gli stati iniziali.

## <a name="operation"></a>Operazione

L'unità di base dell'esecuzione quantistica in Q. È all'incirca equivalente a una funzione in C, C , o Python, o un metodo statico in C , o Java. Per ulteriori informazioni, vedere [Tipi di operazione e funzione](xref:microsoft.quantum.language.type-model#operation-and-function-types).

## <a name="operator-application"></a>Applicazione operatore

Esecuzione di un'operazione quantistica. Questo in genere applica una matrice unitaria al vettore di stato quantistico corrente.

## <a name="oracle"></a>Oracle

Subroutine che fornisce informazioni dipendenti dai dati a un algoritmo quantistico in fase di esecuzione. In genere, l'obiettivo è fornire una [sovrapposizione](xref:microsoft.quantum.glossary#superposition) degli output corrispondenti agli input che si trovano nella sovrapposizione. Per ulteriori informazioni, vedere [Oracles](xref:microsoft.quantum.libraries.data-structures#oracles).

## <a name="partial-application"></a>Applicazione parziale

Chiamata di una [funzione](xref:microsoft.quantum.glossary#function) o [un'operazione](xref:microsoft.quantum.glossary#operation) senza tutti gli input necessari. Restituisce un nuovo [oggetto richiamabile](xref:microsoft.quantum.glossary#callable) che richiede solo i parametri mancanti (indicati da un carattere di sottolineatura) da fornire durante un'applicazione futura. Ad esempio, data `MyFunc(x : int, y : int) : int {return x + y;}` la funzione, è possibile `let NewFunc = MyFunc(_, 3)`applicarla parzialmente a una nuova funzione . È quindi possibile chiamare la nuova funzione in `NewFunc(2)` un secondo momento con il parametro mancante che restituisce il valore *5*.  Per ulteriori informazioni, vedere [Applicazione parziale](xref:microsoft.quantum.language.expressions#partial-application).

## <a name="pauli-operators"></a>Operatori Pauli

Un insieme di tre matrici unitari 2 `X` `Y` x `Z` 2 note come operazioni e quantistiche . La matrice di identità, $I, è spesso inclusa anche nel set.  $I $I, iniziate, & \\ \\ & 0 0 0, & 1' fine' bmatrix, $X \\ \\ , $X, $X, $X, $X, & 1 & 0, \\ \\ ovvero a ,end, bmatrix, $Y , $Y , & \\ \\ -i & 0, fine, bmatrix, $Z & & $Z .   Per ulteriori informazioni, consultate [Operazioni a ciclo singolo](xref:microsoft.quantum.concepts.qubit#single-qubit-operations).

## <a name="quantum-circuit-diagram"></a>Diagramma del circuito quantistico

Metodo per rappresentare graficamente la sequenza di [operazioni](xref:microsoft.quantum.glossary#operation) (o ![ [gate)](xref:microsoft.quantum.glossary#gate)per programmi quantistici semplici, ad esempio Schema di circuiti di esempio .](~/media/qpe.png) Per ulteriori informazioni, vedere [Circuiti quantistici](xref:microsoft.quantum.concepts.circuits).

## <a name="quantum-libraries"></a>Librerie quantistiche

Raccolte di [operazioni,](xref:microsoft.quantum.glossary#operation) [funzioni](xref:microsoft.quantum.glossary#function) e [tipi definiti dall'utente](xref:microsoft.quantum.glossary#user-defined-type) per la creazione di programmi Q. La [libreria Standard](xref:microsoft.quantum.libraries.standard.intro) viene installata per impostazione predefinita. Altre librerie disponibili sono la [libreria Chimica](xref:microsoft.quantum.chemistry.concepts.intro), la [libreria Numerics](xref:microsoft.quantum.numerics.intro) e la [libreria Machine Learning](xref:microsoft.quantum.machine-learning.concepts.intro).

## <a name="quantum-state"></a>Stato quantico

Lo stato preciso di un sistema quantistico isolato, da cui è possibile estrarre le probabilità di [misurazione.](xref:microsoft.quantum.glossary#measurement) Nell'informatica quantistica, il simulatore quantistico utilizza queste informazioni per simulare il modo in cui i qubit rispondono alle operazioni. Per ulteriori informazioni, vedere [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="qubit"></a>Qubit

Un'unità di base di informazioni quantistiche, analoga a un *po'* nell'informatica classica. Per ulteriori informazioni, vedere [Qubit](xref:microsoft.quantum.concepts.qubit).

## <a name="repeat-until-success"></a>Ripetizione fino al successo

Un algoritmo quantistico che probabilisticamente ha successo. In caso di errore, la routine tenterà di ripetere fino a quando non ha esito positivo (o non è stato raggiunto un limite). Per ulteriori informazioni, vedere [Ripeti fino al successo (RUS)](xref:microsoft.quantum.techniques.qubits#measurements)

## <a name="standard-libraries"></a>Librerie standard

[Operazioni](xref:microsoft.quantum.glossary#operation), [funzioni](xref:microsoft.quantum.glossary#function) e [tipi definiti dall'utente](xref:microsoft.quantum.glossary#user-defined-type) che vengono installati insieme al compilatore Q , durante l'installazione. L'implementazione della libreria standard è agnostica rispetto alle macchine di destinazione. Per ulteriori informazioni, consultate [Librerie standard.](xref:microsoft.quantum.libraries.standard.intro)

## <a name="superposition"></a>Sovrapposizione

Il concetto nel calcolo quantistico che un [qubit](xref:microsoft.quantum.glossary#qubit) è una combinazione lineare di due stati, ovvero "ket" e "ket" e "ket" (fotogramma) e "1", finché non viene [misurato.](xref:microsoft.quantum.glossary#measurement)  Per ulteriori informazioni, consultate [Che cos'è l'informatica quantistica.](xref:microsoft.quantum.overview.what)

## <a name="target-machine"></a>Macchina di destinazione

Un obiettivo di compilazione che abbassa un programma quantistico astratto verso l'hardware o la simulazione. Questo include in genere riscritture per molti scopi, tra cui la sostituzione del gate, la codifica per la correzione degli errori, il layout geometrico e altri. Per ulteriori informazioni, consultate [Simulatori quantistici e applicazioni host.](xref:microsoft.quantum.machines)

## <a name="teleportation"></a>Teletrasporto

Metodo per rigenerare i dati, o [lo stato quantistico](xref:microsoft.quantum.glossary#quantum-state), di un [qubit](xref:microsoft.quantum.glossary#qubit) da un luogo all'altro senza spostare fisicamente il qubit, utilizzando [l'entanglement](xref:microsoft.quantum.glossary#entanglement) e [la misurazione.](xref:microsoft.quantum.glossary#measurement)  Per ulteriori informazioni, vedere [Circuiti quantici](xref:microsoft.quantum.concepts.circuits) e [Mettere tutto insieme.](xref:microsoft.quantum.techniques.puttingittogether)

## <a name="tuple"></a>Tupla

Raccolta di valori delimitati da virgole che funge da singolo valore. Il *tipo* di una tupla è definito dai tipi di valori che contiene. In Q, le tuple non sono [modificabili](xref:microsoft.quantum.glossary#immutable) e possono essere annidate, contengono matrici o utilizzate in una matrice. Per ulteriori informazioni, vedere [Tipi di tupla](xref:microsoft.quantum.language.type-model#tuple-types).

## <a name="unitary-operator"></a>Operatore unitario

Un operatore il cui inverso è uguale al relativo [adjoint](xref:microsoft.quantum.glossary#adjoint), vale a dire, $UU, il pugnale, ovvero il pugnale, ovvero l'id.

## <a name="user-defined-type"></a>Tipo definito dall'utente

Raccolta di tipi predefiniti o definiti in precedenza che possono essere definiti come una singola unità. Per ulteriori informazioni, vedere [Tipi definiti dall'utente](xref:microsoft.quantum.language.type-model#user-defined-types).