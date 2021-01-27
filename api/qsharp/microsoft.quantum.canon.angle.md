---
uid: Microsoft.Quantum.Canon.Angle
title: Angle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Angle
qsharp.summary: Returns 1, if `index` has an odd number of 1s and -1, if `index` has an even number of 1s.
ms.openlocfilehash: 0528f21b2d9c98b6497e28741964e6497d4d0fb9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842048"
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

