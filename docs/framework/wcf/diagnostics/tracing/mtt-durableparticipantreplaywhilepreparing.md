---
title: Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
ms.date: 03/30/2017
ms.assetid: 10ef3876-6f8e-4d4e-8444-f47847b64795
ms.openlocfilehash: 3b51a100677221866186b2e24f34396c012d11c1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54603128"
---
# <a name="microsofttransactionstransactionbridgedurableparticipantreplaywhilepreparing"></a>Microsoft.Transactions.TransactionBridge.DurableParticipantReplayWhilePreparing
Služba protokolu WS-AT obdržela odpověď od trvalého účastníka, který neodpověděl na připravit. V důsledku toho byla transakce přerušena.  
  
## <a name="description"></a>Popis  
 Trasovaná, pokud se stále připravuje trvalého účastníka bylo přijato odpověď. Toto je neplatná zpráva pro tento stav a transakce bude přerušen.  
  
## <a name="troubleshooting"></a>Poradce při potížích  
 Tato chyba může indiate, trvalého účastníka (včetně podřízených TransactionManagers) se zotavil po selhání, i když je jistí, jaké výsledek transakce a požádat o jeho stav.  
  
## <a name="see-also"></a>Viz také:
- [Trasování](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Řešení problémů s aplikací pomocí trasování](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Správa a diagnostika](../../../../../docs/framework/wcf/diagnostics/index.md)
