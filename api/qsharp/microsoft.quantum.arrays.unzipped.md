---
uid: Microsoft.Quantum.Arrays.Unzipped
title: Funzione decompressa
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Unzipped
qsharp.summary: Given an array of 2-tuples, returns a tuple of two arrays, each containing the elements of the tuples of the input array.
ms.openlocfilehash: 37c960dc5dbdb8099fbebe1ad63cb44ce642733c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718791"
---
# <a name="unzipped-function"></a>Funzione decompressa

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Data una matrice di 2 Tuple, restituisce una tupla di due matrici, ognuna contenente gli elementi delle tuple della matrice di input.

```qsharp
function Unzipped<'T, 'U> (arr : ('T, 'U)[]) : ('T[], 'U[])
```


## <a name="input"></a>Input

### <a name="arr--tu"></a>arr: (t,' U) []

Matrice contenente 2 Tuple



## <a name="output--tu"></a>Output: (' t [],' U [])

Due matrici, il primo contenente tutti i primi elementi delle tuple di input, il secondo contenente tutti i secondi elementi delle tuple di input.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo del primo elemento in ogni tupla
### <a name="u"></a>' U

Tipo del secondo elemento in ogni tupla

## <a name="see-also"></a>Vedere anche

- [Microsoft.Quantum.Arrays.ZipPED](xref:Microsoft.Quantum.Arrays.Zipped)