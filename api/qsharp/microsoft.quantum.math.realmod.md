---
uid: Microsoft.Quantum.Math.RealMod
title: RealMod (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Math
qsharp.name: RealMod
qsharp.summary: Computes the modulus between two real numbers.
ms.openlocfilehash: 6ec799885bd2f0d35314ed727356499efbe9fcf8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720402"
---
# <a name="realmod-function"></a>RealMod (funzione)

Spazio dei nomi: [Microsoft. Quantum. Math](xref:Microsoft.Quantum.Math)

Pacchetto [](https://nuget.org/packages/)


Calcola il modulo tra due numeri reali.

```qsharp
function RealMod (value : Double, modulo : Double, minValue : Double) : Double
```


## <a name="input"></a>Input

### <a name="value--double"></a>valore: [Double](xref:microsoft.quantum.lang-ref.double)

Un numero reale $x $ per eseguire il modulo di.


### <a name="modulo--double"></a>modulo: [Double](xref:microsoft.quantum.lang-ref.double)

Numero reale da usare per il modulo di $x $ rispetto a.


### <a name="minvalue--double"></a>minValue: [Double](xref:microsoft.quantum.lang-ref.double)

Valore minimo che deve essere restituito da questa funzione.



## <a name="output--double"></a>Output: [Double](xref:microsoft.quantum.lang-ref.double)



## <a name="remarks"></a>Commenti

Questa funzione calcola il modulo reale eseguendo il wrapping della riga reale sul cerchio di unità, quindi individuando l'angolo nel cerchio di unità corrispondente all'input.
L' `minValue` input specifica quindi la posizione in cui tagliare il cerchio di unità.