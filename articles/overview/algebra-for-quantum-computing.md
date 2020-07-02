---
title: Algebra lineare per il calcolo quantistico
description: Informazioni sui concetti di base di algebra lineare necessari per comprendere il calcolo quantistico
author: bradben
ms.author: bradben
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.algebra
ms.openlocfilehash: 4cf6cce870c7661a7fffc21dcb60dd53cf281ddd
ms.sourcegitcommit: af10179284967bd7a72a52ae7e1c4da65c7d128d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "85415441"
---
# <a name="linear-algebra-for-quantum-computing"></a>Algebra lineare per il calcolo quantistico

Il linguaggio del calcolo quantistico è l'algebra lineare. Sebbene non sia necessario conoscerla per implementare o scrivere programmi quantistici, è ampiamente usata per descrivere gli stati dei qubit, le operazioni quantistiche e per prevedere ciò che un computer quantistico eseguirà in risposta a una sequenza di istruzioni.

Come la conoscenza dei [concetti di base della fisica quantistica](xref:microsoft.quantum.overview.understanding) può aiutare a comprendere il calcolo quantistico, alcune informazioni di algebra lineare di base consentono di comprendere il funzionamento degli algoritmi quantistici. Come minimo, è opportuno acquisire familiarità con **vettori** e **moltiplicazione di matrici**. Se è necessario aggiornare la conoscenza di questi concetti di algebra, di seguito sono riportate alcune esercitazioni sulle nozioni di base:

- [Esercitazione per Jupyter Notebook sull'algebra lineare](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/LinearAlgebra)
- [Esercitazione per Jupyter notebook sull'aritmetica complessa](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/ComplexArithmetic)
- [Algebra lineare per il calcolo quantistico](https://cds.cern.ch/record/1522001/files/978-1-4614-6336-8_BookBackMatter.pdf)
- [Nozioni fondamentali sull'algebra lineare](https://www.math.ubc.ca/~carrell/NB.pdf)
- [Guida introduttiva al calcolo quantistico](https://www.codeproject.com/Articles/5155638/Quantum-Computation-Primer-Part-1#exploring-quantum-superposition)

## <a name="vectors-and-matrices-in-quantum-computing"></a>Vettori e matrici nel calcolo quantistico

Nell'argomento [Informazioni sul calcolo quantistico](xref:microsoft.quantum.overview.understanding) è stato illustrato che un qubit può trovarsi in uno stato di 1 o 0 o di una sovrapposizione o entrambi. Usando l'algebra lineare, lo stato di un qubit viene descritto come vettore ed è rappresentato da una **matrice** a singola colonna $\begin{bmatrix} a \\\\ b \end{bmatrix}$. È noto anche come **vettore di stato quantistico** e deve soddisfare il requisito in base a cui $|a|^2 + |b|^2 = 1$.  

Gli elementi della matrice rappresentano la probabilità che il qubit collassi in un modo o nell'altro, dove $|a|^2$ è la probabilità di collassare in zero e $|b|^2$ è la probabilità di collassare in uno. Le matrici seguenti rappresentano tutte vettori di stato quantistico validi:

$$\begin{bmatrix} 1 \\\\  0 \end{bmatrix}, \begin{bmatrix} 0 \\\\  1 \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{1}{\sqrt{2}} \end{bmatrix}, \begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{-1}{\sqrt{2}} \end{bmatrix}, \text{ and }\begin{bmatrix} \frac{1}{\sqrt{2}} \\\\  \frac{i}{\sqrt{2}} \end{bmatrix}.$$

In [Computer e simulatori quantistici](xref:microsoft.quantum.overview.simulators) si è potuto inoltre osservare che le operazioni quantistiche vengono usate per modificare lo stato di un qubit.  Anche le operazioni quantistiche possono essere rappresentate da una matrice. Quando un'operazione quantistica viene applicata a un qubit, le due matrici che li rappresentano vengono moltiplicate e la risposta risultante rappresenta il nuovo stato del qubit dopo l'operazione.  

Di seguito sono riportate due operazioni quantistiche comuni rappresentate dalla moltiplicazione di matrici.


L'[operazione `X`](xref:microsoft.quantum.intrinsic.x) è rappresentata dalla matrice di Pauli $X$,

$$X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix},$$
    
e viene usata per capovolgere lo stato di un qubit da 0 a 1 (o viceversa), ad esempio

$$\begin{bmatrix}0 &1\\\\ 1 &0\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix} = \begin{bmatrix} 0 \\\\  1 \end{bmatrix}.$$

L'[operazione 'H'](xref:microsoft.quantum.intrinsic.h) è rappresentata dalla trasformazione di Hadamard $H$,

$$H = \dfrac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix},$$

 e colloca un qubit in uno stato di sovrapposizione in cui presenta pari probabilità di collassare in un modo o nell'altro, come illustrato qui

$$\frac{1}{\sqrt{2}}\begin{bmatrix}1 &1\\\\ 1 &-1\end{bmatrix}\begin{bmatrix} 1 \\\\  0 \end{bmatrix}=\frac{1}{\sqrt{2}}\begin{bmatrix} 1 \\\\  1 \end{bmatrix}=\left(\frac{1}{\sqrt{2}}\right)^2=\frac{1}{2}.$$

Una matrice che rappresenta un'operazione quantistica prevede un requisito, ovvero deve essere una matrice **unitaria**. Una matrice è unitaria se l'**inversa** della matrice è uguale alla **trasposta coniugata** della matrice.

## <a name="representing-two-qubit-states"></a>Rappresentazione di stati a due qubit

Negli esempi precedenti lo stato di un qubit è stato descritto con una matrice a singola colonna $\begin{bmatrix} a \\\\  b \end{bmatrix}$ e l'applicazione di un'operazione a esso è stata descritta moltiplicando le due matrici. Tuttavia, i computer quantistici usano più di un qubit, quindi come si descrive lo stato combinato di due qubit? 

Tenere presente che ogni qubit è uno spazio vettoriale, quindi non può essere semplicemente moltiplicato. Si usa invece un **prodotto tensoriale**, che è un'operazione correlata che crea un nuovo spazio vettoriale da singoli spazi vettoriali ed è rappresentato dal simbolo $\otimes$. Ad esempio, il prodotto tensoriale di due stati di qubit$\begin{bmatrix} a \\\\  b \end{bmatrix}$ e $\begin{bmatrix} c \\\\  d \end{bmatrix}$ viene calcolato

$$ \begin{bmatrix} a \\\\  b \end{bmatrix} \otimes \begin{bmatrix} c \\\\  d \end{bmatrix} =\begin{bmatrix} a \begin{bmatrix} c \\\\  d \end{bmatrix} \\\\ b \begin{bmatrix}c \\\\  d \end{bmatrix} \end{bmatrix} = \begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}. $$

Il risultato è una matrice quadridimensionale, con ogni elemento che rappresenta una probabilità. Ad esempio, $ac$ è la probabilità che i due qubit collassino in 0 e 0, $ad$ è la probabilità di 0 e 1 e così via. 

Esattamente come un singolo stato di qubit $\begin{bmatrix} a \\\\  b \end{bmatrix}$ deve soddisfare il requisito che $|a|^2 + |b|^2 = 1$ per rappresentare uno stato quantistico, uno stato a due qubit $\begin{bmatrix} ac \\\\  ad \\\\  bc \\\\  bd \end{bmatrix}$ deve soddisfare il requisito che $|ac|^2 + |ad|^2 + |bc|^2+ |bd|^2 = 1$.

## <a name="summary"></a>Summary

L'algebra lineare è il linguaggio standard per la descrizione del calcolo quantistico e della fisica quantistica. Anche se le [librerie](xref:microsoft.quantum.libraries) incluse nel kit di sviluppo Microsoft Quantum consentiranno di eseguire algoritmi quantistici avanzati senza approfondire i calcoli matematici sottostanti, la comprensione delle nozioni di base permetterà di iniziare più rapidamente e costituirà una solida base su cui costruire le competenze future.

## <a name="next-steps"></a>Passaggi successivi

[Installare QDK](xref:microsoft.quantum.install)
