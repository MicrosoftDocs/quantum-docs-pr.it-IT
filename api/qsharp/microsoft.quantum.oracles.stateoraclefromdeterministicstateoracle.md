---
uid: Microsoft.Quantum.Oracles.StateOracleFromDeterministicStateOracle
title: StateOracleFromDeterministicStateOracle (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: StateOracleFromDeterministicStateOracle
qsharp.summary: Converts an oracle of type `DeterministicStateOracle` to `StateOracle`.
ms.openlocfilehash: ccb083dbaaec2f306ba0740ef364ebb22408ed98
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724216"
---
# <a name="stateoraclefromdeterministicstateoracle-function"></a>StateOracleFromDeterministicStateOracle (funzione)

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto [](https://nuget.org/packages/)


Converte un oggetto Oracle di tipo `DeterministicStateOracle` in `StateOracle` .

```qsharp
function StateOracleFromDeterministicStateOracle (deterministicStateOracle : Microsoft.Quantum.Oracles.DeterministicStateOracle) : Microsoft.Quantum.Oracles.StateOracle
```


## <a name="input"></a>Input

### <a name="deterministicstateoracle--deterministicstateoracle"></a>deterministicStateOracle: [deterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Una preparazione dello stato Oracle $A $ di tipo `DeterministicStateOracle` .



## <a name="output--stateoracle"></a>Output: [StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Lo stesso stato di preparazione Oracle $A $, ma ora di tipo `StateOracle` . Si noti che l'indice del flag in questo `StateOracle` oggetto è una variabile fittizia e non ha alcun effetto.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)
- [Microsoft. Quantum. Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)