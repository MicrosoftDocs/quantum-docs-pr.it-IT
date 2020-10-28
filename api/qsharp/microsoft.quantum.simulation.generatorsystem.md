---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definito dall'utente GeneratorSystem
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: c03caf99b197410c7fa15021c8acaaf55a728781
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724563"
---
# <a name="generatorsystem-user-defined-type"></a>Tipo definito dall'utente GeneratorSystem

Spazio dei nomi: [Microsoft. Quantum. Simulation](xref:Microsoft.Quantum.Simulation)

Pacchetto [](https://nuget.org/packages/)


Rappresenta una raccolta di `GeneratorIndex` es.

Viene eseguita l'iterazione della raccolta usando un Integer a indice singolo e la dimensione della raccolta si presuppone che sia nota.

```qsharp

newtype GeneratorSystem = (Int, (Int -> Microsoft.Quantum.Simulation.GeneratorIndex));
```



## <a name="remarks"></a>Commenti

`GeneratorSystem`È possibile definire facilmente le istanze di utilizzando la <xref:microsoft.quantum.arrays.lookupfunction> funzione.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. Arrays. LookupFunction](xref:Microsoft.Quantum.Arrays.LookupFunction)