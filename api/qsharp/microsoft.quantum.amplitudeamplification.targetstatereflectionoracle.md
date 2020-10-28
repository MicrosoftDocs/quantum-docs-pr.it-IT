---
uid: Microsoft.Quantum.AmplitudeAmplification.TargetStateReflectionOracle
title: TargetStateReflectionOracle (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.AmplitudeAmplification
qsharp.name: TargetStateReflectionOracle
qsharp.summary: >-
  Constructs a `ReflectionOracle` about the target state uniquely marked by the flag qubit.

  The target state has a single qubit set to 1, and all others 0: $\ket{1}_f$.
ms.openlocfilehash: a6ed0397be57ef6f14a712749cc416e1fd98b71c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92721724"
---
# <a name="targetstatereflectionoracle-function"></a>TargetStateReflectionOracle (funzione)

Spazio dei nomi: [Microsoft. Quantum. AmplitudeAmplification](xref:Microsoft.Quantum.AmplitudeAmplification)

Pacchetto [](https://nuget.org/packages/)


Costruisce un oggetto `ReflectionOracle` sullo stato di destinazione in modo univoco contrassegnato dal flag qubit.

Lo stato di destinazione ha un solo qubit impostato su 1 e tutti gli altri 0: $ \ket {1} _F $.

```qsharp
function TargetStateReflectionOracle (idxFlagQubit : Int) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="input"></a>Input

### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Indice per contrassegnare qubit $f $ di Oracle.



## <a name="output--reflectionoracle"></a>Output: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Oggetto `ReflectionOracle` che riflette lo stato contrassegnato da $ \ket {1} _F $.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Canon. ReflectionOracle](xref:Microsoft.Quantum.Canon.ReflectionOracle)