---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Sequencel (funzione)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92718878"
---
# <a name="sequencel-function"></a>Sequencel (funzione)

Spazio dei nomi: [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Pacchetto [](https://nuget.org/packages/)


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

## <a name="remarks"></a>Commenti

La differenza tra `from` e `to` deve rientrare in un `Int` valore.