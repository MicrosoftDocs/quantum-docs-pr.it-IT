---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: e31273702a9850d0162f160ca412ff6d50f38b28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723362"
---
# <a name="expmodi-function"></a>ExpModI (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Restituisce un intero elevato a una determinata potenza, rispetto a un modulo specificato.

```qsharp
function ExpModI (expBase : Int, power : Int, modulus : Int) : Int
```


## <a name="description"></a>Descrizione

È ora necessario indicare expBase per $x $, Power by $p $ e modulo per $N $.
La funzione restituisce $x ^ p \operatorname{mod} N $.

Si presuppone che $N $, $x $ siano positivi e che la potenza sia non negativa.

## <a name="input"></a>Input

### <a name="expbase--int"></a>expBase: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="power--int"></a>Potenza: [int](xref:microsoft.quantum.lang-ref.int)




### <a name="modulus--int"></a>modulo: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)



## <a name="remarks"></a>Commenti

Richiede tempo proporzionale al numero di bit in `power` , non a `power` se stesso.