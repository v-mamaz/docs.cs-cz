---
title: <see> - C# Průvodce programováním
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <see>
- see
helpviewer_keywords:
- cref [C#], <see> tag
- <see> C# XML tag
- cross-references [C#]
- see C# XML tag
ms.assetid: 0200de01-7e2f-45c4-9094-829d61236383
ms.openlocfilehash: 90fd73346d255d195fa7384ebc2f60ebc4f32fba
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480673"
---
# <a name="see-c-programming-guide"></a>\<Zobrazit > (C# Programming Guide)
## <a name="syntax"></a>Syntaxe  
  
```xml  
<see cref="member"/>  
```  
  
## <a name="parameters"></a>Parametry  
 cref = " `member`"  
 Odkaz na člena nebo na pole, které lze volat z prostředí aktuální kompilace. Kompilátor kontroluje, zda daný prvek kódu existuje a předá `member` do názvu prvku ve výstupním souboru XML. Místo *člen* do dvojitých uvozovek ("").  
  
## <a name="remarks"></a>Poznámky  
 \<Naleznete v tématu > značky umožňuje zadat odkaz v rámci textu. Použití [ \<seealso >](../../../csharp/programming-guide/xmldoc/seealso.md) označit, že text by měl být umístěno v části Viz také. Použití [cref – atribut](../../../csharp/programming-guide/xmldoc/cref-attribute.md) k vytvoření interních hypertextových odkazů na stránky dokumentace prvků kódu.  
  
 Kompilovat s [-doc](../../../csharp/language-reference/compiler-options/doc-compiler-option.md) pro zpracování dokumentačních komentářů do souboru.  
  
 Následující příklad ukazuje \<naleznete v tématu > značky v souhrnné části.  
  
 [!code-csharp[csProgGuideDocComments#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#12)]  
  
## <a name="see-also"></a>Viz také:

- [Průvodce programováním v jazyce C#](../../../csharp/programming-guide/index.md)
- [Doporučené značky pro komentáře dokumentace](../../../csharp/programming-guide/xmldoc/recommended-tags-for-documentation-comments.md)
