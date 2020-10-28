---
uid: Microsoft.Quantum.Logical.NotNearlyEqualD
title: NotNearlyEqualD (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: NotNearlyEqualD
qsharp.summary: Returns true if and only if two inputs are not nearly equal (that is, are not within a tolerance of 1e-12).
ms.openlocfilehash: d9e4cc5b0cfba3989ae64e494d0daa52069718a4
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720726"
---
# <a name="notnearlyequald-function"></a>NotNearlyEqualD (funzione)

Spazio dei nomi: [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)

Pacchetto [](https://nuget.org/packages/)


Restituisce true se e solo se due input non sono quasi uguali (ovvero, non sono compresi nella tolleranza di 1e-12).

```qsharp
function NotNearlyEqualD (a : Double, b : Double) : Bool
```


## <a name="input"></a>Input

### <a name="a--double"></a>a: [Double](xref:microsoft.quantum.lang-ref.double)

Primo valore da confrontare.


### <a name="b--double"></a>b: [Double](xref:microsoft.quantum.lang-ref.double)

Secondo valore da confrontare.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` Se e solo se `a` non è quasi uguale a `b` .

## <a name="remarks"></a>Commenti

Gli elementi seguenti sono equivalenti:

```Q#
let cond = Microsoft.Quantum.Math.AbsD(a - b) >= 1e-12;
let cond = NotNearlyEqualD(a, b);
```