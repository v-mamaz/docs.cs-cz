---
title: ServiceTimeoutsBehavior
ms.date: 03/30/2017
ms.assetid: 4412525d-a3cc-4eae-b3e8-a50ce766d09d
ms.openlocfilehash: b129483b60a62f04f522036c9d1fa54268f6f346
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566668"
---
# <a name="servicetimeoutsbehavior"></a>ServiceTimeoutsBehavior
ServiceTimeoutsBehavior  
  
## <a name="syntax"></a>Syntaxe  
  
```csharp
class ServiceTimeoutsBehavior : Behavior  
{  
  datetime TransactionTimeout;  
};  
```  
  
## <a name="methods"></a>Metody  
 Třída ServiceTimeoutsBehavior nedefinuje žádné metody.  
  
## <a name="properties"></a>Vlastnosti  
 Třída ServiceTimeoutsBehavior má následující vlastnost:  
  
### <a name="transactiontimeout"></a>Vlastnost TransactionTimeout  
 Datový typ: datum a čas  
  
 Typ přístupu: jen pro čtení  
  
 Období, ve kterém musí být transakce dokončena.  
  
## <a name="requirements"></a>Požadavky  
  
|SOUBOR MOF|Deklarované v Servicemodel.mof.|  
|---------|-----------------------------------|  
|Obor názvů|Definované v root\ServiceModel|  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Configuration.ServiceTimeoutsElement>
