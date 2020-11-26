---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString (funzione)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 9435406506fc99fe211f5dce628b21c18ee4f9fe
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/26/2020
ms.locfileid: "96216660"
---
# <a name="controlledonbitstring-function"></a>ControlledOnBitString (funzione)

Spazio dei nomi: [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Pacchetto: [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Restituisce un'operazione unitaria che applica un oggetto Oracle nel registro di destinazione se lo stato del registro di controllo corrisponde a una maschera di bit specificata.

```qsharp
function ControlledOnBitString<'T> (bits : Bool[], oracle : ('T => Unit is Adj + Ctl)) : ((Qubit[], 'T) => Unit is Adj + Ctl)
```


## <a name="description"></a>Descrizione

L'output di questa funzione è un'operazione che può essere rappresentata da una trasformazione unitaria $U $ tale che \begin{align} U \ket{b_0 b_1 \cdots b_ {n-1}} \ket{\psi} = \ket{b_0 b_1 \cdots b_ {n-1}} \otimes \begin{cases} V \ket{\psi} & \textrm{if} (b_0 b_1 \cdots b_ {n-1}) = \texttt{bits} \\ \\ \ket{\psi} & \textrm{otherwise} \end{Cases}, \end{align} in cui $V $ è una trasformazione unitaria che rappresenta l'azione dell' `oracle` operazione.

## <a name="input"></a>Input

### <a name="bits--bool"></a>BITS: [bool](xref:microsoft.quantum.lang-ref.bool)[]

Stringa di bit per controllare l'operazione unitaria specificata su.


### <a name="oracle--t--unit--is-adj--ctl"></a>Oracle:' t => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione unitaria da applicare al registro di destinazione.



## <a name="output--qubitt--unit--is-adj--ctl"></a>Output: ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],' t) => [unità](xref:microsoft.quantum.lang-ref.unit)  è ADJ + CTL

Operazione unitaria che si applica al `oracle` Registro di destinazione se lo stato del registro di controllo corrisponde alla maschera di bit `bits` .

## <a name="type-parameters"></a>Parametri di tipo

### <a name="t"></a>T



## <a name="remarks"></a>Commenti

Il modello fornito da `bits` può essere più breve di `controlRegister` , nel qual caso i qubits di controllo aggiuntivi vengono ignorati, ovvero non sono controllati in $ \ket {0} $ né $ \ket {1} $.
Se `bits` è più lungo di `controlRegister` , viene generato un errore.

Data una matrice booleana `bits` e un'operazione unitaria `oracle` , l'output di questa funzione è un'operazione che esegue i passaggi seguenti:

* applicare un' `X` operazione a ogni qubit del registro di controllo che corrisponde all' `false` elemento di `bits` ;
* applicare `Controlled oracle` ai registri di controllo e di destinazione;
* applicare un' `X` operazione a ogni qubit del registro di controllo che corrisponde all' `false` elemento di di `bits` nuovo per restituire il registro di controllo allo stato originale.

L'output del `Controlled` functor è un caso speciale di `ControlledOnBitString` Where `bits` è uguale a `[true, ..., true]` .