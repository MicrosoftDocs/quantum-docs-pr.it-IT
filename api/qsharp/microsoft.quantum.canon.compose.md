---
uid: Microsoft.Quantum.Canon.Compose
title: Compose (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Compose
qsharp.summary: Returns the composition of two functions.
ms.openlocfilehash: 02cff7eef4d55d27d5d72e6219a90b7d8f5beb3b
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92716495"
---
# <a name="compose-function"></a>Compose (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto [](https://nuget.org/packages/)


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