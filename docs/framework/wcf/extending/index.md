---
title: Rozšíření WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 24ad74f04a3ac31d0b0d0d87f0d74f88c0521f50
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803702"
---
# <a name="extending-wcf"></a>Rozšíření WCF
Windows Communication Foundation (WCF) umožňuje upravit a rozšířit běhu součásti přesněji řídit a rozšířit aplikace založené na služby. Témata v této části najdete podrobněji o architektuře rozšíření. Další informace o základní programování najdete v tématu [základní programování WCF](../../../../docs/framework/wcf/basic-wcf-programming.md).  
  
## <a name="in-this-section"></a>V tomto oddílu  
 [Rozšíření ServiceHost a vrstva modelu služby](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 Vrstva modelu služby je zodpovědná za stahování příchozí zprávy mimo základní kanály, převedena do volání metod v kódu aplikace a odesílání výsledky zpět k volajícímu.  Rozšíření modelů služby upravit nebo jsou implementovány provádění nebo komunikace chování a funkce zahrnující dispečera funkce, vlastní chování, zprávu a parametr zachycení a další funkce rozšiřitelnost.  
  
 [Rozšíření vazeb](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 Vazby jsou objekty, které popisují podrobnosti komunikace požadované pro připojení ke koncovému bodu. Vazba rozšíření nebo vlastní vazby implementovat vlastní komunikaci funkce potřebné k podpoře funkce aplikací.  
  
 [Rozšíření vrstvy kanálu](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 Vrstvy kanálu je umístěna pod vrstva modelu služby a je odpovědná za výměny zpráv mezi klienty a služby. Kanál rozšíření můžete implementovat nové funkce protokolu, například zabezpečení. Rozšíření kanál také přenosu funkce, například implementace nový síťový přenos pro přenos protokolu SOAP zprávy.  
  
 [Rozšíření zabezpečení](../../../../docs/framework/wcf/extending/extending-security.md)  
 Zabezpečení ve WCF se skládá z přenosu zabezpečení (integrity, důvěrnost a ověřování), řízení přístupu (autorizace) a auditování. Třídy v nalezen `IdentityModel` obor názvů se používá technologie WCF pro řízení přístupu. Principy zabezpečení architektura umožňuje vytvořit typy vlastních deklarací identity pro přizpůsobení systémy kontroly vlastní přístup.  
  
 [Rozšíření systému metadat](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 Systém metadat WCF je skupina třídy a rozhraní, které představují metadata potřebnou k implementaci aplikace založené na služby. Upravit nebo rozšíření třídy nebo implementovat a nakonfigurovat rozhraní pro export a import vlastních metadat, jako je například rozšíření webové služby popis Language (WSDL) nebo vlastní WS-PolicyAttachments kontrolní výrazy.  
  
 [Rozšiřování kodérů a serializátorů](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 Kodérů a serializátorů převede data z jednoho formátu do jiného. Témata v této části popisují, jak rozšířit zadané třídy zvláštních požadavků.  
  
## <a name="reference"></a>Odkaz  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a>Související oddíly  
 [Základní programování WCF](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [Podrobnosti o funkcích WCF](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [Pokyny a osvědčené postupy](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
