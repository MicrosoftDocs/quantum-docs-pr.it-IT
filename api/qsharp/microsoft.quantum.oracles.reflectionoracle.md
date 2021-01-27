---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Tipo definito dall'utente ReflectionOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854481"
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