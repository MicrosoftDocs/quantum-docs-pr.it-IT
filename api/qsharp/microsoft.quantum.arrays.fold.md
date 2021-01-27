---
uid: Microsoft.Quantum.Arrays.Fold
title: Funzione fold
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: d12e070058178ce2cbdd70cade5bc16607a55d5e
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848600"
---
# <a name="fold-function"></a>Funzione fold

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Scorre una funzione `f` tramite una matrice `array` , restituendo `f(f(f(initialState, array[0]), array[1]), ...)` .

```qsharp
function Fold<'State, 'T> (folder : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State
```


## <a name="input"></a>Input

### <a name="folder--statet---state"></a>cartella: (' stato,' non)-stato >'

Funzione da ripiegare sulla matrice.


### <a name="state--state"></a>stato:' stato

Stato iniziale della cartella.


### <a name="array--t"></a>matrice:' t []

Matrice di valori da ripiegare.



## <a name="output--state"></a>Output:' stato

Stato finale restituito dalla cartella dopo l'iterazione su tutti gli elementi di `array` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="state"></a>' Stato

Tipo di stati `folder` su cui opera la funzione, ovvero accetta come primo argomento e restituisce.
### <a name="t"></a>T

Tipo di `array` elementi.

## <a name="example"></a>Esempio

```qsharp
function Plus(a : Double, b : Double) {
    return a + b;
}
function Sum(xs : Double[]) {
    return Fold(Plus, 0.0, xs);
}
```