---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger
title: Operazione MultiplyAndAddPhaseByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddPhaseByModularInteger
qsharp.summary: The same as MultiplyAndAddByModularInteger, but assumes that the summand encodes integers in QFT basis.
ms.openlocfilehash: be7df50f040697329c2fe8bbc319c8cebb8b2687
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719802"
---
# <a name="multiplyandaddphasebymodularinteger-operation"></a>Operazione MultiplyAndAddPhaseByModularInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Analogamente a MultiplyAndAddByModularInteger, ma presuppone che summand Codifichi numeri interi in base a QFT.

```qsharp
operation MultiplyAndAddPhaseByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, phaseSummand : Microsoft.Quantum.Arithmetic.PhaseLittleEndian) : Unit
```


## <a name="input"></a>Input

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Integer $a $ da aggiungere a ogni etichetta di stato di base.


### <a name="modulus--int"></a>modulo: [int](xref:microsoft.quantum.lang-ref.int)

Il modulo $N $ quali addizioni e moltiplicazioni vengono prese in relazione a.


### <a name="multiplier--littleendian"></a>moltiplicatore: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registro Quantum che rappresenta un Unsigned Integer il cui valore deve essere aggiunto a ogni etichetta dello stato di base di `summand` .


### <a name="phasesummand--phaselittleendian"></a>phaseSummand: [PhaseLittleEndian](xref:Microsoft.Quantum.Arithmetic.PhaseLittleEndian)

Registro Quantum che rappresenta un Unsigned Integer da usare come destinazione per questa operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Presuppone che `phaseSummand` il bit più alto sia impostato su 0.
Presuppone inoltre che il valore di `phaseSummand` sia minore di $N $.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. aritmetic. MultiplyAndAddByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger)