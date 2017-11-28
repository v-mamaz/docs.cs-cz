---
title: "Postupy: Vytvoření služby pracovních postupů, která volá jinou službu pracovních postupů"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 99b3ee3e-aeb7-4e6f-8321-60fe6140eb67
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a0a3b9f77445e8629fb67d099c6d7944044897fb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-create-a-workflow-service-that-calls-another-workflow-service"></a><span data-ttu-id="ecadc-102">Postupy: Vytvoření služby pracovních postupů, která volá jinou službu pracovních postupů</span><span class="sxs-lookup"><span data-stu-id="ecadc-102">How to: Create a Workflow Service That Calls Another Workflow Service</span></span>
<span data-ttu-id="ecadc-103">Někdy je nezbytné pro služby pracovního postupu, který chcete získat informace z jiné služby pracovního postupu.</span><span class="sxs-lookup"><span data-stu-id="ecadc-103">It is sometimes necessary for a workflow service to obtain information from another workflow service.</span></span>  <span data-ttu-id="ecadc-104">Toto téma ukazuje, jak volat jeden služby pracovního postupu z druhého.</span><span class="sxs-lookup"><span data-stu-id="ecadc-104">This topic demonstrates how to call one workflow service from another.</span></span> <span data-ttu-id="ecadc-105">V tomto tématu vytvoříme dvě služby pracovního postupu; ten, který má metodu, která obrátí vstupní řetězec a druhý, který převádí vstupního řetězce na velká písmena po Prohodit řetězec, který používá službu první.</span><span class="sxs-lookup"><span data-stu-id="ecadc-105">In this topic, we’ll create two workflow services; one that has a method that reverses the input string, and another that converts the input string to uppercase after reversing the string that uses the first service.</span></span>  
  
### <a name="to-create-the-reverser-workflow-service"></a><span data-ttu-id="ecadc-106">Vytvoření služby pracovního postupu Reverser</span><span class="sxs-lookup"><span data-stu-id="ecadc-106">To create the Reverser workflow service</span></span>  
  
1.  <span data-ttu-id="ecadc-107">Spustit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] jako správce.</span><span class="sxs-lookup"><span data-stu-id="ecadc-107">Run [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] as an administrator.</span></span>  
  
2.  <span data-ttu-id="ecadc-108">Vyberte **soubor**, **nový projekt**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-108">Select **File**, **New Project**.</span></span> <span data-ttu-id="ecadc-109">V části **pracovního postupu** uzel v **nainstalovaných šablonách** podokně, vyberte **aplikace služby pracovního postupu WCF**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-109">Under the **Workflow** node in the **Installed Templates** pane, select **WCF Workflow Service Application**.</span></span> <span data-ttu-id="ecadc-110">Název řešení `NestedServices` a pak klikněte na **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-110">Name the solution `NestedServices` and then click **OK**.</span></span>  
  
3.  <span data-ttu-id="ecadc-111">V části **servery**, ujistěte se, že **použití místního webového serveru IIS** je vybrána.</span><span class="sxs-lookup"><span data-stu-id="ecadc-111">Under **Servers**, make sure that **Use Local IIS Web Server** is selected.</span></span> <span data-ttu-id="ecadc-112">Klikněte na tlačítko **vytvořit virtuální adresář**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-112">Click **Create Virtual Directory**.</span></span> <span data-ttu-id="ecadc-113">Klikněte na tlačítko **OK** v dialogovém okně pole oznamující, že byl úspěšně vytvořen virtuální adresář.</span><span class="sxs-lookup"><span data-stu-id="ecadc-113">Click **OK** in the dialog box stating that the virtual directory was successfully created.</span></span>  
  
4.  <span data-ttu-id="ecadc-114">V Průzkumníku řešení, přejmenujte Service1.xamlx k `StringReverserService.xamlx`.</span><span class="sxs-lookup"><span data-stu-id="ecadc-114">In Solution Explorer, rename Service1.xamlx to `StringReverserService.xamlx`.</span></span>  
  
5.  <span data-ttu-id="ecadc-115">Na **vlastnosti projektu** stránky pro nový projekt, klikněte na tlačítko **webové** kartě. Nastavte **spustit akci** k **konkrétní stránky**a vyberte StringReverserService.xamlx jako stránku a spustit.</span><span class="sxs-lookup"><span data-stu-id="ecadc-115">On the **Project Properties** page for the new project, click the **Web** tab. Set the **Start Action** to **Specific Page**, and select StringReverserService.xamlx as the page to start.</span></span>  
  
6.  <span data-ttu-id="ecadc-116">Otevřete StringReverserService.xamlx v návrháři a odstranit existující `ReceiveRequest` a `SendReply` aktivity a pak přetáhněte `ReceiveAndSendReply` aktivity do existující aktivitu pořadí.</span><span class="sxs-lookup"><span data-stu-id="ecadc-116">Open StringReverserService.xamlx in the designer and delete the existing `ReceiveRequest` and `SendReply` activities, and then drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="ecadc-117">Nastavte **OperationName** k ReverseString.</span><span class="sxs-lookup"><span data-stu-id="ecadc-117">Set the **OperationName** to ReverseString.</span></span>  
  
    2.  <span data-ttu-id="ecadc-118">Nastavte **ServiceContractName** k IReverseString.</span><span class="sxs-lookup"><span data-stu-id="ecadc-118">Set the **ServiceContractName** to IReverseString.</span></span>  
  
    3.  <span data-ttu-id="ecadc-119">Vyberte **CanCreateInstance** zaškrtávací políčko.</span><span class="sxs-lookup"><span data-stu-id="ecadc-119">Select the **CanCreateInstance** check box.</span></span>  
  
7.  <span data-ttu-id="ecadc-120">Vyberte **SequentialService** aktivitu a klikněte **proměnné** karta v dolní části návrháře.</span><span class="sxs-lookup"><span data-stu-id="ecadc-120">Select the **SequentialService** activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="ecadc-121">Vytvořte dva nové proměnné s názvem StringToReverse a ReversedStringToReturn typu řetězec.</span><span class="sxs-lookup"><span data-stu-id="ecadc-121">Create two new variables named StringToReverse and ReversedStringToReturn of type String.</span></span>  
  
8.  <span data-ttu-id="ecadc-122">Klikněte na tlačítko **definovat** na odkaz v **Receive** aktivity.</span><span class="sxs-lookup"><span data-stu-id="ecadc-122">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="ecadc-123">Klikněte **parametry**a vytvořte parametr s názvem InputString typu řetězec, který přiřazuje StringToReverse.</span><span class="sxs-lookup"><span data-stu-id="ecadc-123">Click the  **Parameters**, and create a parameter named InputString of type String that assigns to StringToReverse.</span></span>  
  
9. <span data-ttu-id="ecadc-124">Klikněte **definovat** na odkaz v **SendReplyToReceive** aktivity.</span><span class="sxs-lookup"><span data-stu-id="ecadc-124">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="ecadc-125">Klikněte **parametry**a vytvořte parametr s názvem ReversedString typu řetězec, přiřazené ReversedStringToReturn.</span><span class="sxs-lookup"><span data-stu-id="ecadc-125">Click the **Parameters**, and create a parameter named ReversedString of type String, assigned to ReversedStringToReturn.</span></span>  
  
10. <span data-ttu-id="ecadc-126">Pokud chcete implementovat logiku pro službu, vytvořte novou třídu do projektu názvem StringLibrary.</span><span class="sxs-lookup"><span data-stu-id="ecadc-126">To implement the logic for the service, create a new class in the project called StringLibrary.</span></span>  <span data-ttu-id="ecadc-127">Nahraďte definici třídy následujícím kódem.</span><span class="sxs-lookup"><span data-stu-id="ecadc-127">Replace the class definition with the following code.</span></span>  
  
    ```  
    public class StringLibrary  
        {  
            public static String ReverseString(string StringToReverse)  
            {  
                char[] charArray = StringToReverse.ToCharArray();  
                Array.Reverse(charArray);  
                return new String(charArray);  
            }  
        }  
    ```  
  
11. <span data-ttu-id="ecadc-128">K volání metody ReverseString na vstupu, přetáhněte **InvokeMethod** aktivity z panelu nástrojů do prostoru mezi **Receive** a **SendReply** aktivity.</span><span class="sxs-lookup"><span data-stu-id="ecadc-128">To call the ReverseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="ecadc-129">Nastavte vlastnosti aktivity následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="ecadc-129">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="ecadc-130">**MethodName**: ReverseString</span><span class="sxs-lookup"><span data-stu-id="ecadc-130">**MethodName**: ReverseString</span></span>  
  
    2.  <span data-ttu-id="ecadc-131">**Výsledek**: ReversedStringToReturn</span><span class="sxs-lookup"><span data-stu-id="ecadc-131">**Result**: ReversedStringToReturn</span></span>  
  
    3.  <span data-ttu-id="ecadc-132">**Parametry**: Vytvořte nový parametr s **směr** z v, **typ** řetězce a **hodnotu** z StringToReverse.</span><span class="sxs-lookup"><span data-stu-id="ecadc-132">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToReverse.</span></span>  
  
    4.  <span data-ttu-id="ecadc-133">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="ecadc-133">**TargetType**: NestedServices.StringLibrary</span></span>  
  
12. <span data-ttu-id="ecadc-134">Testování služby stisknutím klávesy F5.</span><span class="sxs-lookup"><span data-stu-id="ecadc-134">Test the service by pressing F5.</span></span> <span data-ttu-id="ecadc-135">V testovacího klienta WCF, který se zobrazí klikněte dvakrát na metodu ReverseString().</span><span class="sxs-lookup"><span data-stu-id="ecadc-135">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="ecadc-136">V podokně požadavek zadejte `Sample` pro hodnotu parametru InputString.</span><span class="sxs-lookup"><span data-stu-id="ecadc-136">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="ecadc-137">Klikněte na tlačítko **vyvolání**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-137">Click **Invoke**.</span></span> <span data-ttu-id="ecadc-138">Služba by měl vrátit "elpmaS".</span><span class="sxs-lookup"><span data-stu-id="ecadc-138">The service should return "elpmaS".</span></span>  
  
### <a name="to-create-the-uppercaser-workflow-service"></a><span data-ttu-id="ecadc-139">Vytvoření služby pracovního postupu UpperCaser</span><span class="sxs-lookup"><span data-stu-id="ecadc-139">To create the UpperCaser workflow service</span></span>  
  
1.  <span data-ttu-id="ecadc-140">Klikněte pravým tlačítkem na projekt NestedServices a vyberte **přidat**, **novou položku**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-140">Right-click the NestedServices project and select **Add**, **New Item**.</span></span> <span data-ttu-id="ecadc-141">V **pracovního postupu** uzlu, vyberte **pracovního postupu služby WCF**a název nové služby `UpperCaserService`.</span><span class="sxs-lookup"><span data-stu-id="ecadc-141">In the **Workflow** node, select **WCF Workflow Service**, and name the new service `UpperCaserService`.</span></span> <span data-ttu-id="ecadc-142">Klikněte na tlačítko **přidat**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-142">Click **Add**.</span></span> <span data-ttu-id="ecadc-143">To měli přidat novou službu pracovního postupu s názvem UpperCaserService.xamlx do projektu.</span><span class="sxs-lookup"><span data-stu-id="ecadc-143">This should add a new workflow service called UpperCaserService.xamlx to the project.</span></span>  
  
2.  <span data-ttu-id="ecadc-144">Otevřete UpperCaserService.xamlx v návrháři a odstranit existující **ReceiveRequest** a `SendReply` aktivity a přetažení `ReceiveAndSendReply` aktivity do existující aktivitu pořadí.</span><span class="sxs-lookup"><span data-stu-id="ecadc-144">Open UpperCaserService.xamlx in the designer and delete the existing **ReceiveRequest** and `SendReply` activities, and drag a `ReceiveAndSendReply` activity into the existing sequence activity.</span></span>  
  
    1.  <span data-ttu-id="ecadc-145">Nastavte **OperationName** k UpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="ecadc-145">Set the **OperationName** to UpperCaseString.</span></span>  
  
    2.  <span data-ttu-id="ecadc-146">Nastavte **ServiceContractName** k IUpperCaseString.</span><span class="sxs-lookup"><span data-stu-id="ecadc-146">Set the **ServiceContractName** to IUpperCaseString.</span></span>  
  
    3.  <span data-ttu-id="ecadc-147">Vyberte **CanCreateInstance** zaškrtávací políčko.</span><span class="sxs-lookup"><span data-stu-id="ecadc-147">Select the **CanCreateInstance** check box.</span></span>  
  
3.  <span data-ttu-id="ecadc-148">Vyberte aktivitu SequentialService a klikněte **proměnné** karta v dolní části návrháře.</span><span class="sxs-lookup"><span data-stu-id="ecadc-148">Select the SequentialService activity, and then click the **Variables** tab at the bottom of the designer.</span></span> <span data-ttu-id="ecadc-149">Vytvořte tři nové proměnné s názvem StringToUpper, StringToReverse a StringToReturn typu řetězec.</span><span class="sxs-lookup"><span data-stu-id="ecadc-149">Create three new variables named StringToUpper, StringToReverse, and StringToReturn of type String.</span></span>  
  
4.  <span data-ttu-id="ecadc-150">Klikněte na tlačítko **definovat** na odkaz v **Receive** aktivity.</span><span class="sxs-lookup"><span data-stu-id="ecadc-150">Click the **Define** link in the **Receive** activity.</span></span> <span data-ttu-id="ecadc-151">Klikněte **parametry**a vytvořte parametr s názvem InputString typu řetězec, který přiřazuje StringToUpper.</span><span class="sxs-lookup"><span data-stu-id="ecadc-151">Click the **Parameters**, and create a parameter named InputString of type String that assigns to StringToUpper.</span></span>  
  
5.  <span data-ttu-id="ecadc-152">Klikněte **definovat** na odkaz v **SendReplyToReceive** aktivity.</span><span class="sxs-lookup"><span data-stu-id="ecadc-152">Click the **Define** link in the **SendReplyToReceive** activity.</span></span> <span data-ttu-id="ecadc-153">Klikněte **parametry**a vytvořte parametr s názvem ModifiedString typu řetězec, přiřazené StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="ecadc-153">Click the **Parameters**, and create a parameter named ModifiedString of type String, assigned to StringToReturn.</span></span>  
  
6.  <span data-ttu-id="ecadc-154">Pokud chcete implementovat logiku pro službu, vytvoření nové metody ve třídě StringLibrary pomocí následujícího kódu.</span><span class="sxs-lookup"><span data-stu-id="ecadc-154">To implement the logic for the service, create a new method in the StringLibrary class using the following code.</span></span>  
  
    ```  
    public static String UpperCaseString(string StringToUpperCase)  
    {  
         return StringToUpperCase.ToUpper();  
  
    }  
    ```  
  
7.  <span data-ttu-id="ecadc-155">K volání metody UpperCaseString na vstupu, přetáhněte **InvokeMethod** aktivity z panelu nástrojů do prostoru mezi **Receive** a **SendReply** aktivity.</span><span class="sxs-lookup"><span data-stu-id="ecadc-155">To call the UpperCaseString method on the input, drag an **InvokeMethod** activity from the toolbox to the space between the **Receive** and **SendReply** activities.</span></span> <span data-ttu-id="ecadc-156">Nastavte vlastnosti aktivity následujícím způsobem:</span><span class="sxs-lookup"><span data-stu-id="ecadc-156">Set the properties of the activity as follows:</span></span>  
  
    1.  <span data-ttu-id="ecadc-157">**MethodName**: UpperCaseString</span><span class="sxs-lookup"><span data-stu-id="ecadc-157">**MethodName**: UpperCaseString</span></span>  
  
    2.  <span data-ttu-id="ecadc-158">**Výsledek**: StringToReverse</span><span class="sxs-lookup"><span data-stu-id="ecadc-158">**Result**: StringToReverse</span></span>  
  
    3.  <span data-ttu-id="ecadc-159">**Parametry**: Vytvořte nový parametr s **směr** z v, **typ** řetězce a **hodnotu** z StringToUpper.</span><span class="sxs-lookup"><span data-stu-id="ecadc-159">**Parameters**: Create a new parameter with a **Direction** of In, a **Type** of String, and a **Value** of StringToUpper.</span></span>  
  
    4.  <span data-ttu-id="ecadc-160">**TargetType**: NestedServices.StringLibrary</span><span class="sxs-lookup"><span data-stu-id="ecadc-160">**TargetType**: NestedServices.StringLibrary</span></span>  
  
8.  <span data-ttu-id="ecadc-161">Nyní zavoláme vám první službě na upravené řetězec.</span><span class="sxs-lookup"><span data-stu-id="ecadc-161">We’ll now call the first service on the modified string.</span></span> <span data-ttu-id="ecadc-162">Klikněte pravým tlačítkem na projekt a vyberte **přidat odkaz na službu**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-162">Right-click the project and select **Add Service Reference**.</span></span> <span data-ttu-id="ecadc-163">Přidat odkaz na službu ve službě v http://localhost/NestedServices/StringReverserService.xamlx a sestavte projekt a vytvořit vlastní aktivitu pro přístup k první webové služby.</span><span class="sxs-lookup"><span data-stu-id="ecadc-163">Add a service reference to the service at http://localhost/NestedServices/StringReverserService.xamlx and build the project to create a custom activity to access the first Web service.</span></span>  
  
9. <span data-ttu-id="ecadc-164">Přetáhněte instanci novou aktivitu do pracovního postupu, mezi **InvokeMethod** aktivity a **SendReplyToReceive** aktivity.</span><span class="sxs-lookup"><span data-stu-id="ecadc-164">Drag an instance of the new activity onto the workflow, between the **InvokeMethod** activity and the **SendReplyToReceive** activities.</span></span> <span data-ttu-id="ecadc-165">Přiřaďte proměnnou StringToReverse vlastnost InputString nová aktivita a proměnné StringToReturn pro vlastnost StringToReturn.</span><span class="sxs-lookup"><span data-stu-id="ecadc-165">Assign the variable StringToReverse to the InputString property of the new activity, and the variable StringToReturn to the StringToReturn property.</span></span>  
  
10. <span data-ttu-id="ecadc-166">Otevřete stránku vlastností projektu NestedServices a změňte **konkrétní stránky** v **webové** a UpperCaserService.xamlx.</span><span class="sxs-lookup"><span data-stu-id="ecadc-166">Open the Properties page for the NestedServices project, and change the **Specific Page** in the **Web** tab to UpperCaserService.xamlx.</span></span>  
  
11. <span data-ttu-id="ecadc-167">Testování služby stisknutím klávesy F5.</span><span class="sxs-lookup"><span data-stu-id="ecadc-167">Test the service by pressing F5.</span></span> <span data-ttu-id="ecadc-168">V testovacího klienta WCF, který se zobrazí klikněte dvakrát na metodu ReverseString().</span><span class="sxs-lookup"><span data-stu-id="ecadc-168">In the WCF Test Client that appears, double-click the ReverseString() method.</span></span> <span data-ttu-id="ecadc-169">V podokně požadavek zadejte `Sample` pro hodnotu parametru InputString.</span><span class="sxs-lookup"><span data-stu-id="ecadc-169">In the Request pane, enter `Sample` for the Value of the InputString parameter.</span></span> <span data-ttu-id="ecadc-170">Klikněte na tlačítko **vyvolání**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-170">Click **Invoke**.</span></span> <span data-ttu-id="ecadc-171">Služba by měl vrátit "ELPMAS".</span><span class="sxs-lookup"><span data-stu-id="ecadc-171">The service should return "ELPMAS".</span></span>  
  
### <a name="to-create-a-client-to-call-the-services"></a><span data-ttu-id="ecadc-172">Chcete-li vytvořit klienta k volání služeb</span><span class="sxs-lookup"><span data-stu-id="ecadc-172">To create a client to call the services</span></span>  
  
1.  <span data-ttu-id="ecadc-173">Přidáte nový projekt konzolové aplikace volá klienta k řešení.</span><span class="sxs-lookup"><span data-stu-id="ecadc-173">Add a new Console application project called Client to the solution.</span></span>  
  
2.  <span data-ttu-id="ecadc-174">Klikněte pravým tlačítkem na projekt klienta a vyberte **přidat odkaz na službu**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-174">Right-click the Client project and select **Add Service Reference**.</span></span> <span data-ttu-id="ecadc-175">V okně, které se zobrazí, klikněte na **Discover**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-175">In the window that appears, click **Discover**.</span></span> <span data-ttu-id="ecadc-176">Vyberte StringReverserService.xamlx a zadejte ReverseService jako obor názvů.</span><span class="sxs-lookup"><span data-stu-id="ecadc-176">Select StringReverserService.xamlx, and enter ReverseService as the namespace.</span></span>  <span data-ttu-id="ecadc-177">Click **OK**.</span><span class="sxs-lookup"><span data-stu-id="ecadc-177">Click **OK**.</span></span>  
  
3.  <span data-ttu-id="ecadc-178">Nahraďte metodu Main v souboru Program.cs následujícím kódem.</span><span class="sxs-lookup"><span data-stu-id="ecadc-178">Replace the Main method in Program.cs with the following code.</span></span>  
  
    ```  
    static void Main(string[] args)  
    {  
        Console.Write("Input string to process:");  
        String input = Console.ReadLine();  
        var service = new ReverseService.ReverseStringClient();  
        Console.WriteLine("Output from service: {0}", service.ReverseString(input));  
        Console.ReadKey();  
    }  
    ```