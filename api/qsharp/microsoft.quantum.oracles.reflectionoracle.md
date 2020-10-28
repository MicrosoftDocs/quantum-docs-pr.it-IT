---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definito dall'utente ReflectionOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724213"
---
# <a name="reflectionoracle-user-defined-type"></a>Tipo definito dall'utente ReflectionOracle

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto [](https://nuget.org/packages/)


Rappresenta un oggetto Oracle di Reflection.

Una reflection Oracle, $O $, contiene input:

- Fase $ \Phi $ in base alla quale ruotare il sottospazio riflesso.
- Registro qubit in cui eseguire la reflection specificata.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Elementi denominati

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a>ApplyReflection: ([Double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL



## <a name="remarks"></a>Commenti

Questo $O Oracle = \boldone-(1-e ^ {i \Phi}) \ket{\psi}\bra{\psi} $ esegue una reflection parziale di una fase $ \Phi $ relativa a un singolo stato puro $ \ket{\psi} $.