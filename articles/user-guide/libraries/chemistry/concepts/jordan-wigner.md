---
title: Rappresentazione di Jordan-Wigner
description: Informazioni sulla rappresentazione Giordania-Wigner, che esegue il mapping degli operatori hamiltoniana a matrici unitarie che possono essere implementate più facilmente in un computer Quantum.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
no-loc:
- Q#
- $$v
ms.openlocfilehash: 29abb4d2ef11239a58af45bc4eee3bd60d20a6c7
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833860"
---
# <a name="jordan-wigner-representation"></a>Rappresentazione di Jordan-Wigner

Sebbene la seconda hamiltonians quantizzata sia opportunamente rappresentata in termini di $a ^ \dagger $ (Creation) e $a $ (annichilimento), queste operazioni non sono operazioni fondamentali nei computer Quantum.
Di conseguenza, se si desidera implementarli in un computer quantistico, è necessario eseguire il mapping degli operatori a matrici unitarie che possono essere implementate in un computer Quantum.
La rappresentazione Giordania-Wigner fornisce una mappa di questo tipo.
Tuttavia, altri, come la rappresentazione Bravyi – Kitaev, esistono anche e presentano vantaggi e svantaggi relativi.
Il vantaggio principale della rappresentazione di Jordan-Wigner è la sua semplicità.

La rappresentazione Giordania-Wigner è diretta a derivare.
Si tenga presente che uno stato $ \ket {0} _J $ implica che la rotazione orbitale $j $ è vuota e $ \ket {1} _J $ implica che è occupata.
Ciò significa che qubits può archiviare naturalmente il lavoro di un dato orbitale di rotazione.
Si avrà quindi $a ^ \ dagger_j \ket {0} _J = \ket {1} _J $ e $a ^ \ dagger_j \ket {1} _J = $0.
È facile verificare che \begin{align} a ^ \ dagger_j &= \begin{Bmatrix}0 & 0 \\ \ 1 &0 \end{Bmatrix} = \frac{X_j-iY_j} {2} , \nonumber \\ \\ a_j &= \begin{Bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} , \end{align} dove $X _J $ e $Y _J $ sono gli operatori di Pauli-$X $ e-$Y $ che operano su qubit $j $.

>[!NOTE]
> Nello Q# stato $ \ket {0} $ rappresenta il autostato + 1 dell'operatore $Z $. In alcune aree di fisica $ \ket {0} $ rappresenta lo stato di basso livello di energia e quindi il autostato-1 dell'operatore $Z $. Di conseguenza, alcune formule potrebbero differire dalla letteratura popolare.

Nella libreria di chimica viene usato $ \ket {0} $ per rappresentare uno spin-Orbital non occupato.
Ciò dimostra che per un singolo orbitale di rotazione è facile rappresentare gli operatori di creazione e annientamento in termini di matrici unitarie che i computer Quantum conoscono.
Si noti che, mentre $X $ e $Y $ sono Unity $a ^ \dagger $ e $a $ non lo sono.
In seguito si noterà che questo non costituisce una sfida per la simulazione.

Un problema che rimane è che, mentre la costruzione precedente funziona per un singolo Orbital di rotazione, l'operazione ha esito negativo per i sistemi con due o più orbitali di rotazione.
Poiché fermioni sono antisymmetic, sappiamo che $a ^ \ dagger_j a ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $ per qualsiasi $j $ e $k $.
Tuttavia, $ $ \left (\frac{X_j-iY_j} {2} \right) \left (\frac{X_k-iY_k} {2} \right) = \left (\frac{X_k-iY_k} {2} \right) \left (\frac{X_j-iY_j} {2} \right).
$ $ In altre parole, i due operatori di creazione non eseguono l'anti-disattivazione secondo necessità.
Questa operazione può essere risolta anche se in modo semplice, se non elegante.
La correzione consiste nel tenere presente che gli operatori di Pauli naturalmente non sono in grado di disattivare
In particolare, $XZ =-ZX $ e $YZ =-l'$.
Intercalando quindi $Z $ Operators nella costruzione dell'operatore, è possibile emulare la corretta anti-commutazione.
La costruzione completa è la seguente: 

\begin{align} a ^ \ dagger_1 &= \left (\frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_2 &= Z\otimes\left (\frac{X-iY} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_3 &= Z\otimes Z\otimes \left (\frac{X-iY} {2} \right) \otimes 1 \otimes \cdots \otimes 1, \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left (\frac{X-iY} {2} \right). \label{EQ: JW} \end{align}

È anche utile esprimere gli operatori numerici, $n _j $, in termini di operatori Pauli.
Fortunatamente, le stringhe di $Z $ Operators (note come stringhe Jordan-Wigner) vengono annullate dopo la sostituzione.
Dopo aver eseguito questa operazione (e aver richiamato il $X _jY_j = iZ_j $), abbiamo \begin{Equation} n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)} {2} .
\end{equation}


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a>Costruzione di hamiltonians nella rappresentazione Giordania-Wigner

Una volta richiamata la rappresentazione Giordania-Wigner che traduce l'hamiltoniana in una somma di operatori Pauli, è possibile procedere in modo semplice.
È sufficiente sostituire ogni $a ^ \dagger $ e $a $ Operators nell'Hamiltoniana fermioniche con le stringhe di Pauli-Operators indicate in precedenza.
Quando si esegue questa sostituzione, sono disponibili solo cinque classi di termini all'interno dell'hamiltoniana.
Queste cinque classi corrispondono ai diversi modi in cui è possibile selezionare l'$p, q $ e $p, q, r, s $ nel corpo di uno e i termini di due corpo nell'Hamiltoniana.
Queste cinque classi, nel caso in cui $p>q>r>s $ e gli orbitali con valori reali, siano

\begin{align} h_ {PP} A_p ^ \dagger A_p &= \ sum_p \frac{h_ {PP}} {2} (1-Z_p) \\ \\ h_ {PQ} (A_p ^ \dagger a_q + a ^ \ dagger_q A_p) &= \frac{h_ {PQ}} {2} \left (\ prod_ {j = q + 1} ^ {p-1} Z_j \right) \left (X_pX_q + Y_pY_q \right) \\ \\ h_ {pqqp} n_P n_q &= \frac{h_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{h_ {pqqr}} {2} \left (\ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r \right) \left (\frac{1-Z_q} {2} \right) \\ \\ H_ {PQRS} &= \frac{h_ {PQRS}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \Big (xxxx-xxyy + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}

Anche se la generazione di tali hamiltonians richiede solo l'applicazione di queste regole di sostituzione, questa operazione potrebbe non essere praticabile per le molecole di grandi dimensioni che possono essere costituite da milioni di termini hamiltoniana.
In alternativa, è possibile costruire automaticamente il `JordanWignerEncoding` dato una `FermionHamiltonian` rappresentazione dell'hamiltoniana.

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

Una volta che i hamiltonians vengono costruiti in questo formato, è possibile usare un host di algoritmi di simulazione quantistica per compilare le dinamiche generate da $e ^ {-iHt} $ in una sequenza di controlli elementari (all'interno di una tolleranza di errore definibile dall'utente).
Sono illustrati i due metodi più diffusi per le formule Quantum Simulation, qubitization e Trotter – Suzuki nella documentazione algoritmica. Sono disponibili implementazioni per entrambi i metodi nella libreria di simulazione hamiltoniana.
