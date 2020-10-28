---
uid: Microsoft.Quantum.Arithmetic.MultiplyByModularInteger
title: Operazione MultiplyByModularInteger
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arithmetic
qsharp.name: MultiplyByModularInteger
qsharp.summary: Performs modular multiplication by an integer constant on a qubit register.
ms.openlocfilehash: 6deced7862ab4cb74315219eaaab97380cdf0f92
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719790"
---
# <a name="multiplybymodularinteger-operation"></a>Operazione MultiplyByModularInteger

Spazio dei nomi: [Microsoft. Quantum. aritmetico](xref:Microsoft.Quantum.Arithmetic)

Pacchetto [](https://nuget.org/packages/)


Esegue la moltiplicazione modulare in base a una costante Integer in un registro qubit.

```qsharp
operation MultiplyByModularInteger (constMultiplier : Int, modulus : Int, multiplier : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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