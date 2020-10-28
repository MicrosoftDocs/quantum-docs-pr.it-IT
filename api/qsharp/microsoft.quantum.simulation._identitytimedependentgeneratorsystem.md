---
uid: Microsoft.Quantum.Simulation._IdentityTimeDependentGeneratorSystem
title: Funzione _IdentityTimeDependentGeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: _IdentityTimeDependentGeneratorSystem
qsharp.summary: Returns a generator system consistent with the Hamiltonian `H(s) = 0`, where `s` is a schedule parameter.
ms.openlocfilehash: 0b440ce9adaab562e16b02da46844c68a7470b11
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92710688"
---
# <a name="_identitytimedependentgeneratorsystem-function"></a>Funzione _IdentityTimeDependentGeneratorSystem

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Restituisce un sistema di generazione coerente con l'Hamiltoniana `H(s) = 0` , dove `s` è un parametro di pianificazione.

```qsharp
function _IdentityTimeDependentGeneratorSystem (schedule : Double) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Input

### <a name="schedule--double"></a>pianificazione: [Double](xref:microsoft.quantum.lang-ref.double)

Questo input viene ignorato e viene definito per coerenza con il <xref:microsoft.quantum.canon.timedependentgeneratorsystem> tipo definito dall'utente.



## <a name="output--generatorsystem"></a>Output: [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Sistema di generazione che rappresenta l'evoluzione nei $H hamiltoniana = $0 per tutti i $s $.