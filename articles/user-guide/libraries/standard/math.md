---
title: Matematica nelle Q# librerie standard
description: Informazioni sulle funzioni matematiche classiche nelle Q# librerie standard usate con i tipi di dati incorporati.
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4a3747eaa2c91e482ded3af1279a0e40d922bfb3
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "87868424"
---
# <a name="classical-mathematical-functions"></a>Funzioni matematiche classiche #

Queste funzioni vengono utilizzate principalmente per lavorare con i Q# tipi di dati incorporati `Int` , `Double` e `Range` .

L' <xref:microsoft.quantum.intrinsic.random> operazione è firmata `(Double[] => Int)` .
Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int` .
La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice. n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.
Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.
