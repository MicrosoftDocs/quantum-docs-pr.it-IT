---
uid: Microsoft.Quantum.Arrays.Any
title: Qualsiasi funzione
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Any
qsharp.summary: Given an array and a predicate that is defined for the elements of the array, checks if at least one element of the array satisfies the predicate.
ms.openlocfilehash: dd5639f1b0a76cb356c89aca0c0e02d375f30d12
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719475"
---
# <a name="any-function"></a>Qualsiasi funzione

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Data una matrice e un predicato definito per gli elementi della matrice, verifica se almeno un elemento della matrice soddisfa il predicato.

```qsharp
function Any<'T> (predicate : ('T -> Bool), array : 'T[]) : Bool
```


## <a name="input"></a>Input

### <a name="predicate--t---bool"></a>predicato:' t-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione da `'T` a `Bool` utilizzata per controllare gli elementi.


### <a name="array--t"></a>matrice:' t []

Matrice di elementi su `'T` .



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`Bool`Valore della funzione o del predicato applicato a tutti gli elementi.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di `array` elementi.

## <a name="remarks"></a>Commenti

La funzione è definita per i tipi generici, ad esempio, ogni volta che si dispone di una matrice `'T[]` e di una funzione, è `predicate: 'T -> Bool` possibile produrre un `Bool` valore che indica se alcuni elementi soddisfano `predicate` .