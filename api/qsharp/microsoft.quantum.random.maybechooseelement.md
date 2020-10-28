---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operazione MaybeChooseElement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 12640d9dc3aad301146eff7bcbbaae33d3ccd420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722169"
---
# <a name="maybechooseelement-operation"></a>Operazione MaybeChooseElement

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


Data una matrice di dati e una distribuzione sugli indici, tenta di scegliere un elemento in modo casuale.

```qsharp
operation MaybeChooseElement<'T> (data : 'T[], indexDistribution : Microsoft.Quantum.Random.DiscreteDistribution) : (Bool, 'T)
```


## <a name="input"></a>Input

### <a name="data--t"></a>dati:' t []

Matrice da cui scegliere un elemento.


### <a name="indexdistribution--discretedistribution"></a>indexDistribution: [DiscreteDistribution](xref:Microsoft.Quantum.Random.DiscreteDistribution)

Distribuzione sugli indici di `data` .



## <a name="output--boolt"></a>Output: ([bool](xref:microsoft.quantum.lang-ref.bool),' t)



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

