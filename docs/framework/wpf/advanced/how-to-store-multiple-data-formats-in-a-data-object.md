---
title: 'Postupy: Uložení několika datových formátů do datového objektu'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataObject class [WPF], storing multiple formats
- DataFormats class [WPF], storing multiple formats
- drag-and-drop [WPF], storing multiple formats
ms.assetid: 941ace29-29c4-4c26-b75b-ea7d06aa0d69
ms.openlocfilehash: 9e261f3f00c28a0a15343e2691048ad022f1be7c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 03/05/2019
ms.locfileid: "57351070"
---
# <a name="how-to-store-multiple-data-formats-in-a-data-object"></a>Postupy: Uložení několika datových formátů do datového objektu
Následující příklad ukazuje způsob použití <xref:System.Windows.DataObject.SetData%28System.String%2CSystem.Object%29> metoda pro přidání dat na datový objekt v různých formátech.  
  
## <a name="example"></a>Příklad  
  
### <a name="description"></a>Popis  
  
### <a name="code"></a>Kód  
 [!code-csharp[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/csharp/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/CSharp/Window1.xaml.cs#_dragdrop_storemultipleformats)]
 [!code-vb[DragDrop_DragDropMiscCode#_DragDrop_StoreMultipleFormats](~/samples/snippets/visualbasic/VS_Snippets_Wpf/DragDrop_DragDropMiscCode/visualbasic/window1.xaml.vb#_dragdrop_storemultipleformats)]  
  
## <a name="see-also"></a>Viz také:
- <xref:System.Windows.IDataObject>
- [Přehled přetažení](drag-and-drop-overview.md)
