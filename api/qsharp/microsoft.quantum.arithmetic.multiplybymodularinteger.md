---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operazione MultiplyByModularInteger
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: bd4e0ad6c5bad779d9a31139690021fd9fcda210
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846501"
---
# <a name="multiplybymodularinteger-operation"></a>Operazione MultiplyByModularInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Esegue la moltiplicazione modulare in base a una costante Integer in un registro qubit.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Descrizione

È ora indicata `modulus` da $N $ e `constMultiplier` da $a $.
Questa operazione implementa quindi un'operazione unitaria definita dalla mappa seguente in base al calcolo: $ $ \begin{align} \ket{y} \mapsto \ket{(a \cdot y) \operatorname{mod} N} \end{align} $ $ per tutti $y $ tra $0 $ e $N-$1.

## <a name="input"></a>Input

### <a name="constmultiplier--int"></a>constMultiplier: [int](xref:microsoft.quantum.lang-ref.int)

Costante da cui viene moltiplicato il moltiplicatore. Deve essere co-primo al modulo.


### <a name="modulus--int"></a>modulo: [int](xref:microsoft.quantum.lang-ref.int)

Viene eseguita l'operazione di moltiplicazione modulo `modulus` .


### <a name="multiplier--littleendian"></a>moltiplicatore: [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Numero moltiplicato per una costante.
Si tratta di una matrice di qubits che codifica un numero intero in formato little-endian.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

- Per il diagramma di circuito e la spiegazione, vedere la figura 7 nella [pagina 8 di arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf#page=8)
- Questa operazione corrisponde a U ₐ in [arXiv: quanti-pH/0205095v3](https://arxiv.org/pdf/quant-ph/0205095v3.pdf)