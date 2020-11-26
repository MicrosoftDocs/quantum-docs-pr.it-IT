---
uid: Microsoft.Quantum.Canon.Angle
title: Angle (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 1d8a9c2c19469e4949f043edd1ba91021fa42e78
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96219414"
---
# <a name="angle-function"></a>Angle (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce 1, se `index` ha un numero dispari di 1s e-1, se `index` ha un numero pari di 1s.

```qsharp
function Angle (index : Int) : Int
```


## <a name="description"></a>Descrizione

Il valore corrisponde al segno del coefficiente dello spettro di Rademacher-Walsh della variabile n e della funzione per una determinata assegnazione che decide l'angolo della rotazione.

## <a name="input"></a>Input

### <a name="index--int"></a>Indice: [int](xref:microsoft.quantum.lang-ref.int)

Assegnazione di input come Integer (da 0 a 2 ^ n-1)



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)

