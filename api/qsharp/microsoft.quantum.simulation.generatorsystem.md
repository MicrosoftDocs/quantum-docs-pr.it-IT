---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definito dall'utente GeneratorSystem
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 20092a8deca50c90f46f4d79c6b40b805f135754
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225228"
---
# <a name="generatorsystem-user-defined-type"></a>Tipo definito dall'utente GeneratorSystem

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Rappresenta una raccolta di `GeneratorIndex` es.

Viene eseguita l'iterazione della raccolta usando un Integer a indice singolo e la dimensione della raccolta si presuppone che sia nota.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Commenti

`GeneratorSystem`È possibile definire facilmente le istanze di utilizzando la <xref:microsoft.quantum.arrays.lookupfunction> funzione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)