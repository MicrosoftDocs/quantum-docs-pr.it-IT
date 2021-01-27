---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: b3aa03d20195bdd8bb64783a9b68cafac29e68f6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850916"
---
# <a name="unique-function"></a>Unique (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce una nuova matrice che non dispone di elementi adiacenti uguali.

```qsharp
function Unique<'T> (equal : (('T, 'T) -> Bool), array : 'T[]) : 'T[]
```


## <a name="description"></a>Descrizione

Data una matrice di elementi e una funzione per verificare l'uguaglianza, questa funzione restituisce una nuova matrice in cui viene mantenuto l'ordine relativo degli elementi, ma tutti gli elementi adiacenti uguali vengono filtrati in un solo elemento.

## <a name="input"></a>Input

### <a name="equal--tt---bool"></a>uguale a: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione che confronta due elementi, che `a` sono considerati uguali a `b` se `equal(a, b)` è `true` .


### <a name="array--t"></a>matrice:' t []

Matrice da filtrare per gli elementi univoci.



## <a name="output--t"></a>Output:' t []

Matrice senza elementi adiacenti uguali.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di ogni elemento di `array` .

## <a name="example"></a>Esempio

```qsharp
let unique1 = Unique(EqualI, [1, 1, 3, 3, 2, 5, 5, 5, 7]);
// same as [1, 3, 2, 5, 7]
let unique2 = Unique(EqualI, [2, 2, 1, 1, 2, 2, 1, 1]);
// same as [2, 1, 2, 1];
let unique3 = Unique(EqualI, Sorted(LessThanOrEqualI, [2, 2, 1, 1, 2, 2, 1, 1]));
// same as [1, 2];
```

## <a name="remarks"></a>Commenti

Se sono presenti più elementi uguali ma non vicini tra loro, saranno presenti più occorrenze nella matrice di output.  Usare questa funzione insieme `Sorted` a per ottenere una matrice con elementi univoci complessivi.