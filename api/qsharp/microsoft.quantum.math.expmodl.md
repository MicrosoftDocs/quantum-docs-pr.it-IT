---
uid: Microsoft.Quantum.Math.ExpModL
title: ExpModL (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: ExpModL
qsharp.summary: Returns an integer raised to a given power, with respect to a given modulus.
ms.openlocfilehash: 73d434bd364847b4e5e06d1a9f460424e0c50850
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723726"
---
# <a name="expmodl-function"></a>ExpModL (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Restituisce un intero elevato a una determinata potenza, rispetto a un modulo specificato.

```qsharp
function ExpModL (expBase : BigInt, power : BigInt, modulus : BigInt) : BigInt
```


## <a name="description"></a>Descrizione

È ora necessario indicare expBase per $x $, Power by $p $ e modulo per $N $.
La funzione restituisce $x ^ p \operatorname{mod} N $.

Si presuppone che $N $, $x $ siano positivi e che la potenza sia non negativa.

## <a name="input"></a>Input

### <a name="expbase--bigint"></a>expBase: [bigint](xref:microsoft.quantum.lang-ref.bigint)




### <a name="power--bigint"></a>Potenza: [bigint](xref:microsoft.quantum.lang-ref.bigint)




### <a name="modulus--bigint"></a>modulo: [bigint](xref:microsoft.quantum.lang-ref.bigint)





## <a name="output--bigint"></a>Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)



## <a name="remarks"></a>Commenti

Richiede tempo proporzionale al numero di bit in `power` , non a `power` se stesso.