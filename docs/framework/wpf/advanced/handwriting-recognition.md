---
title: Rozpoznávání textu psaného rukou
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
ms.openlocfilehash: 08cd9e0a167d1bef9bbe6437b22985082c80e5f9
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57365799"
---
# <a name="handwriting-recognition"></a>Rozpoznávání textu psaného rukou
Tato část popisuje základní informace o rozpoznávání, protože se týkají digitálních inkoust v platformě WPF.  
  
## <a name="recognition-solutions"></a>Rozpoznávání řešení  
 Následující příklad ukazuje, jak rozpoznávání rukopisu pomocí [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90)) třídy.  
  
> [!NOTE]
>  Tato ukázka vyžaduje nainstalované nástroje pro rozpoznávání rukopisu v systému.  
  
 Vytvoření nového projektu aplikace WPF v sadě Visual Studio volá **InkRecognition**. Nahraďte obsah souboru Window1.xaml následující kód XAML. Tento kód vykreslí uživatelské rozhraní vaší aplikace.  
  
 [!code-xaml[InkRecognition#1](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 Přidáte odkaz na sestavení Microsoft Ink, Microsoft.Ink.dll, který se nachází v \Program Files\Microsoft Shared\Ink. Nahraďte obsah souboru kódu na pozadí s následujícím kódem.  
  
 [!code-csharp[InkRecognition#2](~/samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](~/samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a>Viz také:
- [Microsoft.Ink.InkCollector](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms583683(v=vs.90))
