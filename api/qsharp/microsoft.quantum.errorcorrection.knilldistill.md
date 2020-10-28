---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operazione KnillDistill
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 1135db83cf750918347df10c6f1301b636aaee0c
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92712281"
---
# <a name="knilldistill-operation"></a>Operazione KnillDistill

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto [](https://nuget.org/packages/)


Implementa l'algoritmo di distillazione Magic state Knill.

```qsharp
operation KnillDistill (roughMagic : Qubit[]) : Bool
```


## <a name="description"></a>Descrizione

Date le 15 copie approssimative di uno stato magico $ $ \begin{align} \cos\frac{\Pi} {8} \ket {0} + \sin \frac{\Pi} {8} \ket {1} \end{align}, $ $ produce una copia di qualità superiore.

## <a name="input"></a>Input

### <a name="roughmagic--qubit"></a>roughMagic: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro di quindici qubits contenenti copie approssimative di uno stato magico. L'applicazione seguente di questa procedura di distillazione conterrà `roughMagic[0]` una copia di qualità superiore e il resto del registro verrà reimpostato sullo stato $ \ket{00\cdots 0} $.



## <a name="output--bool"></a>Output: [bool](xref:microsoft.quantum.lang-ref.bool)

Se `true` , la procedura è stata completata e la copia di qualità superiore deve essere accettata. Se `false` , la procedura ha avuto esito negativo e lo stato del registro deve essere considerato non definito.

## <a name="remarks"></a>Commenti

Si segue l'algoritmo di Knill.
Tuttavia, l'implementazione attuale è lungi dall'essere ottimale, perché usa un numero eccessivo di qubits.
Gli stati magici vengono inseriti in questa routine, nel qual caso sono disponibili protocolli migliori.

## <a name="references"></a>Riferimenti

- [Knill](https://arxiv.org/abs/quant-ph/0402171)