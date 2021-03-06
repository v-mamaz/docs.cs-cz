---
title: <value> - C# Průvodce programováním
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <value>
helpviewer_keywords:
- <value> C# XML tag
- value C# XML tag
ms.assetid: 08dbadaf-9ab6-43d9-9493-98e43bed199a
ms.openlocfilehash: 7f82008d000bf0316b505bfc5d40e9e64b2685a3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57465190"
---
# <a name="value-c-programming-guide"></a>\<Hodnota > (C# Programming Guide)
## <a name="syntax"></a>Syntaxe  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a>Parametry  
 `property-description`  
 Popis pro vlastnost.  
  
## <a name="remarks"></a>Poznámky  
 \<Hodnota > značky umožňuje popisují hodnotu, která představuje vlastnost. Všimněte si, že při přidání vlastnosti prostřednictvím Průvodce kódem ve vývojovém prostředí sady Visual Studio .NET, přidá [ \<summary >](../../../csharp/programming-guide/xmldoc/summary.md) značky pro novou vlastnost. Měli byste pak ručně přidat \<hodnota > značka, které popisují hodnotu, která představuje vlastnost.  
  
 Kompilovat s [/doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) pro zpracování dokumentačních komentářů do souboru.  
  
## <a name="example"></a>Příklad  
 [!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#14)]  
  
## <a name="see-also"></a>Viz také:

- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)
- [Doporučené značky pro komentáře dokumentace](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
