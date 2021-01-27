---
uid: Microsoft.Quantum.Synthesis.DecomposedOn
title: DecomposedOn (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: DecomposedOn
qsharp.summary: Decomposes a permutation on a variable
ms.openlocfilehash: fb7aa5af8f3eb07399e0d2dd2d50723f4e6b169a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855521"
---
# <a name="decomposedon-function"></a>DecomposedOn (funzione)

Spazio dei nomi: [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Scompone una permutazione su una variabile

```qsharp
function DecomposedOn (perm : Int[], index : Int) : ((Int[], Int[]), Int[])
```


## <a name="description"></a>Descrizione

Data una permutazione $ \Pi $ ( `perm` ) e un indice $i $ ( `index` ), questo metodo restituisce tre permutazioni $ ((\ pi_l, \ pi_r), \Pi ') $ in modo tale che le immagini di $ \ pi_l $ e $ \ pi_r $ non modifichino i bit nei rispettivi elementi a indici diversi da $i $ e immagini di $ \Pi ' $ non cambiano bit $i $ nei relativi elementi.

## <a name="input"></a>Input

### <a name="perm--int"></a>Perm: [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="index--int"></a>Indice: [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--intintint"></a>Output: (([int](xref:microsoft.quantum.lang-ref.int)[],[int](xref:microsoft.quantum.lang-ref.int)[]),[int](xref:microsoft.quantum.lang-ref.int)[])



## <a name="example"></a>Esempio

Si supponga che l'input sia Perm = [0, 2, 3, 5, 7, 1, 4, 6] e index = 0, quindi questa funzione calcola tre permutazioni in base alla tabella seguente, che elenca la permutazione `perm` nella notazione binaria con gli elementi del gruppo a e le immagini nel gruppo D.  Le colonne elencano gli indici di bit.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 |       |       | 0 0 0 | 0
| 0 0 1 |       |       | 0 1 0 | 2
| 0 1 0 |       |       | 0 1 1 | 3
| 0 1 1 |       |       | 1 0 1 | 5
| 1 0 0 |       |       | 1 1 1 | 7
| 1 0 1 |       |       | 0 0 1 | 1
| 1 1 0 |       |       | 1 0 0 | 4
| 1 1 1 |       |       | 1 1 0 | 6

Tutti i valori per gli indici non uguali a 0 (= index) vengono copiati da a a B e da D a C.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0   | 0 0   | 0 0 0 |
| 0 0 1 | 0 0   | 0 1   | 0 1 0 |
| 0 1 0 | 0 1   | 0 1   | 0 1 1 |
| 0 1 1 | 0 1   | 1 0   | 1 0 1 |
| 1 0 0 | 1 0   | 1 1   | 1 1 1 |
| 1 0 1 | 1 0   | 0 0   | 0 0 1 |
| 1 1 0 | 1 1   | 1 0   | 1 0 0 |
| 1 1 1 | 1 1   | 1 1   | 1 1 0 |

Viene quindi inserito un valore 0 per il primo elemento con un indice vuoto nella colonna 0 del blocco B, quindi un valore 1 viene inserito in B dove il prefisso corrisponde a (nel primo caso l'altra riga con indici 0 0).
Successivamente, un valore 1 viene aggiunto nella stessa riga del blocco C e quindi 0 per il prefisso corrispondente nel blocco C.  Questo processo viene ripetuto fino a quando tutti gli indici non sono stati inseriti nella colonna 0 nei blocchi B e C.

|   A |   B |   C |   D |
| 2 1 0 | 2 1 0 | 2 1 0 | 2 1 0 |
|-------|-------|-------|-------|
| 0 0 0 | 0 0 0 | 0 0 0 | 0 0 0 |
| 0 0 1 | 0 0 1 | 0 1 1 | 0 1 0 |
| 0 1 0 | 0 1 0 | 0 1 0 | 0 1 1 |
| 0 1 1 | 0 1 1 | 1 0 1 | 1 0 1 |
| 1 0 0 | 1 0 0 | 1 1 0 | 1 1 1 |
| 1 0 1 | 1 0 1 | 0 0 1 | 0 0 1 |
| 1 1 0 | 1 1 0 | 1 0 0 | 1 0 0 |
| 1 1 1 | 1 1 1 | 1 1 1 | 1 1 0 |

È possibile leggere tre nuove permutazioni dalla tabella:

- $ \ pi_l $ con elementi in un oggetto, immagini in B (a sinistra)
- $ \ pi_r $ con elementi in D, immagini in C (a destra)
- $ \Pi ' $ con elementi in B, immagini in C (resto)

Si noti che i valori di bit di progettazione non cambiano in $ \ pi_l $ e $ \ pi_r $ per gli indici 1 e 2 e i valori di bit non cambiano per in $ \ pi_' $ per index 0.  Si noti inoltre che $ \ pi_l $ e $ \ pi_r $ devono essere autonomi.

Le permutazioni derivate e restituite sono: Left = [0, 1, 2, 3, 4, 5, 6, 7] right = [0, 1, 3, 2, 4, 5, 7, 6] resto = [0, 3, 2, 5, 6, 1, 4, 7]