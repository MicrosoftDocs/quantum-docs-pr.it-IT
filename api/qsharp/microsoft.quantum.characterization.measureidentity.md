---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operazione MeasureIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: 71a103fddb3a27703318975bea94bc7a22a9ce81
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714969"
---
# <a name="measureidentity-operation"></a>Operazione MeasureIdentity

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto [](https://nuget.org/packages/)


Misura l'operatore di identità in un registro di qubits.

```qsharp
operation MeasureIdentity (register : Qubit[]) : Result
```


## <a name="input"></a>Input

### <a name="register--qubit"></a>Register: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro da misurare.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Valore del risultato `Zero` .

## <a name="remarks"></a>Commenti

Poiché $ \boldone $ ha solo autovalore $1 $ e non ha un autovalore negativo, questa operazione restituisce sempre `Zero` , corrispondente a autovalore $ + 1 = (-1) ^ 0 $, e non provoca un collasso dello stato di `register` .

Da solo, questa operazione non è utile, ma è utile nel contesto della tomografia dei processi, poiché fornisce informazioni sulla conservazione delle tracce di un processo quantum.
In particolare, un computer di destinazione con misurazione con perdita di dati deve sostituire questa operazione con una misurazione effettiva di $ \boldone $.