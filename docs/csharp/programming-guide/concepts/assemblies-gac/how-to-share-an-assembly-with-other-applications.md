---
title: 'Postupy: Sdílení sestavení s jinými aplikacemi (C#)'
ms.date: 07/20/2015
ms.assetid: c30e972b-1693-4e05-b115-c31831fdf9f2
ms.openlocfilehash: d440000ef509199bf69f06c2f3b5d0819e48f724
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713574"
---
# <a name="how-to-share-an-assembly-with-other-applications-c"></a>Postupy: Sdílení sestavení s jinými aplikacemi (C#)
Sestavení mohou být privátní nebo sdílené: ve výchozím nastavení, většina jednoduché programy obsahovat soukromé sestavení vzhledem k tomu, že nejsou určena pro použití jiné aplikace.  
  
 Pokud chcete sdílení sestavení s jinými aplikacemi, musí být umístěn v [Global Assembly Cache](../../../../framework/app-domains/gac.md) (GAC).  
  
### <a name="sharing-an-assembly"></a>Sdílení sestavení  
  
1.  Vytvoření vašeho sestavení. Další informace najdete v tématu [vytváření sestavení](../../../../framework/app-domains/create-assemblies.md).  
  
2.  K sestavení přiřadíte silný název. Další informace najdete v tématu [jak: Podepsání sestavení silným názvem](../../../../framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
3.  Informace o verzi přiřadíte k sestavení. Další informace najdete v tématu [Správa verzí sestavení](../../../../../docs/framework/app-domains/assembly-versioning.md).  
  
4.  Přidáte sestavení do globální mezipaměti sestavení. Další informace najdete v tématu [jak: Instalace sestavení do globální mezipaměti sestavení](../../../../framework/app-domains/how-to-install-an-assembly-into-the-gac.md).  
  
5.  Přístup k typům obsaženy v sestavení z jiných aplikací. Další informace najdete v tématu [jak: Odkazování na sestavení se silným názvem](../../../../framework/app-domains/how-to-reference-a-strong-named-assembly.md).  
  
## <a name="see-also"></a>Viz také:

- [Průvodce programováním v jazyce C#](../../../../csharp/programming-guide/index.md)
- [Programování se sestaveními](../../../../framework/app-domains/programming-with-assemblies.md)
