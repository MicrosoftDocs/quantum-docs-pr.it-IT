---
uid: Microsoft.Quantum.Intrinsic.Rz
title: Operazione RZ
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Rz
qsharp.summary: >-
  Applies a rotation about the $z$-axis by a given angle.

  \begin{align} R_z(\theta) \mathrel{:=} e^{-i \theta \sigma_z / 2} = \begin{bmatrix} e^{-i \theta / 2} & 0 \\\\ 0 & e^{i \theta / 2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 954b0b097d4bffcb8047a9f0c8a4c28445653c5d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720867"
---
# <a name="rz-operation"></a>Operazione RZ

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Applica una rotazione sull'asse di $z $ da un angolo specificato.

\begin{align} R_z (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_z/2} = \begin{Bmatrix} e ^ {-i \theta/2} & 0 \\ \\ 0 & e ^ {i \theta/2} \end{Bmatrix}.
\end{align}

```qsharp
operation Rz (theta : Double, qubit : Qubit) : Unit
```


## <a name="input"></a>Input

### <a name="theta--double"></a>Theta: [Double](xref:microsoft.quantum.lang-ref.double)

Angolo per la rotazione del qubit.


### <a name="qubit--qubit"></a>Qubit: [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit a cui deve essere applicato il controllo.



## <a name="output--unit"></a>Output: [unità](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Commenti

Equivalente a:

```qsharp
R(PauliZ, theta, qubit);
```