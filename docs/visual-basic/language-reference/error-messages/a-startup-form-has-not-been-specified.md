---
title: Nebyl zadán formulář spuštění.
ms.date: 07/20/2015
f1_keywords:
- vbrAppModel_NoStartupForm
ms.assetid: 8e04af49-4bef-49de-a7ec-e407e9873da7
ms.openlocfilehash: f05358f76829768d8ff5c4ac85b5134f35254126
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627210"
---
# <a name="a-startup-form-has-not-been-specified"></a>Nebyl zadán formulář spuštění.
Aplikace používá <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase> třídy, ale není zadán formulář spuštění.  
  
 Tato situace může nastat, pokud **Povolit aplikační framework** v Návrháři projektu je zaškrtnuté políčko ale **úvodní formulář** není zadán. Další informace najdete v tématu [stránka aplikace, Návrhář projektu (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
## <a name="to-correct-this-error"></a>Oprava této chyby  
  
1.  Zadejte spouštěcí objekt pro aplikaci.  
  
     Další informace najdete v tématu [stránka aplikace, Návrhář projektu (Visual Basic)](/visualstudio/ide/reference/application-page-project-designer-visual-basic).  
  
2.  Přepsat <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A> metody nastavte <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A> vlastnost formuláře úvodního formuláře.  
  
## <a name="see-also"></a>Viz také:
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OnCreateMainForm%2A>
- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.MainForm%2A>
- [Přehled aplikačního modelu jazyka Visual Basic](../../../visual-basic/developing-apps/development-with-my/overview-of-the-visual-basic-application-model.md)
