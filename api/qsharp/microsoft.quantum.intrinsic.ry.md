---
uid: Microsoft.Quantum.Intrinsic.Ry
title: Operazione ry
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Intrinsic
qsharp.name: Ry
qsharp.summary: >-
  Applies a rotation about the $y$-axis by a given angle.

  \begin{align} R_y(\theta) \mathrel{:=} e^{-i \theta \sigma_y / 2} = \begin{bmatrix} \cos \frac{\theta}{2} & -\sin \frac{\theta}{2}  \\\\ \sin \frac{\theta}{2} & \cos \frac{\theta}{2} \end{bmatrix}. \end{align}
ms.openlocfilehash: 9966693eb7283e855f7b72e910aa3604d6c2bd61
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2020
ms.locfileid: "92720006"
---
# <a name="ry-operation"></a>Operazione ry

Spazio dei nomi: [Microsoft. Quantum. Intrinsic](xref:Microsoft.Quantum.Intrinsic)

Pacchetto [](https://nuget.org/packages/)


Applica una rotazione sull'asse di $y $ da un angolo specificato.

\begin{align} R_y (\theta) \mathrel{: =} e ^ {-i \theta \ sigma_y/2} = \begin{Bmatrix} \cos \frac{\theta} {2} &-\sin \frac{\theta} {2} \\ \\ \sin \frac{\theta} {2} & \cos \frac{\theta} {2} \end{Bmatrix}.  
\end{align}

```qsharp
operation Ry (theta : Double, qubit : Qubit) : Unit
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
R(PauliY, theta, qubit);
```