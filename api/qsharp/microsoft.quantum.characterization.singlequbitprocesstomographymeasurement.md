---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Operazione SingleQubitProcessTomographyMeasurement
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 34e5143d5be316ee42a63124d35475949db0a692
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92714927"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a>Operazione SingleQubitProcessTomographyMeasurement

Spazio dei nomi: [Microsoft. Quantum. characteration](xref:Microsoft.Quantum.Characterization)

Pacchetto [](https://nuget.org/packages/)


Esegue una misurazione della tomografia del processo qubit singolo in base a Pauli, dato un canale specifico di interesse.

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a>Input

### <a name="preparation--pauli"></a>preparazione: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

L'elemento di base di Pauli $P $ in cui deve essere preparato un qubit.


### <a name="measurement--pauli"></a>misurazione: [Pauli](xref:microsoft.quantum.lang-ref.pauli)

L'elemento di base di Pauli $Q $ in cui è necessario misurare un qubit.


### <a name="channel--qubit--unit"></a>canale: [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [unità](xref:microsoft.quantum.lang-ref.unit) qubit 

Un singolo canale qubit $ \Lambda $ il cui comportamento viene stimato con la tomografia del processo.



## <a name="output--__invalidresult__"></a>Output: __non <Result> valido__

Risultato `Zero` con probabilità $ $ \Begin{align} \Pr (\texttt{zero} | \Lambda; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).
\end{align} $ $

## <a name="remarks"></a>Commenti

La distribuzione dei risultati restituiti da questa operazione è un caso speciale di tomografia a due qubit di stato. Let $ \rho = J (\Lambda)/$2 è lo stato Choi-Jamiłkowski per $ \Lambda $. Quindi, la distribuzione precedente è identica a $ $ \begin{align} \Pr (\texttt{Zero} | \rho; M) = \operatorname{Tr} (M \rho), \end{align} $ $ where $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 è la misura effettiva corrispondente a $P $ e $Q $.