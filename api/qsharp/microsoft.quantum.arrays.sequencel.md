---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Sequencel (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: 7e3c5c31428f9be152e28afbe478a3d15eb0a56c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850978"
---
# <a name="sequencel-function"></a>Sequencel (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Ottiene una matrice di numeri interi in un intervallo specificato.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Input

### <a name="from--bigint"></a>da: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Indice di inizio inclusivo dell'intervallo.


### <a name="to--bigint"></a>a: [bigint](xref:microsoft.quantum.lang-ref.bigint)

Indice finale inclusivo dell'intervallo non più piccolo di `from` .



## <a name="output--bigint"></a>Output: [bigint](xref:microsoft.quantum.lang-ref.bigint)[]

Matrice contenente la sequenza di numeri,,... `from` `from + 1` , `to` .

## <a name="example"></a>Esempio

```qsharp
let arr1 = SequenceL(0L, 3L); // [0L, 1L, 2L, 3L]
let arr2 = SequenceL(23L, 29L); // [23L, 24L, 25L, 26L, 27L, 28L, 29L]
let arr3 = SequenceL(-5L, -2L); // [-5L, -4L, -3L, -2L]
```

## <a name="remarks"></a>Commenti

La differenza tra `from` e `to` deve rientrare in un `Int` valore.