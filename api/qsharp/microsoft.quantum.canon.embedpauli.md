---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716201"
---
# <a name="embedpauli-function"></a>EmbedPauli (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Dato un operatore Pauli Single-qubit e l'indice di un qubit, restituisce un operatore Pauli a più qubit con l'operatore Single-qubit specificato in corrispondenza di tale indice e `PauliI` in corrispondenza di ogni altro indice.

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>Input

### <a name="pauli--pauli"></a>Pauli: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Operatore Pauli Single-qubit da inserire nella posizione specificata.


### <a name="location--int"></a>Località: [int](xref:microsoft.quantum.lang-ref.int)

Indice in modo che `output[location] == pauli` , dove `output` è l'output di questa funzione.


### <a name="n--int"></a>n: [int](xref:microsoft.quantum.lang-ref.int)

Lunghezza della matrice da restituire.



## <a name="output--pauli"></a>Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

