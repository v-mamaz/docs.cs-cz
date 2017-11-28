---
title: "Počet odmítnutých zpráv zařazených do fronty za sekundu"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77ea9aa3-b9e2-4a1d-a65e-5ca115ba0567
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0a773d30cc9cb33a9bd3a1e1fb5562026bcfb7e2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="queued-rejected-messages-per-second"></a><span data-ttu-id="6ef32-102">Počet odmítnutých zpráv zařazených do fronty za sekundu</span><span class="sxs-lookup"><span data-stu-id="6ef32-102">Queued Rejected Messages Per Second</span></span>
<span data-ttu-id="6ef32-103">Název čítače: Počet odmítnutých za sekundu zpráv zařazených do fronty.</span><span class="sxs-lookup"><span data-stu-id="6ef32-103">Counter Name: Queued Messages Rejected Per Second.</span></span>  
  
## <a name="description"></a><span data-ttu-id="6ef32-104">Popis</span><span class="sxs-lookup"><span data-stu-id="6ef32-104">Description</span></span>  
 <span data-ttu-id="6ef32-105">Počet zpráv, které jsou odmítnut zařazených do fronty přenosu v této služby za sekundu.</span><span class="sxs-lookup"><span data-stu-id="6ef32-105">Number of messages that are rejected by the queued transport at this service in a second.</span></span>  
  
 <span data-ttu-id="6ef32-106">Tento čítač je typu čítače výkonu [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), jehož hodnota je vypočítána pomocí následujícího vzorce.</span><span class="sxs-lookup"><span data-stu-id="6ef32-106">This counter is of performance counter type [PERF_COUNTER_COUNTER](http://go.microsoft.com/fwlink/?LinkID=94649), whose value is calculated using the following formula.</span></span>  
  
 <span data-ttu-id="6ef32-107">(NE 1 - N 0) / ((D 1 - D 0) / F)</span><span class="sxs-lookup"><span data-stu-id="6ef32-107">(N 1 - N 0 ) / ( (D 1 -D 0 ) / F)</span></span>