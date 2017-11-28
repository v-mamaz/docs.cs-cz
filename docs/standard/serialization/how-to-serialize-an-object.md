---
title: 'Postupy: serializaci objektu'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.assetid: a1207d05-32b2-4953-8582-959607991227
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 76b6006c34b29e17ea725a5f7d104c1b085b5edc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-serialize-an-object"></a><span data-ttu-id="9fc1e-102">Postupy: serializaci objektu</span><span class="sxs-lookup"><span data-stu-id="9fc1e-102">How to: Serialize an Object</span></span>
<span data-ttu-id="9fc1e-103">K serializaci objektu, nejprve vytvořte objekt, který má být serializován a nastavíte jeho veřejné vlastnosti a pole.</span><span class="sxs-lookup"><span data-stu-id="9fc1e-103">To serialize an object, first create the object that is to be serialized and set its public properties and fields.</span></span> <span data-ttu-id="9fc1e-104">Chcete-li to provést, je třeba určit přenos formát, ve kterém má být uložena jako datový proud nebo jako soubor XML datového proudu.</span><span class="sxs-lookup"><span data-stu-id="9fc1e-104">To do this, you must determine the transport format in which the XML stream is to be stored, either as a stream or as a file.</span></span> <span data-ttu-id="9fc1e-105">Například pokud datový proud XML musí být uložen ve formě trvalé, vytvořit <xref:System.IO.FileStream> objektu.</span><span class="sxs-lookup"><span data-stu-id="9fc1e-105">For example, if the XML stream must be saved in a permanent form, create a <xref:System.IO.FileStream> object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="9fc1e-106">Další příklady serializace XML, najdete v části [serializace XML Příklady](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="9fc1e-106">For more examples of XML serialization, see [Examples of XML Serialization](../../../docs/standard/serialization/examples-of-xml-serialization.md).</span></span>  
  
### <a name="to-serialize-an-object"></a><span data-ttu-id="9fc1e-107">K serializaci objektu</span><span class="sxs-lookup"><span data-stu-id="9fc1e-107">To serialize an object</span></span>  
  
1.  <span data-ttu-id="9fc1e-108">Vytvoření objektu a nastavíte jeho veřejné polí a vlastností.</span><span class="sxs-lookup"><span data-stu-id="9fc1e-108">Create the object and set its public fields and properties.</span></span>  
  
2.  <span data-ttu-id="9fc1e-109">Vytvořit <xref:System.Xml.Serialization.XmlSerializer> pomocí daného typu objektu.</span><span class="sxs-lookup"><span data-stu-id="9fc1e-109">Construct a <xref:System.Xml.Serialization.XmlSerializer> using the type of the object.</span></span> <span data-ttu-id="9fc1e-110">Další informace naleznete <xref:System.Xml.Serialization.XmlSerializer> třídy konstruktory.</span><span class="sxs-lookup"><span data-stu-id="9fc1e-110">For more information, see the <xref:System.Xml.Serialization.XmlSerializer> class constructors.</span></span>  
  
3.  <span data-ttu-id="9fc1e-111">Volání <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> metoda ke generování datový proud XML nebo soubor, který představuje polí a veřejné vlastnosti objektu.</span><span class="sxs-lookup"><span data-stu-id="9fc1e-111">Call the <xref:System.Xml.Serialization.XmlSerializer.Serialize%2A> method to generate either an XML stream or a file representation of the object's public properties and fields.</span></span> <span data-ttu-id="9fc1e-112">Následující příklad vytvoří soubor.</span><span class="sxs-lookup"><span data-stu-id="9fc1e-112">The following example creates a file.</span></span>  
  
    ```vb  
    Dim myObject As MySerializableClass = New MySerializableClass()  
    ' Insert code to set properties and fields of the object.  
    Dim mySerializer As XmlSerializer = New XmlSerializer(GetType(MySerializableClass))  
    ' To write to a file, create a StreamWriter object.  
    Dim myWriter As StreamWriter = New StreamWriter("myFileName.xml")  
    mySerializer.Serialize(myWriter, myObject)  
    myWriter.Close()  
    ```  
  
    ```csharp  
    MySerializableClass myObject = new MySerializableClass();  
    // Insert code to set properties and fields of the object.  
    XmlSerializer mySerializer = new   
    XmlSerializer(typeof(MySerializableClass));  
    // To write to a file, create a StreamWriter object.  
    StreamWriter myWriter = new StreamWriter("myFileName.xml");  
    mySerializer.Serialize(myWriter, myObject);  
    myWriter.Close();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="9fc1e-113">Viz také</span><span class="sxs-lookup"><span data-stu-id="9fc1e-113">See Also</span></span>  
 [<span data-ttu-id="9fc1e-114">Představení serializace XML</span><span class="sxs-lookup"><span data-stu-id="9fc1e-114">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)  
 [<span data-ttu-id="9fc1e-115">Postupy: deserializaci objektu</span><span class="sxs-lookup"><span data-stu-id="9fc1e-115">How to: Deserialize an Object</span></span>](../../../docs/standard/serialization/how-to-deserialize-an-object.md)