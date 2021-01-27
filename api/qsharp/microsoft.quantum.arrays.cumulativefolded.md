---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: 95cd5233a09a1234bba4de9fe870b9d93c0f86a4
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846230"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Combina il mapping e il ripiego in una singola funzione

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Descrizione

Questa funzione esegue l'iterazione della `fn` funzione attraverso la matrice, iniziando da uno stato iniziale `state` e restituisce tutti i valori intermedi, escluso lo stato iniziale.

## <a name="input"></a>Input

### <a name="fn--statet---state"></a>FN: (' state,' t')->' stato

Funzione da ripiegare sulla matrice


### <a name="state--state"></a>stato:' stato

Stato iniziale da ripiegare


### <a name="array--t"></a>matrice:' t []

Matrice di valori da ripiegare



## <a name="output--state"></a>Output:' stato []

Tutti gli stati intermedi, incluso lo stato finale, ma non lo stato iniziale.
La lunghezza della matrice di output è uguale a quella di `array` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="state"></a>' Stato

Tipo di stati `fn` su cui opera la funzione, ovvero accetta come primo input e restituisce.
### <a name="t"></a>T

Tipo di `array` elementi.

## <a name="example"></a>Esempio

```qsharp
// same as sums = [1, 3, 6, 10, 15]
let sums = CumulativeFolded(PlusI, 0, SequenceI(1, 5));
```