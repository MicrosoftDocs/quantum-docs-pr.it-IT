---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842545"
---
# <a name="oracletodiscrete-function"></a>OracleToDiscrete (funzione)

Spazio dei nomi: [Microsoft. Quantum. Oracles](xref:Microsoft.Quantum.Oracles)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Data un'operazione che rappresenta un Oracle "black-box", restituisce un Oracle a tempo discreto che rappresenta il "black-box" Oracle ripetuto più volte.

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a>Input

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a>blackBoxOracle: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione da exponentiatedre.



## <a name="output--discreteoracle"></a>Output: [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)

Un'operazione è stata applicata parzialmente sul Oracle "black-box" che rappresenta l'Oracle a tempo discreto

## <a name="example"></a>Esempio

`OracleToDiscrete(U)(3, target)` equivale a `U(target)` tre volte ripetute.