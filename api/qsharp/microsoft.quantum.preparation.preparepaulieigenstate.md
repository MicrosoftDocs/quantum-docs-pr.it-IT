---
uid: Microsoft.Quantum.Preparation.PreparePauliEigenstate
title: Operazione PreparePauliEigenstate
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PreparePauliEigenstate
qsharp.summary: Prepares a qubit in the positive eigenstate of a given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.
ms.openlocfilehash: b24852bb3a455a9fe04b3535156d0c3dfb1a7d12
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96193693"
---
# <a name="preparepaulieigenstate-operation"></a>Operazione PreparePauliEigenstate

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prepara un qubit nell'autostato positivo di un determinato operatore di Pauli.
Se viene specificato l'operatore di identità, il qubit viene preparato nello stato massimo misto.

```qsharp
operation PreparePauliEigenstate (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="description"></a>Descrizione

Se il qubit inizialmente si trovava nello stato $ \ket {0} $, questa operazione prepara il qubit in $ + $1 autostato di un determinato operatore Pauli oppure, per `PauliI` , nello stato massimo misto (vedere <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Se il valore di qubit si trovava in uno stato diverso da $ \ket {0} $, questa operazione applica le seguenti attività di controllo: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ per `PauliZ` e <xref:microsoft.quantum.preparation.preparesinglequbitidentity> per `PauliI` .

## <a name="input"></a>Input

### <a name="basis--pauli"></a>base: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Un operatore Pauli $P $.


### <a name="qubit--qubit"></a>Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit da preparare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

