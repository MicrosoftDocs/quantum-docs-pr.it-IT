---
uid: Microsoft.Quantum.Arrays.Unique
title: Unique (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unique
qsharp.summary: Returns a new array that has no equal adjacent elements.
ms.openlocfilehash: c5d40bb82f2de640e9c78eef0c27e4766b477826
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718782"
---
# <a name="unique-function"></a>Unique (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Commenti

Se sono presenti più elementi uguali ma non vicini tra loro, saranno presenti più occorrenze nella matrice di output.  Usare questa funzione insieme `Sorted` a per ottenere una matrice con elementi univoci complessivi.