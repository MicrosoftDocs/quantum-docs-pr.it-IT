---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Operazione DrawRandomBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853682"
---
# <a name="drawrandombool-operation"></a>Operazione DrawRandomBool

Spazio dei nomi: [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Pacchetto: [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Data la probabilità di esito positivo, restituisce una singola versione di valutazione di Bernoulli che è true con la probabilità specificata.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Input

### <a name="successprobability--double"></a>successProbability: [Double](xref:microsoft.quantum.lang-ref.double)

Probabilità con la quale `true` deve essere restituito.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

`true` con probabilità `successProbability` e `false` con probabilità `1.0 - successProbability` .

## <a name="example"></a>Esempio

Il seguente esempio di frammento di codice Q # esegue il capovolgimento da una moneta distorta:

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```