---
uid: Microsoft.Quantum.Arithmetic.ApplyPhaseLEOperationOnLE
title: Operazione ApplyPhaseLEOperationOnLE
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: ApplyPhaseLEOperationOnLE
qsharp.summary: Applies an operation that takes a <xref:microsoft.quantum.arithmetic.littleendian> register as input on a target register of type <xref:microsoft.quantum.arithmetic.phaselittleendian>.
ms.openlocfilehash: dacc52766cf72d2bd562b76fc4939f962133e9a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721551"
---
# <a name="applyphaseleoperationonle-operation"></a>Operazione ApplyPhaseLEOperationOnLE

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Applica un'operazione che accetta un <xref:microsoft.quantum.arithmetic.littleendian> registro come input per un registro di destinazione di tipo <xref:microsoft.quantum.arithmetic.phaselittleendian> .

```qsharp
operation ApplyPhaseLEOperationOnLE (op : (Microsoft.Quantum.Arithmetic.PhaseLittleEndian => Unit), target : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="op--phaselittleendian--unit"></a>op: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian) => [unità](xref:microsoft.quantum.lang-ref.unit) PhaseLittleEndian 

Operazione da applicare.


### <a name="target--littleendian"></a>destinazione: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registro a cui viene applicata l'operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Il registro viene trasformato in `PhaseLittleEndian` mediante l'utilizzo di <xref:microsoft.quantum.canon.qftle> e viene quindi restituito alla relativa rappresentazione originale dopo l'applicazione di `op` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLEA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLEA)
- [Microsoft. Quantum. Canon. ApplyPhaseLEOperationonLECA](xref:Microsoft.Quantum.Canon.ApplyPhaseLEOperationonLECA)