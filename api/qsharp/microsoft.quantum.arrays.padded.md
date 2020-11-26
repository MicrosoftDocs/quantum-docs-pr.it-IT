---
uid: Microsoft.Quantum.Arrays.Padded
title: Funzione riempita
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Padded
qsharp.summary: Returns an array padded at with specified values up to a specified length.
ms.openlocfilehash: 2b7a80d1cf5c82a1ff52bc4aa207cfe335b40061
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96220536"
---
# <a name="padded-function"></a>Funzione riempita

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce una matrice riempita con i valori specificati fino a una lunghezza specificata.

```qsharp
function Padded<'T> (nElementsTotal : Int, defaultElement : 'T, inputArray : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="nelementstotal--int"></a>nElementsTotal: [int](xref:microsoft.quantum.lang-ref.int)

Lunghezza della matrice riempita. Se questo è positivo, `inputArray` viene riempito alla testa. Se si tratta di un valore negativo, `inputArray` viene riempito alla fine della coda.


### <a name="defaultelement--t"></a>impostazione predefinita:' t

Valore predefinito da usare per gli elementi di riempimento.


### <a name="inputarray--t"></a>inputArray:' t []

Matrice i cui valori si trovano all'inizio della matrice di output.



## <a name="output--t"></a>Output:' t []

Matrice `output` `inputArray` riempita all'inizio con `defaultElement` s finché non `output` ha lunghezza `nElementsTotal`

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo degli elementi della matrice.