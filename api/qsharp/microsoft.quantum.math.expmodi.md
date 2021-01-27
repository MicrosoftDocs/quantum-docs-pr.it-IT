---
uid: Microsoft.Quantum.Math.ExpModI
title: ExpModI (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModI
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: dd4fc7d98275f6a02e3b13163b92f0812c92a82f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98857041"
---
# <a name="expmodi-function"></a>ExpModI (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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