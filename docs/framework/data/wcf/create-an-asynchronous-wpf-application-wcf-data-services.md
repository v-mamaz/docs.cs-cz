---
title: 'Postupy: Vytvoření asynchronní Windows Presentation Framework aplikace (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, asynchronous operations
ms.assetid: 834614df-1427-4839-b0be-90f68e5afffd
ms.openlocfilehash: 89a4d1c244e69098971e87957f308f9a30ade6d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676637"
---
# <a name="how-to-create-an-asynchronous-windows-presentation-framework-application-wcf-data-services"></a>Postupy: Vytvoření asynchronní Windows Presentation Framework aplikace (WCF Data Services)
S [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], můžete svázat data z datové služby na prvek uživatelského rozhraní aplikace Windows Presentation Framework (WPF). Další informace najdete v tématu [vazba dat k ovládacím prvkům](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md). Operace se datové služby můžete také spustit v asynchronním režimu, které umožní aplikaci reagovat při čekání na odpověď na žádost o službu data i nadále. Aplikace pro Silverlight vyžadovaných pro přístup ke službě data asynchronně. Další informace najdete v tématu [asynchronních operací](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
 Toto téma ukazuje, jak přístup ke službě data asynchronně a svázat výsledky na elementy aplikaci WPF. Příklady v tomto tématu ukázková datová služba Northwind a klientská data automaticky generované služby třídy. Tuto službu a třídy dat klientů jsou vytvořeny po dokončení [rychlý start služeb WCF Data Services](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
## <a name="example"></a>Příklad  
 Následující XAML definuje okno aplikace WPF.  
  
 [!code-xaml[Astoria Northwind Client#WpfDataBindingAsyncXaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml#wpfdatabindingasyncxaml)]  
  
## <a name="example"></a>Příklad  
 Na následující stránce použití modelu code-behind pro soubor XAML provede asynchronního dotazu pomocí datové služby a sváže s výsledky prvků v okně WPF.  
  
 [!code-csharp[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind client/cs/customerordersasync.xaml.cs#wpfdatabindingasync)]
 [!code-vb[Astoria Northwind Client#WpfDataBindingAsync](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind client/vb/customerordersasync.xaml.vb#wpfdatabindingasync)]  
  
## <a name="see-also"></a>Viz také:
- [Klientská knihovna pro WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
