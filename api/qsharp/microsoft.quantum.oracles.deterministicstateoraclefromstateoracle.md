---
uid: Microsoft.Quantum.Oracles.DeterministicStateOracleFromStateOracle
title: DeterministicStateOracleFromStateOracle (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: DeterministicStateOracleFromStateOracle
qsharp.summary: Converts an oracle of type `StateOracle` to `DeterministicStateOracle`.
ms.openlocfilehash: 539cc56e7ae4ead6654aaaae5353a771e06d2bfb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724255"
---
# <a name="deterministicstateoraclefromstateoracle-function"></a>DeterministicStateOracleFromStateOracle (funzione)

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto [](https://nuget.org/packages/)


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