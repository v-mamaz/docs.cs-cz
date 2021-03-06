---
title: System.ServiceModel.Channels.MsmqMessageRejected
ms.date: 03/30/2017
ms.assetid: 9b7c10a7-2af6-44a2-8b1a-90bba0c7cf26
ms.openlocfilehash: 87d6e6fc3205fff9bd977ebe77004dfa489098cb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54681219"
---
# <a name="systemservicemodelchannelsmsmqmessagerejected"></a>System.ServiceModel.Channels.MsmqMessageRejected
MSMQ odmítl zprávu.  
  
## <a name="description"></a>Popis  
 Trasování označuje, že zprávy MSMQ byla odmítnuta.  
  
 Když (používá se NetMsmqBinding nebo vazbu MsmqIntegrationBinding) Windows Communication Foundation (WCF) není schopen se jejich zpracování může být odmítnutá zprávy služby MSMQ. Tyto zprávy jsou označovány jako počet nezpracovatelných zpráv. Nezpracovatelná zpráva zamítá při `ReceiveErrorHandling` NetMsmqBinding nebo vazbu MsmqIntegrationBinding je nastavena na `Reject`. Odmítnuté zprávy se doručí zpět do odesílatele [fronty nedoručených zpráv](https://go.microsoft.com/fwlink/?LinkID=99544).  
  
 Zobrazit [zpracování zpráv Poison](https://go.microsoft.com/fwlink/?LinkID=99546) podrobné informace o při stát nezpracovatelných zpráv a způsob konfigurace vaší služby k odpovídajícím způsobem zpracovat.  
  
 Zobrazit [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548) pro další podrobnosti o tom, co znamená odmítnuté zprávy služby MSMQ.  
  
## <a name="see-also"></a>Viz také:
- [Trasování](../../../../../docs/framework/wcf/diagnostics/tracing/index.md)
- [Řešení problémů s aplikací pomocí trasování](../../../../../docs/framework/wcf/diagnostics/tracing/using-tracing-to-troubleshoot-your-application.md)
- [Správa a diagnostika](../../../../../docs/framework/wcf/diagnostics/index.md)
- [Zpracování zpráv Poison](https://go.microsoft.com/fwlink/?LinkID=99546)
- [MQMarkMessageRejected](https://go.microsoft.com/fwlink/?LinkID=99548)
