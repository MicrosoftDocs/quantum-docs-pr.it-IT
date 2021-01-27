---
uid: Microsoft.Quantum.Canon.ControlledOnBitString
title: ControlledOnBitString (funzione)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ControlledOnBitString
qsharp.summary: Returns a unitary operation that applies an oracle on the target register if the control register state corresponds to a specified bit mask.
ms.openlocfilehash: 176170cc972ca67b812b84f79cf97ba5418be9b6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840811"
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



## <a name="example"></a>Esempio

I frammenti di codice seguenti sono equivalenti:

```qsharp
(ControlledOnBitString(bits, oracle))(controlRegister, targetRegister);
```

e

```qsharp
within {
    ApplyPauliFromBitString(PauliX, false, bits, controlRegister);
} apply {
    Controlled oracle(controlRegister, targetRegister);
}
```

Il codice seguente prepara uno stato $ \frac {1} {2} (\ket {00} -\ket {01} + \ket {10} + \ket {11} ) $:

```qsharp
using (register = Qubit[2]) {
    ApplyToEach(H, register);
    (ControlledOnBitString([false], Z))(register[0..0], register[1]);
}
```

## <a name="remarks"></a>Commenti

Il modello fornito da `bits` può essere più breve di `controlRegister` , nel qual caso i qubits di controllo aggiuntivi vengono ignorati, ovvero non sono controllati in $ \ket {0} $ né $ \ket {1} $.
Se `bits` è più lungo di `controlRegister` , viene generato un errore.

Data una matrice booleana `bits` e un'operazione unitaria `oracle` , l'output di questa funzione è un'operazione che esegue i passaggi seguenti:

* applicare un' `X` operazione a ogni qubit del registro di controllo che corrisponde all' `false` elemento di `bits` ;
* applicare `Controlled oracle` ai registri di controllo e di destinazione;
* applicare un' `X` operazione a ogni qubit del registro di controllo che corrisponde all' `false` elemento di di `bits` nuovo per restituire il registro di controllo allo stato originale.

L'output del `Controlled` functor è un caso speciale di `ControlledOnBitString` Where `bits` è uguale a `[true, ..., true]` .