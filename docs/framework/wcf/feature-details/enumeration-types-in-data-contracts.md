---
title: "Výčtové typy v kontraktech dat"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: data contracts [WCF], enumeration types
ms.assetid: b5d694da-68cb-4b74-a5fb-75108a68ec3b
caps.latest.revision: "13"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ea76ae136695ce2dc9eca0a9c7660e4e1ffe547d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="enumeration-types-in-data-contracts"></a><span data-ttu-id="ae290-102">Výčtové typy v kontraktech dat</span><span class="sxs-lookup"><span data-stu-id="ae290-102">Enumeration Types in Data Contracts</span></span>
<span data-ttu-id="ae290-103">Výčty může být vyjádřený v datovém modelu kontrakt.</span><span class="sxs-lookup"><span data-stu-id="ae290-103">Enumerations can be expressed in the data contract model.</span></span> <span data-ttu-id="ae290-104">Toto téma vás provede několik příkladů, které vysvětlují programovací model.</span><span class="sxs-lookup"><span data-stu-id="ae290-104">This topic walks through several examples that explain the programming model.</span></span>  
  
## <a name="enumeration-basics"></a><span data-ttu-id="ae290-105">Základy – výčet</span><span class="sxs-lookup"><span data-stu-id="ae290-105">Enumeration Basics</span></span>  
 <span data-ttu-id="ae290-106">Jeden ze způsobů použití výčtové typy v modelu kontraktu dat je pro použití <xref:System.Runtime.Serialization.DataContractAttribute> atributu typu.</span><span class="sxs-lookup"><span data-stu-id="ae290-106">One way to use enumeration types in the data contract model is to apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the type.</span></span> <span data-ttu-id="ae290-107">Musíte použít <xref:System.Runtime.Serialization.EnumMemberAttribute> atribut pro každého člena, který musí být součástí kontrakt dat.</span><span class="sxs-lookup"><span data-stu-id="ae290-107">You must then apply the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute to each member that must be included in the data contract.</span></span>  
  
 <span data-ttu-id="ae290-108">Následující příklad ukazuje dvě třídy.</span><span class="sxs-lookup"><span data-stu-id="ae290-108">The following example shows two classes.</span></span> <span data-ttu-id="ae290-109">Používá výčtu první a druhý definuje výčtu.</span><span class="sxs-lookup"><span data-stu-id="ae290-109">The first uses the enumeration and the second defines the enumeration.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#1)]
 [!code-vb[c_DataContractEnumerations#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#1)]  
  
 <span data-ttu-id="ae290-110">Instance `Car` třída může odesílat nebo přijímat pouze v případě `condition` je nastaveno na jednu z hodnot `New`, `Used`, nebo `Rental`.</span><span class="sxs-lookup"><span data-stu-id="ae290-110">An instance of the `Car` class can be sent or received only if the `condition` field is set to one of the values `New`, `Used`, or `Rental`.</span></span> <span data-ttu-id="ae290-111">Pokud `condition` je `Broken` nebo `Stolen`, <xref:System.Runtime.Serialization.SerializationException> je vyvolána výjimka.</span><span class="sxs-lookup"><span data-stu-id="ae290-111">If the `condition` is `Broken` or `Stolen`, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>  
  
 <span data-ttu-id="ae290-112">Můžete použít <xref:System.Runtime.Serialization.DataContractAttribute> vlastnosti (<xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> a <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>) jako obvykle pro kontrakty dat výčtu.</span><span class="sxs-lookup"><span data-stu-id="ae290-112">You can use the <xref:System.Runtime.Serialization.DataContractAttribute> properties (<xref:System.Runtime.Serialization.DataContractAttribute.Name%2A> and <xref:System.Runtime.Serialization.DataContractAttribute.Namespace%2A>) as usual for enumeration data contracts.</span></span>  
  
### <a name="enumeration-member-values"></a><span data-ttu-id="ae290-113">Hodnoty člen výčtu</span><span class="sxs-lookup"><span data-stu-id="ae290-113">Enumeration Member Values</span></span>  
 <span data-ttu-id="ae290-114">Obecně kontrakt dat zahrnuje názvy členů výčtu, nikoli číselné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="ae290-114">Generally the data contract includes enumeration member names, not numerical values.</span></span> <span data-ttu-id="ae290-115">Ale když pomocí dat smlouvy modelu, pokud je na straně příjmu [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] klienta, schéma exportovaný zachovává číselné hodnoty.</span><span class="sxs-lookup"><span data-stu-id="ae290-115">However, when using the data contract model, if the receiving side is a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, the exported schema preserves the numerical values.</span></span> <span data-ttu-id="ae290-116">Všimněte si, že to tak není při použití [používání třídy XmlSerializer](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).</span><span class="sxs-lookup"><span data-stu-id="ae290-116">Note that this is not the case when using the [Using the XmlSerializer Class](../../../../docs/framework/wcf/feature-details/using-the-xmlserializer-class.md).</span></span>  
  
 <span data-ttu-id="ae290-117">V předchozím příkladu Pokud `condition` je nastaven na `Used` a je serializovat data XML, je výsledný soubor XML `<condition>Used</condition>` a není `<condition>1</condition>`.</span><span class="sxs-lookup"><span data-stu-id="ae290-117">In the preceding example, if `condition` is set to `Used` and the data is serialized to XML, the resulting XML is `<condition>Used</condition>` and not `<condition>1</condition>`.</span></span> <span data-ttu-id="ae290-118">Proto je ekvivalentní kontrakt dat z následující kontrakt dat `CarConditionEnum`.</span><span class="sxs-lookup"><span data-stu-id="ae290-118">Therefore, the following data contract is equivalent to the data contract of `CarConditionEnum`.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#2)]
 [!code-vb[c_DataContractEnumerations#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#2)]  
  
 <span data-ttu-id="ae290-119">Například můžete použít `CarConditionEnum` na straně odesílání a `CarConditionWithNumbers` na straně příjmu.</span><span class="sxs-lookup"><span data-stu-id="ae290-119">For example, you can use `CarConditionEnum` on the sending side and `CarConditionWithNumbers` on the receiving side.</span></span> <span data-ttu-id="ae290-120">I když na odesílající straně používá hodnotu "1" pro `Used` a přijímající straně používá, je hodnota "20," reprezentaci XML `<condition>Used</condition>` pro obou stranách.</span><span class="sxs-lookup"><span data-stu-id="ae290-120">Although the sending side uses the value "1" for `Used` and the receiving side uses the value "20," the XML representation is `<condition>Used</condition>` for both sides.</span></span>  
  
 <span data-ttu-id="ae290-121">Chcete-li být součástí kontrakt dat, je nutné použít <xref:System.Runtime.Serialization.EnumMemberAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="ae290-121">To be included in the data contract, you must apply the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute.</span></span> <span data-ttu-id="ae290-122">V [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], můžete vždy použít speciální hodnota 0 (nula) pro výčet, který je taky výchozí hodnota pro všechny – výčet.</span><span class="sxs-lookup"><span data-stu-id="ae290-122">In the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], you can always apply the special value 0 (zero) to an enumeration, which is also the default value for any enumeration.</span></span> <span data-ttu-id="ae290-123">Ale i v této zvláštní nulovou hodnotu nelze serializovat, pokud je označené <xref:System.Runtime.Serialization.EnumMemberAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="ae290-123">However, even this special zero value cannot be serialized unless it is marked with the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="ae290-124">Existují dvě výjimky:</span><span class="sxs-lookup"><span data-stu-id="ae290-124">There are two exceptions to this:</span></span>  
  
-   <span data-ttu-id="ae290-125">Příznak výčty (popsané dál v tomto tématu).</span><span class="sxs-lookup"><span data-stu-id="ae290-125">Flag enumerations (discussed later in this topic).</span></span>  
  
-   <span data-ttu-id="ae290-126">Datové členy výčtu s <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> vlastnost nastavena na hodnotu `false` (v takovém případě výčtu s nulovou hodnotou je vynechaný serializovaná data).</span><span class="sxs-lookup"><span data-stu-id="ae290-126">Enumeration data members with the <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> property set to `false` (in which case, the enumeration with the value zero is omitted from the serialized data).</span></span>  
  
### <a name="customizing-enumeration-member-values"></a><span data-ttu-id="ae290-127">Přizpůsobení hodnot člen výčtu</span><span class="sxs-lookup"><span data-stu-id="ae290-127">Customizing Enumeration Member Values</span></span>  
 <span data-ttu-id="ae290-128">Můžete upravit hodnotu člena výčtu, která součástí kontrakt dat pomocí <xref:System.Runtime.Serialization.EnumMemberAttribute.Value%2A> vlastnost <xref:System.Runtime.Serialization.EnumMemberAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="ae290-128">You can customize the enumeration member value that forms a part of the data contract by using the <xref:System.Runtime.Serialization.EnumMemberAttribute.Value%2A> property of the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute.</span></span>  
  
 <span data-ttu-id="ae290-129">Například následující kontrakt dat odpovídá také kontrakt dat z `CarConditionEnum`.</span><span class="sxs-lookup"><span data-stu-id="ae290-129">For example, the following data contract is also equivalent to the data contract of the `CarConditionEnum`.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#3)]
 [!code-vb[c_DataContractEnumerations#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#3)]  
  
 <span data-ttu-id="ae290-130">Když serializovanou hodnotu `PreviouslyOwned` má reprezentaci XML `<condition>Used</condition>`.</span><span class="sxs-lookup"><span data-stu-id="ae290-130">When serialized, the value of `PreviouslyOwned` has the XML representation `<condition>Used</condition>`.</span></span>  
  
## <a name="simple-enumerations"></a><span data-ttu-id="ae290-131">Jednoduché výčty</span><span class="sxs-lookup"><span data-stu-id="ae290-131">Simple Enumerations</span></span>  
 <span data-ttu-id="ae290-132">Můžete také serializovat výčtové typy, ke kterému <xref:System.Runtime.Serialization.DataContractAttribute> atribut nebyla použita.</span><span class="sxs-lookup"><span data-stu-id="ae290-132">You can also serialize enumeration types to which the <xref:System.Runtime.Serialization.DataContractAttribute> attribute has not been applied.</span></span> <span data-ttu-id="ae290-133">Takové výčtové typy jsou považovány přesně podle předchozích pokynů, vyjma toho, že každý člen (která nemá <xref:System.NonSerializedAttribute> atribut použitý) považuje jako kdyby <xref:System.Runtime.Serialization.EnumMemberAttribute> byl použit atribut.</span><span class="sxs-lookup"><span data-stu-id="ae290-133">Such enumeration types are treated exactly as previously described, except that every member (that does not have the <xref:System.NonSerializedAttribute> attribute applied) is treated as if the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute has been applied.</span></span> <span data-ttu-id="ae290-134">Například následující výčet implicitně má ekvivalentní předchozím kontraktu dat `CarConditionEnum` příklad.</span><span class="sxs-lookup"><span data-stu-id="ae290-134">For example, the following enumeration implicitly has a data contract equivalent to the preceding `CarConditionEnum` example.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#6)]
 [!code-vb[c_DataContractEnumerations#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#6)]  
  
 <span data-ttu-id="ae290-135">Jednoduché výčty můžete použít, když není potřeba přizpůsobit název kontraktu dat ve výčtu a obor názvů a hodnot člen výčtu.</span><span class="sxs-lookup"><span data-stu-id="ae290-135">You can use simple enumerations when you do not need to customize the enumeration's data contract name and namespace and the enumeration member values.</span></span>  
  
#### <a name="notes-on-simple-enumerations"></a><span data-ttu-id="ae290-136">Poznámky k jednoduché výčty</span><span class="sxs-lookup"><span data-stu-id="ae290-136">Notes on Simple Enumerations</span></span>  
 <span data-ttu-id="ae290-137">Použití <xref:System.Runtime.Serialization.EnumMemberAttribute> atribut na jednoduchý výčty nemá žádný vliv.</span><span class="sxs-lookup"><span data-stu-id="ae290-137">Applying the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute to simple enumerations has no effect.</span></span>  
  
 <span data-ttu-id="ae290-138">Nezáleží na tom, jestli <xref:System.SerializableAttribute> výčtu je použit atribut.</span><span class="sxs-lookup"><span data-stu-id="ae290-138">It makes no difference whether or not the <xref:System.SerializableAttribute> attribute is applied to the enumeration.</span></span>  
  
 <span data-ttu-id="ae290-139">Fakt, <xref:System.Runtime.Serialization.DataContractSerializer> třídy respektuje <xref:System.NonSerializedAttribute> atributu použitého pro členy výčtu se liší od chování <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> a <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span><span class="sxs-lookup"><span data-stu-id="ae290-139">The fact that the <xref:System.Runtime.Serialization.DataContractSerializer> class honors the <xref:System.NonSerializedAttribute> attribute applied to enumeration members is different from the behavior of the <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> and the <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>.</span></span> <span data-ttu-id="ae290-140">Obě tyto serializátorů Ignorovat <xref:System.NonSerializedAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="ae290-140">Both of those serializers ignore the <xref:System.NonSerializedAttribute> attribute.</span></span>  
  
## <a name="flag-enumerations"></a><span data-ttu-id="ae290-141">Příznak výčty</span><span class="sxs-lookup"><span data-stu-id="ae290-141">Flag Enumerations</span></span>  
 <span data-ttu-id="ae290-142">Můžete použít <xref:System.FlagsAttribute> atribut výčty.</span><span class="sxs-lookup"><span data-stu-id="ae290-142">You can apply the <xref:System.FlagsAttribute> attribute to enumerations.</span></span> <span data-ttu-id="ae290-143">V takovém případě seznam nula nebo více hodnot výčtu můžete odeslat nebo současně.</span><span class="sxs-lookup"><span data-stu-id="ae290-143">In that case, a list of zero or more enumeration values can be sent or received simultaneously.</span></span>  
  
 <span data-ttu-id="ae290-144">K tomu použít <xref:System.Runtime.Serialization.DataContractAttribute> atribut výčet příznaků a označí všechny členy, kteří jsou dva pravomocí <xref:System.Runtime.Serialization.EnumMemberAttribute> atribut.</span><span class="sxs-lookup"><span data-stu-id="ae290-144">To do so, apply the <xref:System.Runtime.Serialization.DataContractAttribute> attribute to the flag enumeration and then mark all the members that are powers of two with the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute.</span></span> <span data-ttu-id="ae290-145">Všimněte si, že pokud chcete použít výčet příznaků, musí být průběh v bez přerušení sekvenci zajišťuje 2 (například 1, 2, 4, 8, 16, 32, 64).</span><span class="sxs-lookup"><span data-stu-id="ae290-145">Note that to use a flag enumeration, the progression must be an uninterrupted sequence of powers of 2 (for example, 1, 2, 4, 8, 16, 32, 64).</span></span>  
  
 <span data-ttu-id="ae290-146">Následující postup se vztahuje k odesílání Příznak Hodnota výčtu:</span><span class="sxs-lookup"><span data-stu-id="ae290-146">The following steps apply to sending a flag's enumeration value:</span></span>  
  
1.  <span data-ttu-id="ae290-147">Pokus o vyhledání člena výčtu (s <xref:System.Runtime.Serialization.EnumMemberAttribute> atribut použitý) která se mapuje na číselnou hodnotu.</span><span class="sxs-lookup"><span data-stu-id="ae290-147">Attempt to find an enumeration member (with the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute applied) that maps to the numeric value.</span></span> <span data-ttu-id="ae290-148">Pokud nalezen, odeslání seznamu, který právě tohoto člena obsahuje.</span><span class="sxs-lookup"><span data-stu-id="ae290-148">If found, send a list that contains just that member.</span></span>  
  
2.  <span data-ttu-id="ae290-149">Pokus o rozdělit číselnou hodnotu na součet tak, že jsou členy výčtu (každý <xref:System.Runtime.Serialization.EnumMemberAttribute> atribut použitý), mapování na jednotlivých součástí součet.</span><span class="sxs-lookup"><span data-stu-id="ae290-149">Attempt to break the numeric value into a sum such that there are enumeration members (each with the <xref:System.Runtime.Serialization.EnumMemberAttribute> attribute applied) that map to each part of the sum.</span></span> <span data-ttu-id="ae290-150">Odesílání seznamu všech těchto členů.</span><span class="sxs-lookup"><span data-stu-id="ae290-150">Send the list of all these members.</span></span> <span data-ttu-id="ae290-151">Všimněte si, že *typu greedy algoritmus* se používá k vyhledání sum, a proto není zaručeno, například součet nalezené i v případě, že je k dispozici.</span><span class="sxs-lookup"><span data-stu-id="ae290-151">Note that the *greedy algorithm* is used to find such a sum, and thus there is no guarantee that such a sum is found even if it is present.</span></span> <span data-ttu-id="ae290-152">K tomuto problému nedošlo, ujistěte se, že číselné hodnoty výčtu členy, jsou zajišťuje dva.</span><span class="sxs-lookup"><span data-stu-id="ae290-152">To avoid this problem, make sure that the numeric values of the enumeration members are powers of two.</span></span>  
  
3.  <span data-ttu-id="ae290-153">Pokud předchozí dva kroky k selhání, a je číselná hodnota nenulové hodnoty, throw <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="ae290-153">If the preceding two steps fail, and the numeric value is nonzero, throw a <xref:System.Runtime.Serialization.SerializationException>.</span></span> <span data-ttu-id="ae290-154">Pokud je číselná hodnota nulová, odeslat prázdný seznam.</span><span class="sxs-lookup"><span data-stu-id="ae290-154">If the numeric value is zero, send the empty list.</span></span>  
  
### <a name="example"></a><span data-ttu-id="ae290-155">Příklad</span><span class="sxs-lookup"><span data-stu-id="ae290-155">Example</span></span>  
 <span data-ttu-id="ae290-156">Následující příklad výčet můžete použít v operaci příznak.</span><span class="sxs-lookup"><span data-stu-id="ae290-156">The following enumeration example can be used in a flag operation.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#4)]
 [!code-vb[c_DataContractEnumerations#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#4)]  
  
 <span data-ttu-id="ae290-157">Následující ukázkové hodnoty jsou serializovat jako uvedené.</span><span class="sxs-lookup"><span data-stu-id="ae290-157">The following example values are serialized as indicated.</span></span>  
  
 [!code-csharp[c_DataContractEnumerations#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontractenumerations/cs/source.cs#5)]
 [!code-vb[c_DataContractEnumerations#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontractenumerations/vb/source.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="ae290-158">Viz také</span><span class="sxs-lookup"><span data-stu-id="ae290-158">See Also</span></span>  
 <xref:System.Runtime.Serialization.DataContractSerializer>  
 [<span data-ttu-id="ae290-159">Použití kontraktů dat</span><span class="sxs-lookup"><span data-stu-id="ae290-159">Using Data Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)  
 [<span data-ttu-id="ae290-160">Určování přenosu dat v kontraktech služby</span><span class="sxs-lookup"><span data-stu-id="ae290-160">Specifying Data Transfer in Service Contracts</span></span>](../../../../docs/framework/wcf/feature-details/specifying-data-transfer-in-service-contracts.md)