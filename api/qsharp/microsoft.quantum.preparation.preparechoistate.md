---
uid: Microsoft.Quantum.Preparation.PrepareChoiState
title: Operazione PrepareChoiState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareChoiState
qsharp.summary: Prepares the Choi–Jamiołkowski state for a given operation onto given reference and target registers.
ms.openlocfilehash: cb34078c09f8c28b5b9bbda1bae6936d13ffcc78
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854397"
---
# <a name="preparechoistate-operation"></a>Operazione PrepareChoiState

Spazio dei nomi: [Microsoft. Quantum. Preparation](xref:Microsoft.Quantum.Preparation)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Prepara lo stato Choi-Jamiołkowski per una determinata operazione sui registri di riferimento e di destinazione specificati.

```qsharp
operation PrepareChoiState (op : (Qubit[] => Unit), reference : Qubit[], target : Qubit[]) : Unit
```


## <a name="input"></a>Input

### <a name="op--qubit--unit"></a>op: [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unità](xref:microsoft.quantum.lang-ref.unit)> 

Operazione $ \Lambda $ la cui proprietà Choi – Jamiołkowski state $J (\Lambda)/2 ^ N $ deve essere preparata, dove $N $ è il numero di qubits su cui `op` agisce.


### <a name="reference--qubit"></a>riferimento: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro di qubits che inizia nello stato $ \ket{00\cdots 0} $ da usare come riferimento per l'azione di `op` .


### <a name="target--qubit"></a>destinazione: [qubit](xref:microsoft.quantum.lang-ref.qubit)[]

Un registro di qubits inizialmente nello stato $ \ket{00\cdots 0} $ in cui deve `op` essere applicato.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Il $J di stato Choi-Jamiłkowski (\Lambda) $ di un processo quantum è definito come $ $ \begin{align} J (\Lambda) \mathrel{: =} (\boldone \otimes \Lambda) (| \boldone\rangle \! \rangle\langle \! \langle\boldone |), \end{align} $ $ where $ | X\rangle \! \rangle $ è la *vettorizzazione* di una matrice $X $ nella convenzione di stack di colonne. L'apprendimento di una descrizione classica di questo stato fornisce informazioni complete sull'effetto di $ \Lambda $ che agisce sugli stati di input arbitrari e costituisce la base della *tomografia del processo quantum*.

## <a name="see-also"></a>Vedere anche

- [Microsoft. Quantum. preping. PrepareChoiStateA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateA)
- [Microsoft. Quantum. preping. PrepareChoiStateC](xref:Microsoft.Quantum.Preparation.PrepareChoiStateC)
- [Microsoft. Quantum. preping. PrepareChoiStateCA](xref:Microsoft.Quantum.Preparation.PrepareChoiStateCA)