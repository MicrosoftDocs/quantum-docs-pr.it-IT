---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operazione MaybeChooseElement
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 1a69c8d5a6ae022ceda9269e17434b740809b107
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96192860"
---
# <a name="maybechooseelement-operation"></a>Operazione MaybeChooseElement

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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

