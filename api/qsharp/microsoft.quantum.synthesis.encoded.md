---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Funzione codificata
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855488"
---
# <a name="encoded-function"></a>Funzione codificata

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Codifica della tabella di verità nella {1,-1} codifica

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>Input

### <a name="table--bool"></a>tabella: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Tabella di verità come matrice di valori di verità



## <a name="output--int"></a>Output: [int](xref:microsoft.quantum.lang-ref.int)[]

Tabella di verità come matrice di {1,-1} numeri interi

## <a name="example"></a>Esempio

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```