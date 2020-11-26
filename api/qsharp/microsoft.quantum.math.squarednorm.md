---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: ecbc66a8851f23187e0c0ea53ce121442323733b
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96227302"
---
# <a name="squarednorm-function"></a>SquaredNorm (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce la norma 2 quadrata di un vettore.

```qsharp
function SquaredNorm (array : Double[]) : Double
```


## <a name="description"></a>Descrizione

Restituisce la norma 2 quadrata di un vettore; ovvero, dato un input $ \vec{x} $, restituisce $ \ sum_i x_i ^ 2 $.

## <a name="input"></a>Input

### <a name="array--double"></a>array: [Double](xref:microsoft.quantum.lang-ref.double)[]

Vettore di cui deve essere restituita la norma quadrata 2.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)

La norma 2 quadrata di `array` .