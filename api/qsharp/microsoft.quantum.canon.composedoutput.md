---
uid: Microsoft.Quantum.Canon.ComposedOutput
title: ComposedOutput (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ComposedOutput
qsharp.summary: Returns the output of the composition of `inner` and `outer` for a given input.
ms.openlocfilehash: 4da66616692055a7d60abbf1fac6e6799806675d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716484"
---
# <a name="composedoutput-function"></a>ComposedOutput (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


Restituisce l'output della composizione di `inner` e `outer` per un input specificato.

```qsharp
function ComposedOutput<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U), target : 'T) : 'V
```


## <a name="input"></a>Input

### <a name="outer--u---v"></a>Outer:' U->' V




### <a name="inner--t---u"></a>Inner: t->' U




### <a name="target--t"></a>destinazione:' t





## <a name="output--v"></a>Output:' V



## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T


### <a name="u"></a>' U


### <a name="v"></a>' V

