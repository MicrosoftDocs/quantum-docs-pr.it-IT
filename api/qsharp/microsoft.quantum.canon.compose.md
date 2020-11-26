---
uid: Microsoft.Quantum.Canon.Compose
title: Compose (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: f8c6ad36220b48be1723c2d91cbf7c0a4947af14
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216762"
---
# <a name="compose-function"></a>Compose (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce la composizione di due funzioni.

```qsharp
function Compose<'T, 'U, 'V> (outer : ('U -> 'V), inner : ('T -> 'U)) : ('T -> 'V)
```


## <a name="description"></a>Descrizione

Date due funzioni $f $ e $g $, restituisce una nuova funzione che rappresenta $f \circ g $.

## <a name="input"></a>Input

### <a name="outer--u---v"></a>Outer:' U->' V

Seconda funzione da applicare.


### <a name="inner--t---u"></a>Inner: t->' U

Prima funzione da applicare.



## <a name="output--t---v"></a>Output:' t->' V

Una nuova funzione $h $ tale che per tutti gli input $x $, $f (g (x)) = h (x) $.

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T

Tipo di input della prima funzione da applicare.
### <a name="u"></a>' U

Il tipo di output della prima funzione da applicare e il tipo di input della seconda funzione da applicare.
### <a name="v"></a>' V

Tipo di output della seconda funzione da applicare.