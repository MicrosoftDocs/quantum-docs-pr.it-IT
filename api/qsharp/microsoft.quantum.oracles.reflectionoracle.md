---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definito dall'utente ReflectionOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226656"
---
# <a name="reflectionoracle-user-defined-type"></a>Tipo definito dall'utente ReflectionOracle

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un oggetto Oracle di Reflection.

Una reflection Oracle, $O $, contiene input:

- Fase $ \Phi $ in base alla quale ruotare il sottospazio riflesso.
- Registro qubit in cui eseguire la reflection specificata.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Elementi denominati

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL



## <a name="remarks"></a>Commenti

Questo $O Oracle = \boldone-(1-e ^ {i \Phi}) \ket{\psi}\bra{\psi} $ esegue una reflection parziale di una fase $ \Phi $ relativa a un singolo stato puro $ \ket{\psi} $.