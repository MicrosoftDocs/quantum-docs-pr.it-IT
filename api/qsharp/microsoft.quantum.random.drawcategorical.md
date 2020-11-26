---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operazione DrawCategorical
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: a5826aa5f658fea766db0ca5ccbb9c0d7d056d4c
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192996"
---
# <a name="drawcategorical-operation"></a>Operazione DrawCategorical

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Disegna un campione casuale da una distribuzione categorica specificata da un elenco di probablities.

```qsharp
operation DrawCategorical (probs : Double[]) : Int
```


## <a name="description"></a>Descrizione

La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice.
Gli elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti. Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.

## <a name="input"></a>Input

### <a name="probs--double"></a>Probe: [Double](xref:microsoft.quantum.lang-ref.double)[]

Matrice di numeri a virgola mobile proporzionale alla probabilità di selezione di ogni indice.



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

Numero intero $i $ con probabilità $ \Pr (i) = p_i/\ sum_i p_i $, dove $p _i $ è l'elemento $i $ th di `probs` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Random. CategoricalDistribution](xref:Microsoft.Quantum.Random.CategoricalDistribution)