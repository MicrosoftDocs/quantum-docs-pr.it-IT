---
uid: Microsoft.Quantum.Random.DrawCategorical
title: Operazione DrawCategorical
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawCategorical
qsharp.summary: Draws a random sample from a categorical distribution specified by a list of probablities.
ms.openlocfilehash: fdc5ae3a9341cb11e8fda129bdd030289b6c99c2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720282"
---
# <a name="drawcategorical-operation"></a>Operazione DrawCategorical

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


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