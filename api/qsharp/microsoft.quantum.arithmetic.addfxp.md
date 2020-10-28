---
uid: Microsoft.Quantum.Arithmetic.AddFxP
title: Operazione AddFxP
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: AddFxP
qsharp.summary: Adds two fixed-point numbers stored in quantum registers.
ms.openlocfilehash: cf1f1379b7e1c32aefb0fccb55f4d13c95c78d8f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721698"
---
# <a name="addfxp-operation"></a>Operazione AddFxP

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Aggiunge due numeri a virgola fissa archiviati nei registri Quantum.

```qsharp
operation AddFxP (fp1 : Microsoft.Quantum.Arithmetic.FixedPoint, fp2 : Microsoft.Quantum.Arithmetic.FixedPoint) : Unit
```


## <a name="description"></a>Descrizione

Dato due registri a virgola fissa rispettivamente negli Stati $ \ket{f_1} $ e $ \ket{f_2} $, esegue l'operazione $ \ket{f_1} \ket{f_2} \mapsto \ket{f_1} \ket{f_1 + f_2} $.

## <a name="input"></a>Input

### <a name="fp1--fixedpoint"></a>FP1: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Primo numero a virgola fissa


### <a name="fp2--fixedpoint"></a>FP2: [FixedPoint](xref:Microsoft.Quantum.Arithmetic.FixedPoint)

Il secondo numero a virgola fissa verrà aggiornato in modo da contenere la somma dei due input.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Per l'implementazione corrente è necessario che i due numeri a virgola fissa dispongano della stessa posizione del punto dal bit meno significativo, ad esempio $n _i $ e $p _i $ debbano essere uguali.