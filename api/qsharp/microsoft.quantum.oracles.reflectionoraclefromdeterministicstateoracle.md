---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c2d37216aebcdc5243d0f1d6ec9db261cc9bd0c8
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92722183"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle (funzione)

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto [](https://nuget.org/packages/)


Costruisce la reflection su un dato stato da un Oracle.

```qsharp
function ReflectionOracleFromDeterministicStateOracle (oracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.ReflectionOracle
```


## <a name="description"></a>Descrizione

Dato un Oracle di preparazione dello stato deterministico rappresentato da una matrice unitaria $O $, il risultato di questa funzione è un Oracle che applica una reflection intorno allo stato $ \ket{\psi} $ preparato da Oracle $O $; ovvero lo stato $ \ket{\psi} $ in modo che $O \ket {0} = \ket{\psi} $.

## <a name="input"></a>Input

### <a name="oracle--deterministicstateoracle"></a>Oracle: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Oracle che prepara copie dello stato $ \ket{\psi} $.



## <a name="output--reflectionoracle"></a>Output: [ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)

Oracle che riflette lo stato $ \ket{\psi} $.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. Oracles. ReflectionOracle](xref:Microsoft.Quantum.Oracles.ReflectionOracle)