---
uid: Microsoft.Quantum.Arithmetic.MultiplyAndAddByModularInteger
title: Operazione MultiplyAndAddByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyAndAddByModularInteger
qsharp.summary: Performs a modular multiply-and-add by integer constants on a qubit register.
ms.openlocfilehash: 3f85f6aaea1d6f8095709c6f387322df7a5e047c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719811"
---
# <a name="multiplyandaddbymodularinteger-operation"></a>Operazione MultiplyAndAddByModularInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Esegue un valore modulare Multiply-and-Add per le costanti integer in un registro qubit.

```qsharp
operation MultiplyAndAddByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian, summand : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
```


## <a name="description"></a>Descrizione

Implementa la mappa $ $ \begin{align} \ket{x} \ket{b} \mapsto \ket{x} \ket{(b + a \cdot x) \operatorname{mod} N} \end{align} $ $ per un modulo specificato $N $, il moltiplicatore costante $a $ e summand $y $.

## <a name="input"></a>Input

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Integer $a $ da aggiungere a ogni etichetta di stato di base.


### <a name="modulus--int"></a>modulo: [int](xref:microsoft.quantum.lang-ref.int)

Il modulo $N $ quali addizioni e moltiplicazioni vengono prese in relazione a.


### <a name="multiplier--littleendian"></a>moltiplicatore: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registro Quantum che rappresenta un Unsigned Integer il cui valore deve essere aggiunto a ogni etichetta dello stato di base di `summand` .


### <a name="summand--littleendian"></a>summand: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Registro Quantum che rappresenta un Unsigned Integer da usare come destinazione per questa operazione.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

- Per il diagramma di circuito e la spiegazione, vedere la figura 6 sulla [pagina 7 di arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=7)
- Questa operazione corrisponde a CMULT (a) MOD (N) in [arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. aritmetic. MultiplyAndAddPhaseByModularInteger](xref:Microsoft.Quantum.Arithmetic.MultiplyAndAddPhaseByModularInteger)