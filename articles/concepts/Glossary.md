---
title: Glossario calcolo Quantum
description: Glossario dei termini, delle azioni e degli oggetti comuni usati in quantum computing.
author: QuantumWriter
ms.author: Alan.Geller@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.glossary
ms.openlocfilehash: f47d87f5bc9d677baa12a7ac1581af72894e8a4b
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909892"
---
# <a name="quantum-computing-glossary"></a>Glossario calcolo Quantum

|Termine|Definizione|
|-------------|----------|
|Adjoint|Traspone la complessa trasportazione dell'operazione. Per le operazioni che implementano un operatore unitario, l'elemento contiguo è l'inverso dell'operazione.|
|Callable|Operazioni e funzioni sono note collettivamente *richiamabili*.|
|Standard|Operazioni e funzioni definite in Q # che compilano la logica definita nel preludio. L'implementazione della libreria standard è indipendente rispetto ai computer di destinazione.|
|Gruppo Clifford|Set di operazioni che occupano il ottanti della sfera Bloch. Sono inclusi: `X`, `Y`, `Z`, `H` e `S`|
|Controllato|Operazione Quantum che accetta uno o più qubits come abilitatori per l'operazione di destinazione.|
|Notazione Dirac|Rappresentazione abbreviata dello stato quantum. Per ulteriori informazioni, vedere la sezione relativa alla [notazione di Dirac](xref:microsoft.quantum.concepts.dirac) .|
|Autovalori e autovettori|Per informazioni dettagliate, vedere la [sezione Advanced Matrix](xref:microsoft.quantum.concepts.matrix-advanced) .|
|Coppia EPR|Noto anche come [stato di campana](https://en.wikipedia.org/wiki/Bell_state)|
|Evoluzione|Modifica dello stato nel tempo. Per un esempio, vedere la sezione <xref:microsoft.quantum.concepts.matrix-advanced#matrix-exponentials>. |
|Funzione|Routine puramente classiche nel linguaggio Q #|
| <a id="global-phase"></a>Fase globale | Due stati identici a un multiplo di un numero complesso $e ^ {i\phi} $ si affermano come differenze fino a una fase globale. Diversamente dalle fasi locali, le fasi globali non possono essere osservate attraverso alcuna misurazione. Per altri dettagli, vedere le [misurazioni di Pauli](xref:microsoft.quantum.concepts.pauli) . |
|Misura|Ottenere un bit classico da un qubit (o un set di qubits). Per ulteriori informazioni, vedere la sezione Concetti relativi a [qubit](xref:microsoft.quantum.concepts.qubit) .|
|Modificabile|Variabile il cui valore può essere modificato dopo la creazione.|
|Spazio dei nomi|Etichetta per una raccolta di nomi correlati, in genere operazioni, funzioni e tipi. Ad esempio, lo spazio dei nomi [`Microsoft.Quantum.Preparation`](xref:microsoft.quantum.preparation) etichetta tutti i simboli definiti nella libreria standard che consentono di preparare gli stati iniziali.|
|Operazione|Unità di base dell'esecuzione del quantum in Q #. È approssimativamente equivalente a una funzione in C, C++ o Python oppure a un metodo statico in C# o Java.|
|Applicazione operator|Esecuzione di un'operazione Quantum. Viene in genere applicata una matrice unitaria al vettore di stato corrente. Per altri dettagli, vedere [Introduzione ai concetti quantistici](xref:microsoft.quantum.concepts.intro) .|
|Oracle|Subroutine che fornisce informazioni dipendenti dai dati a un algoritmo Quantum in fase di esecuzione. In genere, l'obiettivo è quello di fornire una superposizione degli output corrispondenti agli input in posizione superposizionata.   |
|Applicazione parziale|Chiamata di una funzione o di un'operazione senza tutti i parametri obbligatori. Restituisce un nuovo oggetto chiamabile che richiede solo i parametri mancanti forniti durante un'applicazione futura.|
|Operatori Pauli|I controlli Quantum `X`, `Y` e `Z`.|
|Preludio|Il set di operazioni primitive e classiche e funzioni definite da ogni singolo computer di destinazione, anziché a livello di Q #.|
|Circuito Quantum|Rappresentazione di un programma per un computer Quantum. Per ulteriori informazioni, vedere la sezione <xref:microsoft.quantum.concepts.circuits>.|
|Stato quantum|Rappresentazione di qubits nel sistema. Questa operazione viene in genere indicata come vettore di colonna complesso. Per altre informazioni, vedere <xref:microsoft.quantum.concepts.vectors>. |
|Qubit|Unità di archiviazione Quantum. Per ulteriori informazioni, vedere la sezione <xref:microsoft.quantum.concepts.qubit>.|
|Ripeti fino a-esito positivo|Algoritmo Quantum che ha esito positivo. In caso di errore, la routine verrà ritentata fino a quando non viene completata o è stato raggiunto un limite. |
|Computer di destinazione|Destinazione di compilazione che abbassa un programma Quantum astratto per l'hardware o la simulazione. Questo include in genere riscritture per molti scopi, tra cui la sostituzione del Gate, la codifica per la correzione degli errori, il layout geometrico e altro.|
|Tuple|Tipi delimitati da virgole raggruppati tramite parentesi. |
|Tipo definito dall'utente|Raccolta di tipi incorporati o definiti in precedenza a cui è possibile fare riferimento come singola unità.|

