---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714829"
---
# <a name="isnotzero-function"></a>IsNotZero (funzione)

Spazio dei nomi: [Microsoft. Quantum. Chemistry](xref:Microsoft.Quantum.Chemistry)

Pacchetto [](https://nuget.org/packages/)


Verifica se un `Double` numero non è approssimativamente pari a zero.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Input

### <a name="number--double"></a>numero: [Double](xref:microsoft.quantum.lang-ref.double)

Numero da controllare



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

Restituisce true se il `number` valore assoluto di è maggiore di `1e-15` .