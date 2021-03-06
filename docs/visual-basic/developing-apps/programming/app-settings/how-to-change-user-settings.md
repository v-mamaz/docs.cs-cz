---
title: 'Postupy: Změna uživatelského nastavení v jazyce Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- user settings [Visual Basic], changing in Visual Basic
- user settings
- My.Settings object [Visual Basic], changing user settings
- examples [Visual Basic], changing user settings
ms.assetid: 41250181-c594-4854-9988-8183b9eb03cf
ms.openlocfilehash: 4e93dbf453b831bb28707250466ea928bfe9a716
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 02/28/2019
ms.locfileid: "56976379"
---
# <a name="how-to-change-user-settings-in-visual-basic"></a>Postupy: Změna uživatelského nastavení v jazyce Visual Basic
Uživatelské nastavení můžete změnit přiřazení nové hodnoty pro nastavení vlastnosti na `My.Settings` objektu.  
  
 `My.Settings` Objekt poskytuje každému nastavení jako vlastnost. Název vlastnosti je stejný jako název nastavení a typ vlastnosti je stejný jako typů nastavení. Toto nastavení **oboru** Určuje, zda je vlastnost jen pro čtení: Vlastnost pro **aplikace**– obor nastavení je jen pro čtení, při vlastnost pro **uživatele**– obor nastavení je pro čtení i zápis. Další informace najdete v tématu [My.Settings – objekt](../../../../visual-basic/language-reference/objects/my-settings-object.md).  
  
> [!NOTE]
>  I když můžete změnit a uložit hodnoty nastavení rozsahu uživatele za běhu, nastavení oboru aplikace jsou jen pro čtení a nedá se změnit prostřednictvím kódu programu. Nastavení oboru aplikace můžete změnit, když vytvoříte aplikaci pomocí **Návrháře projektu** nebo úpravou konfiguračního souboru aplikace. Další informace najdete v tématu [Správa nastavení aplikace (.NET)](/visualstudio/ide/managing-application-settings-dotnet).  
  
## <a name="example"></a>Příklad  
 V tomto příkladu změní hodnotu `Nickname` nastavení hlavního názvu uživatele.  
  
 [!code-vb[VbVbalrMyResources#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#7)]  
  
 Pro tento příklad fungoval, musí mít vaše aplikace `Nickname` nastavení hlavního názvu uživatele, typu `String`.  
  
 Aplikace ukládá uživatelská nastavení při ukončení aplikace. Chcete-li uložit nastavení okamžitě, zavolejte `My.Settings.Save` metody. Další informace najdete v tématu [jak: Zachování uživatelského nastavení v jazyce Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md).  
  
## <a name="see-also"></a>Viz také:
- [Objekt My.Settings](../../../../visual-basic/language-reference/objects/my-settings-object.md)
- [Postupy: Čtení nastavení aplikace v jazyce Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-read-application-settings.md)
- [Postupy: Zachování uživatelského nastavení v jazyce Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-persist-user-settings.md)
- [Postupy: Vytváření mřížek vlastností pro uživatelská nastavení v jazyce Visual Basic](../../../../visual-basic/developing-apps/programming/app-settings/how-to-create-property-grids-for-user-settings.md)
- [Správa nastavení aplikace (.NET)](/visualstudio/ide/managing-application-settings-dotnet)
