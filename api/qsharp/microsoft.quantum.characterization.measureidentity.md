---
uid: Microsoft.Quantum.Characterization.MeasureIdentity
title: Operazione MeasureIdentity
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: MeasureIdentity
qsharp.summary: Measures the identity operator on a register of qubits.
ms.openlocfilehash: f8cf5975ac9407e8c532ace08455a41d3c08d6f0
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851821"
---
# <a name="measureidentity-operation"></a>Operazione MeasureIdentity

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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