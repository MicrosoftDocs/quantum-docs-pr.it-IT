---
uid: Microsoft.Quantum.Simulation.BlockEncodingByLCU
title: BlockEncodingByLCU (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: BlockEncodingByLCU
qsharp.summary: >-
  Encodes an operator of interest into a `BlockEncoding`.

  This constructs a `BlockEncoding` unitary $U=P\cdot V\cdot P^\dagger$ that encodes some operator $H=\sum_{j}|\alpha_j|U_j$ of interest that is a linear combination of unitaries. Typically, $P$ is a state preparation unitary such that $P\ket{0}\_a=\sum_j\sqrt{\alpha_j/\|\vec\alpha\|\_2}\ket{j}\_a$, and $V=\sum_{j}\ket{j}\bra{j}\_a\otimes U_j$.
ms.openlocfilehash: 254ace01750f94e6c871de9b62f1342000bc84ea
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229546"
---
# <a name="blockencodingbylcu-function"></a>BlockEncodingByLCU (funzione)

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Codifica un operatore di interesse in un oggetto `BlockEncoding` .

Questo costrutto un `BlockEncoding` $U unitario = P\cdot V\cdot P ^ \dagger $ che codifica un operatore $H = \ Sum_ {j} | \ alpha_j | U_j $ di interesse che è una combinazione lineare di unitaries. In genere, $P $ è un Unity di preparazione dello stato in modo che $P \ket {0} \_ a = \ sum_j \sqrt{\ alpha_j/ \| \vec\alpha \| \_ 2} \ket{j} \_ a $ e $V = \ sum_ {j} \ket{j}\bra{j} \_ a\otimes U_j $.

```qsharp
function BlockEncodingByLCU<'T, 'S> (statePreparation : ('T => Unit is Adj + Ctl), selector : (('T, 'S) => Unit is Adj + Ctl)) : (('T, 'S) => Unit is Adj + Ctl)
```


## <a name="input"></a>Input

### <a name="statepreparation--t--unit--is-adj--ctl"></a>statePreparation:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Unitario $P $ che prepara uno stato di destinazione.


### <a name="selector--ts--unit--is-adj--ctl"></a>selettore: (t, s) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Un Unity $V $ che codifica il componente unitaries di $H $.



## <a name="output--ts--unit--is-adj--ctl"></a>Output: (' t,') => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Un Unity $U $ agisce congiuntamente sui registri `a` e `s` tale codifica a blocchi $H $ e soddisfa $U ^ \Dagger = U $.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="s"></a>Gli



## <a name="remarks"></a>Commenti

Questa `BlockEncoding` implementazione fornisce le proprietà di un oggetto `BlockEncodingReflection` .

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. Simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)