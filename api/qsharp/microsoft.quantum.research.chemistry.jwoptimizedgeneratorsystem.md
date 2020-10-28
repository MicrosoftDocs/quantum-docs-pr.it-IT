---
uid: Microsoft.Quantum.Research.Chemistry.JWOptimizedGeneratorSystem
title: JWOptimizedGeneratorSystem (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Research.Chemistry
qsharp.name: JWOptimizedGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: 8e4c06b9447a2e5838cced876febee03d1af5315
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710783"
---
# <a name="jwoptimizedgeneratorsystem-function"></a>JWOptimizedGeneratorSystem (funzione)

Spazio dei nomi: [Microsoft. Quantum. Research. Chemistry](xref:Microsoft.Quantum.Research.Chemistry)

Pacchetto [](https://nuget.org/packages/)


Converte un'Hamiltoniana descritta da in `JWOptimizedHTerms` un oggetto `GeneratorSystem` espresso in termini della `GeneratorIndex` convenzione definita in questo file.

```qsharp
function JWOptimizedGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Input

### <a name="data--jwoptimizedhterms"></a>dati: [JWOptimizedHTerms](xref:Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms)

Descrizione dell'Hamiltoniana nel `JWOptimizedHTerms` formato.



## <a name="output--generatorsystem"></a>Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Rappresentazione di hamiltoniana come `GeneratorSystem` .