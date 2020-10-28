---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 4165a761753f336cb7b94ad36b11ac324ad4e5c6
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725025"
---
# <a name="squarednorm-function"></a>SquaredNorm (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


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