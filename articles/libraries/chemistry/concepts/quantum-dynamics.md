---
title: Dynamics Quantum
description: Informazioni sulle analogie e le differenze tra la dinamica quantistica e la dinamica classica.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
ms.openlocfilehash: 9cb74ccd4b7806a90c0701300860d777fa8e5d75
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904486"
---
# <a name="quantum-dynamics"></a>Dynamics Quantum

La meccanica quantistica è in gran parte lo studio di Quantum Dynamics, che cerca di comprendere come uno stato del quantum iniziale $ \ket{\psi (0)} $ varia nel tempo (vedere la [documentazione concettuale](xref:microsoft.quantum.concepts.dirac) sul quantum computing per ulteriori informazioni sulla notazione Dirac).
In particolare, data questa condizione iniziale uno stato quantico, un tempo di evoluzione e una specifica del sistema Quantum Dynamical, viene ricercato uno stato quantico $ \ket{\psi (t)} $.
Prima di procedere con la spiegazione della Quantum Dynamics, è utile eseguire un passo indietro e pensare alle dinamiche classiche, perché fornisce informazioni approfondite sul modo in cui la meccanica quantistica non è molto diversa dalle dinamiche classiche.

Nelle dinamiche classiche, sappiamo dalla seconda legge del movimento di Newton che la posizione di una particella evolve in base a $F (x, t) = ma = m\frac {\ DD ^ 2} {\dd t ^ 2} {x} (t) $, dove $F (x, t) $ è la forza, $m $ è la massa e $a $ è l'accelerazione.
Quindi, data una posizione iniziale $x (0) $, il tempo di evoluzione $t $ e la descrizione delle forze che agiscono sulla particella, è possibile trovare $x (t) $ risolvendo l'equazione differenziale fornita dalle equazioni di Newton per $x (t) $.
Specificare le forze in questo modo è un po' di dolore.
Quindi, spesso si esprimono le forze in termini di potenziale energia del sistema, che ci fornisce $-\ partial_x V (x, t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $.
Per una particella, quindi, le dinamiche del sistema vengono specificate solo dalla potenziale funzione energetica, dalla massa della particella e dal tempo di evoluzione.

Viene spesso introdotta una lingua più ampia per le dinamiche classiche che vanno oltre $F = ma $.
Una formulazione, che è particolarmente utile nei meccanismi quantistici, è costituita da meccanismi hamiltoniana.
Nei meccanismi hamiltoniana, l'energia totale di un sistema e le posizioni (generalizzate) e momenta forniscono tutte le informazioni necessarie per descrivere il movimento di un oggetto classico arbitrario.
In particolare, consentire $f (x, p, t) $ sia una funzione delle posizioni generalizzate $x $ e momenta $p $ di un sistema e lasciare che $H (x, p, t) $ sia la funzione hamiltoniana.
Se ad esempio si accettano $f (x, p, t) = x (t) $ e $H (x, p, t) = p ^ 2 (t)/2m-V (x, t) $, si recupererà il caso sopra riportato di Dynamics newtoniano.
In generale, \begin{align} \frac{d}{DT} f & = \ partial_t f-(\ partial_x H \ partial_p f + \ partial_p H \ partial_x f)\\\\ & partial_t \\f +\\{f, H}.
\end{align} qui $\\{f, H\\} $ è chiamato la [parentesi di Poisson](https://en.wikipedia.org/wiki/Poisson_bracket) e appare ampliamente in Dynamics classico a causa del ruolo centrale che svolge nella definizione di Dynamics.

La dinamica quantistica può essere descritta usando esattamente la stessa lingua.
L'hamiltoniana, o Total Energy, specifica completamente le dinamiche di qualsiasi sistema Quantum chiuso.
Esistono, tuttavia, alcune differenze sostanziali tra le due teorie.
Nei meccanismi classici $x $ e $p $ sono solo numeri, mentre in meccanica quantistica non lo sono.
In realtà non commutano anche: $xp \ne px $.

Il concetto matematico appropriato per descrivere questi oggetti che non comportano la permuta è un operatore, che nei casi in cui $x $ e $p $ possono solo usare un set di valori discreti coincide con il concetto di matrice.
Quindi, per semplicità, si presuppone che il sistema Quantum sia finito in modo che possa essere descritto usando [vettori e matrici](xref:microsoft.quantum.concepts.vectors).
È necessario che queste matrici siano hermitiane, ovvero che la trasforma coniugata della matrice corrisponda alla matrice originale.
In questo modo si garantisce che gli autovalori delle matrici siano di valore reale; condizione che si impone per assicurarsi che, quando si misura una quantità simile a una posizione per cui non viene restituito un numero immaginario.

Così come gli analoghi della posizione e del momento in meccanica quantistica devono essere sostituiti dagli operatori, la funzione hamiltoniana deve essere sostituita in modo analogo da un operatore.
Ad esempio, per una particella nello spazio libero è necessario che $H (x, p) = p ^ 2/2m $, mentre nei meccanismi quantistici l'operatore Hamiltoniana $ \hat{H} $ sia $ \hat{H} = \hat{p} ^ 2/2m $ dove $ \hat{p} $ è l'operatore Momentum.
Da questo punto di vista, il passaggio da classiche a Quantum Dynamics implica semplicemente la sostituzione delle variabili usate nella normale dinamica con gli operatori.
Una volta creato l'operatore Hamiltoniana traducendo la tradizionale hamiltoniana classica sul linguaggio Quantum, possiamo esprimere la dinamica di una quantità meccanica quantistica arbitraria (ad esempio, l'operatore Quantum Mechanical) $ \hat{f} (t) $ tramite \begin{ align} \frac{d}{DT} \hat{f} = \ partial_t \hat{f} + [\hat{f}, \hat{H}], \end{align} dove $ [f, H] = fH-HF $ è noto come commutatore.
Questa espressione è esattamente come l'espressione classica riportata sopra con la differenza che la parentesi di Poisson $\\{f, H\\} $ sostituita con il commutatore tra $f $ e $H $.
Questo processo di acquisizione di un'Hamiltoniana classica e dell'uso per trovare un'Hamiltoniana quantistica è noto nel gergo Quantico come quantizzazione canonica.

Quali operatori $f $ sono più interessati?  La risposta a questa operazione dipende dal problema che si vuole risolvere.
Probabilmente la quantità più utile da trovare è l'operatore quantum state, come illustrato nella documentazione concettuale precedente, che può essere usato per estrarre tutti gli elementi che si desidera ottenere.
Una volta eseguita questa operazione (e semplificando il risultato nel caso in cui uno abbia uno stato puro), viene trovata l'equazione Schrödinger per lo stato quantum \begin{align} i \ partial_t \ket{\psi (t)} = \hat{H} (t) \ket{\psi (t)}.
\end{align}

Questa equazione, sebbene forse meno intuitiva rispetto a quanto indicato sopra, produce probabilmente l'espressione più semplice per comprendere come simulare la dinamica quantistica in un computer Quantum o classico.
Ciò è dovuto al fatto che la soluzione all'equazione differenziale può essere espressa nel formato seguente (nel caso in cui l'Hamiltoniana sia costante in $t $) \begin{align} \ket{\psi (t)} = e ^ {-iHt} \ket{\psi (0)}.
\end{align} qui $e ^ {-iHt} $ è una matrice unitaria.
Ciò significa che esiste un circuito quantico che può essere progettato per eseguirlo perché i computer Quantum possono approssimarsi a qualsiasi matrice unitaria.
Questo atto di trovare un circuito quantico per implementare l'operatore Quantum Time Evolution $e ^ {-iHt} $ è quello che viene spesso definito simulazione quantistica o in particolare simulazione Quantum dinamica.
