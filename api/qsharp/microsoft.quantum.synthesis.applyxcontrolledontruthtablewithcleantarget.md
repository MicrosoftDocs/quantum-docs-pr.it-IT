---
uid: Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTableWithCleanTarget
title: Operazione ApplyXControlledOnTruthTableWithCleanTarget
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyXControlledOnTruthTableWithCleanTarget
qsharp.summary: Applies the @"microsoft.quantum.intrinsic.x" operation on `target`, if the Boolean function `func` evaluates to true for the classical assignment in `controlRegister`.
ms.openlocfilehash: b43a5351985339bcf7c1f2bbe03ae6dc6dfdd165
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92725235"
---
# <a name="applyxcontrolledontruthtablewithcleantarget-operation"></a>Operazione ApplyXControlledOnTruthTableWithCleanTarget

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto [](https://nuget.org/packages/)


Applica l' @"microsoft.quantum.intrinsic.x" operazione su `target` , se la funzione booleana `func` restituisce true per l'assegnazione classica in `controlRegister` .

```qsharp
operation ApplyXControlledOnTruthTableWithCleanTarget (func : BigInt, controlRegister : Qubit[], target : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Questa operazione implementa un caso speciale di @"microsoft.quantum.synthesis.applyxcontrolledontruthtable" , in cui il qubit di destinazione è noto come nello stato $ \ket {0} $.

L'implementazione utilizza le attività di controllo @"microsoft.quantum.intrinsic.cnot" e @"microsoft.quantum.intrinsic.r1" .  L'implementazione dell'operazione contigua è ottimizzata e utilizza l'incalcolo basato sulla misurazione.

## <a name="input"></a>Input

### <a name="func--bigint"></a>Func: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Tabella di verità booleana rappresentata come valore Big Integer


### <a name="controlregister--qubit"></a>controlRegister: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Registro dei qubits di controllo


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit di destinazione (deve essere nello stato $ \ket {0} $)



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Synthesis. ApplyXControlledOnTruthTable](xref:Microsoft.Quantum.Synthesis.ApplyXControlledOnTruthTable)