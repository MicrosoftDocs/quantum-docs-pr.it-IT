---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204063"
---
# <a name="isnotzero-function"></a>IsNotZero (funzione)

Spazio dei nomi: [Microsoft. Quantum. Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacchetto: [Microsoft. Quantum. Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Verifica se un `Double` numero non è approssimativamente pari a zero.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Input

### <a name="number--double"></a>numero: [Double](xref:microsoft.quantum.lang-ref.double)

Numero da controllare



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

Restituisce true se il `number` valore assoluto di è maggiore di `1e-15` .