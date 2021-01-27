---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: JWOptimizedGeneratorSystem (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 13e3386a612b238c29a9e3368eed8628e8ed9b66
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98847023"
---
# <a name="jwoptimizedgeneratorsystem-function"></a>JWOptimizedGeneratorSystem (funzione)

Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacchetto: [Microsoft. Quantum. Research. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Research.Chemistry)


Converte un'Hamiltoniana descritta da in `JWOptimizedHTerms` un oggetto `GeneratorSystem` espresso in termini della `GeneratorIndex` convenzione definita in questo file.

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Input

### <a name="data--jwoptimizedhterms"></a>dati: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

Descrizione dell'Hamiltoniana nel `JWOptimizedHTerms` formato.



## <a name="output--generatorsystem"></a>Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Rappresentazione di hamiltoniana come `GeneratorSystem` .