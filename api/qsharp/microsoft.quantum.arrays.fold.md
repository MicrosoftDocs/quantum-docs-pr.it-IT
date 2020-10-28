---
uid: Microsoft.Quantum.Arrays.Fold
title: Funzione fold
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Fold
qsharp.summary: Iterates a function `f` through an array `array`, returning `f(f(f(initialState, array[0]), array[1]), ...)`.
ms.openlocfilehash: 47c23dd657391d80fe473d98f2036d8ddf1dbb0b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719211"
---
# <a name="fold-function"></a>Funzione fold

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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