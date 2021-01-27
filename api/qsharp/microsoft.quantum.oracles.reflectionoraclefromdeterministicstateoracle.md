---
uid: Microsoft.Quantum.Oracles.ReflectionOracleFromDeterministicStateOracle
title: ReflectionOracleFromDeterministicStateOracle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracleFromDeterministicStateOracle
qsharp.summary: Constructs reflection about a given state from an oracle.
ms.openlocfilehash: c260bdbcdb2ce53ad602bf84e0d31ef4fec24a79
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842517"
---
# <a name="reflectionoraclefromdeterministicstateoracle-function"></a>ReflectionOracleFromDeterministicStateOracle (funzione)

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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