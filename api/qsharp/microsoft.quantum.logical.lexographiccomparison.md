---
uid: Microsoft.Quantum.Logical.LexographicComparison
title: LexographicComparison (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LexographicComparison
qsharp.summary: Given a comparison function, returns a new function that lexographically compares two arrays.
ms.openlocfilehash: de8179ab6e835d08e7f41287f31a876b7ecc91c5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98814390"
---
# <a name="lexographiccomparison-function"></a>LexographicComparison (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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