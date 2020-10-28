---
uid: Microsoft.Quantum.Preparation.PrepareQubit
title: Operazione PrepareQubit
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareQubit
qsharp.summary: >-
  Prepares a qubit in the +1 (`Zero`) eigenstate of the given Pauli operator. If the identity operator is given, then the qubit is prepared in the maximally mixed state.

  If the qubit was initially in the $\ket{0}$ state, this operation prepares the qubit in the $+1$ eigenstate of a given Pauli operator, or, for `PauliI`, in the maximally mixed state instead (see <xref:microsoft.quantum.preparation.preparesinglequbitidentity>).

  If the qubit was in a state other than $\ket{0}$, this operation applies the following gates: $H$ for `PauliX`, $HS$ for `PauliY`, $I$ for `PauliZ` and <xref:microsoft.quantum.preparation.preparesinglequbitidentity> for `PauliI`.
ms.openlocfilehash: 5f42bf26a8f9638ea88c035a18846050c3776b45
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92723009"
---
# <a name="preparequbit-operation"></a>Operazione PrepareQubit

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto [](https://nuget.org/packages/)


Prepara un qubit in autostato + 1 ( `Zero` ) dell'operatore Pauli specificato.
Se viene specificato l'operatore di identità, il qubit viene preparato nello stato massimo misto.

Se il qubit inizialmente si trovava nello stato $ \ket {0} $, questa operazione prepara il qubit in $ + $1 autostato di un determinato operatore Pauli oppure, per `PauliI` , nello stato massimo misto (vedere <xref:microsoft.quantum.preparation.preparesinglequbitidentity> ).

Se il valore di qubit si trovava in uno stato diverso da $ \ket {0} $, questa operazione applica le seguenti attività di controllo: $H $ for `PauliX` , $HS $ for `PauliY` , $I $ per `PauliZ` e <xref:microsoft.quantum.preparation.preparesinglequbitidentity> per `PauliI` .

```qsharp
operation PrepareQubit (basis : Pauli, qubit : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="basis--pauli"></a>base: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Un operatore Pauli $P $.


### <a name="qubit--qubit"></a>Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit da preparare.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)

