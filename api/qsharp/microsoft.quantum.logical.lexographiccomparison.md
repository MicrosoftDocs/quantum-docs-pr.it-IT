---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: f0b68974a0ea26907b58971e4fa4b1f06f5714d2
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709904"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto [](https://nuget.org/packages/)


Data una funzione di confronto, restituisce una nuova funzione che lexographically Confronta due matrici.

```qsharp
function LexographicComparison<'T> (elementComparison : (('T, 'T) -> Bool)) : (('T[], 'T[]) -> Bool)
```


## <a name="input"></a>Input

### <a name="elementcomparison--tt---bool"></a>elementComparison: (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione che confronta due elementi `x` e `y` restituisce se `x` è minore o uguale a `y` .



## <a name="output--tt---bool"></a>Output: (t [],' t [])-> [bool](xref:microsoft.quantum.lang-ref.bool)

Funzione che confronta due matrici `xs` e `ys` restituisce se `xs` si verifica prima o uguale a `ys` nell'ordinamento lexographical.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo degli elementi delle matrici da confrontare.

## <a name="remarks"></a>Commenti

Il confronto lexographic tra due matrici `xs` e `ys` viene definito dalla procedura seguente. Si dice che due elementi `x` e `y` sono equivalenti se `elementComparison(x, y)` e `elementComparison(y, x)` sono entrambi true.

- Entrambe le matrici vengono confrontate elemento per elemento fino alla prima coppia di elementi che non sono equivalenti. La matrice che contiene l'elemento che si verifica per primo in base a `elementComparison` è detta prima nell'ordinamento lexographical.
- Se non vengono trovati elementi inequivalenti e una matrice è più lunga dell'altra, viene detta prima di tutto la matrice più breve.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. Sorted](xref:Microsoft.Quantum.Arrays.Sorted)