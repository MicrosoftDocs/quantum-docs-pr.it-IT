---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724244"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete (funzione)

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto [](https://nuget.org/packages/)


Data un'operazione che rappresenta un Oracle "black-box", restituisce un Oracle a tempo discreto che rappresenta il "black-box" Oracle ripetuto più volte.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Input

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a>blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit) ADJ + CTL

Operazione da exponentiatedre.



## <a name="output--discreteoracle"></a>Output: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Un'operazione è stata applicata parzialmente sul Oracle "black-box" che rappresenta l'Oracle a tempo discreto