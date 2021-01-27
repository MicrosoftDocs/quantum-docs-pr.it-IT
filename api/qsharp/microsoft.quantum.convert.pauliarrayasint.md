---
uid: Microsoft.Quantum.Convert.PauliArrayAsInt
title: PauliArrayAsInt (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Convert
qsharp.name: PauliArrayAsInt
qsharp.summary: Encodes a multi-qubit Pauli operator represented as an array of single-qubit Pauli operators into an integer.
ms.openlocfilehash: 4c3c51813ef509fdc52773b15a956c0a99500603
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98832714"
---
# <a name="pauliarrayasint-function"></a>PauliArrayAsInt (funzione)

Spazio dei nomi: [Microsoft. Quantum. Convert](xref:Microsoft.Quantum.Convert)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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