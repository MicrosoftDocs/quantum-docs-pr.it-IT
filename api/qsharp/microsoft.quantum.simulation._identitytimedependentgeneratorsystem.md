---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: Funzione _IdentityTimeDependentGeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 7b93a6674bec974e61496696a3d8403225b16d80
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225602"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>Funzione _IdentityTimeDependentGeneratorSystem

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un sistema di generazione coerente con l'Hamiltoniana `H(s) = 0` , dove `s` è un parametro di pianificazione.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Input

### <a name="schedule--double"></a>pianificazione: [Double](xref:microsoft.quantum.lang-ref.double)

Questo input viene ignorato e viene definito per coerenza con il <xref:microsoft.quantum.canon.timedependentgeneratorsystem> tipo definito dall'utente.



## <a name="output--generatorsystem"></a>Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Sistema di generazione che rappresenta l'evoluzione nei $H hamiltoniana = $0 per tutti i $s $.