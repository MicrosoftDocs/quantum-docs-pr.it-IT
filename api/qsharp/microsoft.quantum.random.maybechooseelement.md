---
uid: Microsoft.Quantum.Random.MaybeChooseElement
title: Operazione MaybeChooseElement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: MaybeChooseElement
qsharp.summary: Given an array of data and an a distribution over its indices, attempts to choose an element at random.
ms.openlocfilehash: 86a69110fc92a2b6238cc757c09185c9fbcdb035
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856123"
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



## <a name="example"></a>Esempio

Il frammento di codice Q # seguente sceglie un elemento in modo casuale da una matrice:

```qsharp
let (succeeded, element) = MaybeChooseElement(
    data,
    DiscreteUniformDistribution(0, Length(data) - 1)
);
Fact(succeeded, "Index chosen by MaybeChooseElement was not valid.");
```