---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Operazione PrepareSingleQubitIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 12a650568aa5682e8fb6498808d188b154527acb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92724885"
---
# <a name="preparesinglequbitidentity-operation"></a>Operazione PrepareSingleQubitIdentity

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto [](https://nuget.org/packages/)


Prepara un qubit nello stato massimo misto.

Prepara il qubit specificato nello stato $ \boldone/$2 applicando il canale depolarizzato $ $ \begin{align} \Omega (\rho) \mathrel{: =} \frac {1} {4} \ Sum_ {\mu \In \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ where $ \sigma \_ i $ is the $i $ th operatore Pauli e Where $ \rho $ è un operatore di densità che rappresenta uno stato misto.

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="qubit--qubit"></a>Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Un qubit il cui stato deve essere depolarizzato nel modo descritto in precedenza.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Lo stato misto $ \boldone/$2 che descrive il risultato dell'applicazione di questa operazione a uno stato descrive in modo implicito un valore previsto rispetto a scelte casuali eseguite in questa operazione.
Pertanto, per ogni singola applicazione, questa operazione esegue il mapping degli Stati puri agli Stati puri, ma funziona come descritto in expecting.
In particolare, questa operazione può essere utilizzata nella tomografia del processo per misurare i componenti *non unitari* di un canale.