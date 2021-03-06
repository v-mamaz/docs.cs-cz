---
title: Analytické trasování s ETW
ms.date: 03/30/2017
helpviewer_keywords:
- diagnostics [WCF], analytic tracing
- administration [WCF], analytic tracing
- analytic tracing [WCF]
ms.assetid: 1d518e47-a38d-41e8-93d7-8c3b361f6a56
ms.openlocfilehash: 4651c515a938ed8f8736597808156080cfb0bbed
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54609080"
---
# <a name="analytic-tracing-with-etw"></a>Analytické trasování s ETW
Analytické trasování Windows Communication Foundation (WCF) nabízí způsob, jak zachytit diagnostické informace během provádění ve službě WCF. Události analytického trasování WCF jsou emitovány klíčových bodů v zásobníku WCF povolit Poradce při potížích pro služby WCF v produkčním prostředí. Analytické trasování pro služby WCF má minimální dopad na výkon server produktu, který je hostitelem [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)] služby WCF, protože tyto události jsou velmi efektivně vygenerován pro relaci Event Tracing for Windows (ETW).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Přehled analytického trasování](../../../../../docs/framework/wcf/diagnostics/etw/analytic-tracing-overview.md)  
 Tento článek popisuje princip analytické trasování WCF v [!INCLUDE[netfx_current_long](../../../../../includes/netfx-current-long-md.md)].  
  
 [Dynamické povolování analytického sledování](../../../../../docs/framework/wcf/diagnostics/etw/dynamically-enabling-analytic-tracing.md)  
 Popisuje, jak povolit nebo zakázat trasování dynamicky pomocí trasování událostí pro Windows.  
  
 [Konfigurace trasování toku zpráv](../../../../../docs/framework/wcf/diagnostics/etw/configuring-message-flow-tracing.md)  
 Popisuje postup konfigurace trasování toku zpráv.  
  
 [Události analytického trasování – přehled](../../../../../docs/framework/wcf/diagnostics/etw/analytic-trace-event-reference.md)  
 Zobrazuje tabulku ID událostí s jejich úrovně události, zprávy o událostech a klíčová slova.  
  
## <a name="see-also"></a>Viz také:
- [Služby WCF a Trasování událostí pro Windows](../../../../../docs/framework/wcf/samples/wcf-services-and-event-tracing-for-windows.md)
- [Sledování událostí v Trasování událostí ve Windows](../../../../../docs/framework/windows-workflow-foundation/samples/tracking-events-into-event-tracing-in-windows.md)
