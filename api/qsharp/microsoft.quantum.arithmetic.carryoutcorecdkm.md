---
uid: Microsoft.Quantum.Arithmetic.CarryOutCoreCDKM
title: Operazione CarryOutCoreCDKM
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: CarryOutCoreCDKM
qsharp.summary: The core operation in the RippleCarryAdderCDKM, used with the above ApplyOuterCDKMAdder operation, i.e. conjugated with this operation to obtain the inner operation of the RippleCarryAdderCDKM. This operation computes the carry out qubit and applies a sequence of NOT gates on part of the input `ys`.
ms.openlocfilehash: 6a292e66f6d9911d2a9075f6397f4f5ba97ec64d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721302"
---
# <a name="carryoutcorecdkm-operation"></a>Operazione CarryOutCoreCDKM

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Operazione di base in RippleCarryAdderCDKM, usata con l'operazione ApplyOuterCDKMAdder precedente, ad esempio coniugata con questa operazione per ottenere il funzionamento interno di RippleCarryAdderCDKM. Questa operazione calcola il qubit di esecuzione e applica una sequenza di controlli NOT in parte dell'input `ys` .

```qsharp
operation CarryOutCoreCDKM (xs : Microsoft.Quantum.Arithmetic.LittleEndian, ys : Microsoft.Quantum.Arithmetic.LittleEndian, ancilla : Qubit, carry : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="xs--littleendian"></a>XS: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Primo registro qubit.


### <a name="ys--littleendian"></a>Ys: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Secondo registro qubit.


### <a name="ancilla--qubit"></a>Ancilla: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit ancilla utilizzato in RippleCarryAdderCDKM passato a questa operazione.


### <a name="carry--qubit"></a>porta: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Eseguire qubit nell'operazione RippleCarryAdderCDKM.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="references"></a>Riferimenti

- Steven A. Cuccaro, Thomas G. Draper, Samuel A. kutin, David Petrie Moulton: "A New Quantum Ripple-Carry additional Circuit", 2004.
  https://arxiv.org/abs/quant-ph/0410184v1