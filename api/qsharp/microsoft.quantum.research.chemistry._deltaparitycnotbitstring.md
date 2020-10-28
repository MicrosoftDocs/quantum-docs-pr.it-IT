---
uid: Microsoft.Quantum.Research.Chemistry._DeltaParityCNOTbitstring
title: Funzione _DeltaParityCNOTbitstring
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: _DeltaParityCNOTbitstring
qsharp.summary: Classical processing step of `ApplyDeltaParity`. This computes a list of control qubits for evaluating parity difference between any two PQRS... terms of even length.
ms.openlocfilehash: 95b4c2df05f32cb937ec2cf421f43f2fdbf319da
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710853"
---
# <a name="_deltaparitycnotbitstring-function"></a>Funzione _DeltaParityCNOTbitstring

Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacchetto [](https://nuget.org/packages/)


Passaggio di elaborazione classico di `ApplyDeltaParity` .
Viene calcolato un elenco di qubits di controllo per la valutazione della differenza di parità tra due PQRS... termini di lunghezza pari.

```qsharp
function _DeltaParityCNOTbitstring (prevFermionicTerm : Int[], nextFermionicTerm : Int[]) : (Int, Bool[])
```


## <a name="input"></a>Input

### <a name="prevfermionicterm--int"></a>prevFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="nextfermionicterm--int"></a>nextFermionicTerm: [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--intbool"></a>Output: ([int](xref:microsoft.quantum.lang-ref.int),[bool](xref:microsoft.quantum.lang-ref.bool)[])



## <a name="remarks"></a>Commenti

Si presuppone che la lunghezza dei termini sia pari.
Calcola l'elenco di controlli per la differenza di parità tra due termini.
Si presuppone che gli elenchi di input siano ordinati in ordine crescente.