---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: e9042ca9eac4b8791057037dc5698eb14deadd31
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207038"
---
# <a name="embedpauli-function"></a>EmbedPauli (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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

