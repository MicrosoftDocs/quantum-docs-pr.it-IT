---
title: 'Math nelle librerie standard Q #'
description: 'Informazioni sulle funzioni matematiche classiche nelle librerie standard Q # usate con i tipi di dati incorporati.'
author: cgranade
uid: microsoft.quantum.libraries.math
ms.author: chgranad@microsoft.com
ms.topic: article
ms.openlocfilehash: bec866472abc0d4327cdc570306341375395f492
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85274958"
---
# <a name="classical-mathematical-functions"></a>Funzioni matematiche classiche #

Queste funzioni vengono utilizzate principalmente per lavorare con i tipi di dati predefiniti Q # `Int` , `Double` e `Range` .

L' <xref:microsoft.quantum.intrinsic.random> operazione è firmata `(Double[] => Int)` .
Accetta una matrice di valori Double come input e restituisce un indice selezionato in modo casuale nella matrice come `Int` .
La probabilità di selezione di un indice specifico è proporzionale al valore dell'elemento di matrice in corrispondenza di tale indice. n elementi della matrice uguali a zero vengono ignorati e i relativi indici non vengono mai restituiti.
Se un elemento della matrice è minore di zero o se nessun elemento della matrice è maggiore di zero, l'operazione ha esito negativo.
