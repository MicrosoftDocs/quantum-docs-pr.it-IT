---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operazione DrawRandomBool
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 05cf8ad939691aac90625c5d056ea79aa062f553
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720279"
---
# <a name="drawrandombool-operation"></a>Operazione DrawRandomBool

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto [](https://nuget.org/packages/)


Data la probabilità di esito positivo, restituisce una singola versione di valutazione di Bernoulli che è true con la probabilità specificata.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Input

### <a name="successprobability--double"></a>successProbability: [Double](xref:microsoft.quantum.lang-ref.double)

Probabilità con la quale `true` deve essere restituito.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` con probabilità `successProbability` e `false` con probabilità `1.0 - successProbability` .