---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 9384e5dafd4b5b7d44cb348c9537ebc2c621466d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839590"
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