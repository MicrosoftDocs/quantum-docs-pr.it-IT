---
uid: Microsoft.Quantum.Arrays.CumulativeFolded
title: CumulativeFolded (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: CumulativeFolded
qsharp.summary: Combines Mapped and Fold into a single function
ms.openlocfilehash: a09c2779c8f06d8f6b7b0902366f3cefbbca4525
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92719394"
---
# <a name="cumulativefolded-function"></a>CumulativeFolded (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


Combina il mapping e il ripiego in una singola funzione

```qsharp
function CumulativeFolded<'State, 'T> (fn : (('State, 'T) -> 'State), state : 'State, array : 'T[]) : 'State[]
```


## <a name="description"></a>Descrizione

Questa funzione esegue l'iterazione della `fn` funzione attraverso la matrice, iniziando da uno stato iniziale `state` e restituisce tutti i valori intermedi, escluso lo stato iniziale.

## <a name="input"></a>Input

### <a name="fn--statet---state"></a>FN: (' state,' t')->' stato

Funzione da ripiegare sulla matrice


### <a name="state--state"></a>stato:' stato

Stato iniziale da ripiegare


### <a name="array--t"></a>matrice:' t []

Matrice di valori da ripiegare



## <a name="output--state"></a>Output:' stato []

Tutti gli stati intermedi, incluso lo stato finale, ma non lo stato iniziale.
La lunghezza della matrice di output è uguale a quella di `array` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="state"></a>' Stato

Tipo di stati `fn` su cui opera la funzione, ovvero accetta come primo input e restituisce.
### <a name="t"></a>T

Tipo di `array` elementi.