---
uid: Microsoft.Quantum.Arrays.Rest
title: Rest (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Rest
qsharp.summary: Creates an array that is equal to an input array except that the first array element is dropped.
ms.openlocfilehash: c14e4b2902741d7ea70c895aa715cbcaa849af3e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718914"
---
# <a name="rest-function"></a>Rest (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Crea una matrice uguale a una matrice di input, ad eccezione del fatto che il primo elemento della matrice viene eliminato.

```qsharp
function Rest<'T> (array : 'T[]) : 'T[]
```


## <a name="input"></a>Input

### <a name="array--t"></a>matrice:' t []

Matrice il cui penultimo elemento consiste nel formare la matrice di output.



## <a name="output--t"></a>Output:' t []

Matrice contenente gli elementi `array[1..Length(array) - 1]` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo degli elementi della matrice.