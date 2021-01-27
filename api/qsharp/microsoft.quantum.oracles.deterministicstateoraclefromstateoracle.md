---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: af545a7d6e82e654ee36ab3ba77c8f8be3384b96
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854548"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle (funzione)

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Converte un oggetto Oracle di tipo `StateOracle` in `DeterministicStateOracle` .

```qsharp
function DeterministicStateOracleFromStateOracle (idxFlagQubit : Int, stateOracle : Microsoft.Quantum.Oracles.StateOracle) : Microsoft.Quantum.Oracles.DeterministicStateOracle
```


## <a name="input"></a>Input

### <a name="idxflagqubit--int"></a>idxFlagQubit: [int](xref:microsoft.quantum.lang-ref.int)

Indice del flag qubit del `stateOracle` $A $, che agisce in modo esplicito su due registri: il flag $f $ e il sistema $s $, ad esempio $A \ket {0} \_ f\ket {\ psi} \_ s $.


### <a name="stateoracle--stateoracle"></a>stateOracle: [stateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)

Una preparazione dello stato Oracle $A $ di tipo `StateOracle` .



## <a name="output--deterministicstateoracle"></a>Output: [DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)

Lo stesso stato di preparazione Oracle $A $, ma ora di tipo `DeterministicStateOracle` , quindi agisce su un registro in cui $a, s $ non viene più separato in modo esplicito, ad esempio  $A \ket{0\psi} \_ {As} $.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Oracles. StateOracle](xref:Microsoft.Quantum.Oracles.StateOracle)
- [Microsoft. Quantum. Oracles. DeterministicStateOracle](xref:Microsoft.Quantum.Oracles.DeterministicStateOracle)