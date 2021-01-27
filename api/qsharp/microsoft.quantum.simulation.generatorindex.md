---
uid: Microsoft.Quantum.Simulation.GeneratorIndex
title: Tipo definito dall'utente GeneratorIndex
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorIndex
qsharp.summary: >-
  Represents a single primitive term in the set of all dynamical generators, e.g. Hermitian operators, for which there exists a map from that generator to time-evolution by that generator, through `EvolutionSet`.

  The first element (Int[], Double[]) is indexes that single term -- For instance, the Pauli string XXY with coefficient 0.5 would be indexed by ([1,1,2], [0.5]). Alternatively, Hamiltonians parameterized by a continuous variable, such as X cos φ + Y sin φ, might for instance be represented by ([], [φ]). The second element indexes the subsystem on which the generator acts on.
ms.openlocfilehash: 762dac81ea0963443f0338cea1b879856c84b0ff
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858372"
---
# <a name="generatorindex-user-defined-type"></a>Tipo definito dall'utente GeneratorIndex

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta un singolo termine primitivo nel set di tutti i generatori dinamici, ad esempio operatori hermitiane, per i quali esiste una mappa da tale generatore a Time-Evolution da parte del generatore, fino a `EvolutionSet` .

Il primo elemento (int [], Double []) è indicizzato con un solo termine, ad esempio, la stringa di Pauli XXY con coefficient 0,5 verrebbe indicizzata da ([1, 1, 2], [0,5]). In alternativa, è possibile che i parametri hamiltonians da una variabile continua, ad esempio X cos φ + Y sin φ, siano rappresentati da ([], [φ]). Il secondo elemento indicizza il sottosistema su cui agisce il generatore.

```qsharp

newtype GeneratorIndex = ((Int[], Double[]), Int[]);
```



## <a name="example"></a>Esempio

Utilizzando  <xref:microsoft.quantum.simulation.paulievolutionset> , l'operatore $ \pi X_2 X_5 Y_9 $ è rappresentato come:

```qsharp
let index = GeneratorIndex(([1, 1, 2], [PI()]), [2, 5, 9]);
```

## <a name="remarks"></a>Commenti

> [!WARNING]
> L'interpretazione di un oggetto `GeneratorIndex` non è definita ad eccezione del riferimento a un determinato set di generatori.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Simulation. EvolutionSet](xref:Microsoft.Quantum.Simulation.EvolutionSet)
- [Microsoft. Quantum. Simulation. PauliEvolutionSet](xref:Microsoft.Quantum.Simulation.PauliEvolutionSet)