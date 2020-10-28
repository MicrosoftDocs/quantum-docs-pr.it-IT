---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: f8ec468dd0f0cfd0d868dfc79ff715b3b4fc2f4a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92713373"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto [](https://nuget.org/packages/)


Codifica un operatore Pauli multiqubit rappresentato come una matrice di operatori Single-qubit Pauli in un intero.

```qsharp
function PauliArrayAsInt (paulis : Pauli[]) : Int
```


## <a name="input"></a>Input

### <a name="paulis--pauli"></a>Paulis: [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

Una matrice di al massimo 31 operatori di Pauli a qubit singola.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Intero che identifica in modo univoco `paulis` , come descritto di seguito.

## <a name="remarks"></a>Commenti

Ogni operatore di Pauli può essere codificato usando due bit: $ $ \begin{align} \boldone \mapsto 00, \quad X \mapsto 01, \quad Y \mapsto 11, \quad Z \mapsto 10.
\end{align} $ $

Data una matrice di operatori Pauli `[P0, ..., Pn]` , questa funzione restituisce un integer con espansione binaria formata concatenando i mapping di ogni operatore Pauli nell'ordine big-endian `bits(Pn) ... bits(P0)` .