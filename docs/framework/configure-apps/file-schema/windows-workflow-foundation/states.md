---
title: <states>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: ebea5e7c-ad58-43c5-8f2d-cca25ae1b721
ms.openlocfilehash: 018ea20342475de40a8392a9272724e37902ecb9
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/30/2019
ms.locfileid: "55257717"
---
# <a name="states"></a>\<states>
Představuje kolekci předplacenému stavy z instance sledovaných pracovního postupu při vytváření záznamů sledování.  
  
 Další informace o sledování profil dotazy naleznete v tématu [sledování profilů](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)  
  
\<system.serviceModel>  
\<sledování >  
\<trackingProfile>  
\<pracovní postup >  
\<workflowInstanceQueries>  
\<workflowInstanceQuery>  
\<states>  
  
## <a name="syntax"></a>Syntaxe  
  
```xml  
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <workflowInstanceQueries>
        <workflowInstanceQuery>
          <states>
            <state name="Name"/>
          </states>
        </workflowInstanceQuery>
      </workflowInstanceQueries>
    </workflow>
  </trackingProfile>
</tracking>  
```  
  
## <a name="attributes-and-elements"></a>Atributy a elementy  
 Následující části popisují atributy, podřízené prvky a nadřazené prvky.  
  
### <a name="attributes"></a>Atributy  
 Žádné  
  
### <a name="child-elements"></a>Podřízené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<state>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/states.md)|Odebírané stavu z instance sledovaných pracovního postupu, pokud je vytvořena položka sledování.|  
  
### <a name="parent-elements"></a>Nadřazené elementy  
  
|Prvek|Popis|  
|-------------|-----------------|  
|[\<workflowInstanceQuery>](../../../../../docs/framework/configure-apps/file-schema/windows-workflow-foundation/workflowinstancequery.md)|Dotaz, který sleduje změny životního cyklu instance pracovního postupu, jako je spuštěna nebo dokončené události.|  
  
## <a name="remarks"></a>Poznámky  
 Vrácené záznamy jsou filtrovány státy v této kolekci.  
  
 Stav možné hodnoty jsou popsány v následující tabulce.  
  
|Stav|Popis|  
|-----------|-----------------|  
|Bylo přerušeno|Instance pracovního postupu byla zrušena.|  
|Byla dokončena|Instance pracovního postupu je dokončen.|  
|Odstranit|Instance pracovního postupu byl odstraněn.|  
|Nečinnosti|Instance pracovního postupu nečinnosti.|  
|Trvalé|Instance pracovního postupu je trvalý.|  
|Obnovení|Instance pracovního postupu po obnovení.|  
|Bylo zahájeno|Je spuštěn, instance pracovního postupu.|  
|UnhandledException|Instance pracovního postupu došlo k neošetřené výjimce.|  
|uvolněné|Instance pracovního postupu je uvolněn.|  
|Zrušeno|Instance pracovního postupu bylo zrušeno.|  
|Dočasně blokován.|Instance pracovního postupu je pozastaveno.|  
|Ukončen|Instance pracovního postupu je ukončeno.|  
|Pozastavení|Pozastavení je instance pracovního postupu.|  
  
## <a name="example"></a>Příklad  
 Následující konfigurace přihlásí na úrovni instance sledování záznamů pro pracovní postup `Started` stav instance pomocí tohoto dotazu.  
  
```xml  
<workflowInstanceQueries>  
    <workflowInstanceQuery>  
      <states>  
        <state name="Started"/>  
      </states>  
    </workflowInstanceQuery>  
</workflowInstanceQueries>  
```  
  
## <a name="see-also"></a>Viz také:
- <xref:System.ServiceModel.Activities.Tracking.Configuration.WorkflowInstanceQueryElement?displayProperty=nameWithType>
- <xref:System.ServiceModel.Activities.Tracking.Configuration.StateElementCollection?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.WorkflowInstanceQuery?displayProperty=nameWithType>
- [Sledování a trasování pracovních postupů](../../../../../docs/framework/windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Sledování profilů](../../../../../docs/framework/windows-workflow-foundation/tracking-profiles.md)
