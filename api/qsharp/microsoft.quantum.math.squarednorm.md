---
uid: Microsoft.Quantum.Math.SquaredNorm
title: SquaredNorm (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: SquaredNorm
qsharp.summary: Returns the squared 2-norm of a vector.
ms.openlocfilehash: 72ae8266492bef64eaec34cd70c5fe725ee1e8c9
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848207"
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