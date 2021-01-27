---
uid: Microsoft.Quantum.ErrorCorrection.KnillDistill
title: Operazione KnillDistill
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.ErrorCorrection
qsharp.name: KnillDistill
qsharp.summary: Implements the Knill magic state distillation algorithm.
ms.openlocfilehash: 4eff99eebb1e271d240513f827c6e93973ef79a6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853110"
---
# <a name="knilldistill-operation"></a>Operazione KnillDistill

Spazio dei nomi: [Microsoft. Quantum. ErrorCorrection](xref:Microsoft.Quantum.ErrorCorrection)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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