---
uid: Microsoft.Quantum.Random.DrawRandomPauli
title: Operazione DrawRandomPauli
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomPauli
qsharp.summary: Draws a random Pauli value.
ms.openlocfilehash: 2b6c4417ac462c57db83446a6afad29091005ad7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724647"
---
# <a name="drawrandompauli-operation"></a>Operazione DrawRandomPauli

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


Disegna un valore di Pauli casuale.

```qsharp
operation DrawRandomPauli () : Pauli
```


## <a name="output--pauli"></a>Output: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

`PauliI`,, `PauliX` `PauliY` O `PauliZ` con uguale probabilità.