---
uid: Microsoft.Quantum.Simulation.GeneratorSystem
title: Tipo definito dall'utente GeneratorSystem
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: GeneratorSystem
qsharp.summary: >-
  Represents a collection of `GeneratorIndex`es.

  We iterate over this collection using a single-index integer, and the size of the collection is assumed to be known.
ms.openlocfilehash: 3748d3fb79597fb526c86a91bc28290155189014
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98858416"
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