---
uid: Microsoft.Quantum.Simulation.BlockEncodingReflectionByLCU
title: BlockEncodingReflectionByLCU (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingReflectionByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncodingReflection`.

  This constructs a `BlockEncodingReflection` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: e1247d961a7ebce798106c24c46d924dd6e6d347
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229478"
---
# <a name="blockencodingreflectionbylcu-function"></a>BlockEncodingReflectionByLCU (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Codifica un operatore di interesse in un oggetto `BlockEncodingReflection` .

Questo costrutto un `BlockEncodingReflection` $U unitario = P\cdot V\cdot P ^ \dagger $ che codifica un operatore $H = \ Sum_ {j} | \ alpha_j | U_j $ di interesse che è una combinazione lineare di unitaries. In genere, $P $ è un Unity di preparazione dello stato in modo che $P \ket {0} \_ a \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ e $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingReflectionByLCU (statePreparation : (Qubit[] => Unit is Adj + Ctl), selector : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)) : Microsoft.Quantum.Simulation.BlockEncodingReflection
```


## <a name="input"></a>Input

### <a name="statepreparation--qubit--unit--is-adj--ctl"></a>statePreparation: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Unitario $P $ che prepara uno stato di destinazione.


### <a name="selector--qubitqubit--unit--is-adj--ctl"></a>selettore: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Un Unity $V $ che codifica il componente unitaries di $H $.



## <a name="output--blockencodingreflection"></a>Output: [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

Un Unity $U $ agisce congiuntamente sui registri `a` e `s` tale codifica a blocchi $H $ e soddisfa $U ' ^ {-1} = U $.

## <a name="remarks"></a>Commenti

Questa `BlockEncoding` implementazione fornisce le proprietà di un oggetto `BlockEncodingReflection` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)