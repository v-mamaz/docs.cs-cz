---
title: "Postupy: paralelní provádění vícenásobných webových dotazů pomocí modifikátoru Async a operátoru Await (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a9b96e8acf9f5453ac035769ea7b279c4fedadfb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: cs-CZ
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a><span data-ttu-id="68a36-102">Postupy: paralelní provádění vícenásobných webových dotazů pomocí modifikátoru Async a operátoru Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a36-102">How to: Make Multiple Web Requests in Parallel by Using Async and Await (Visual Basic)</span></span>
<span data-ttu-id="68a36-103">V asynchronní metody když vytváří se spustí úlohy.</span><span class="sxs-lookup"><span data-stu-id="68a36-103">In an async method, tasks are started when they’re created.</span></span> <span data-ttu-id="68a36-104">[Await](../../../../visual-basic/language-reference/operators/await-operator.md) operátor se použije pro úlohu v okamžiku v metodě kde zpracování nemůže pokračovat, dokud na dokončení úlohy.</span><span class="sxs-lookup"><span data-stu-id="68a36-104">The [Await](../../../../visual-basic/language-reference/operators/await-operator.md) operator is applied to the task at the point in the method where processing can’t continue until the task finishes.</span></span> <span data-ttu-id="68a36-105">Úloha je často očekáváno, jakmile je vytvořen, jako ukazuje následující příklad.</span><span class="sxs-lookup"><span data-stu-id="68a36-105">Often a task is awaited as soon as it’s created, as the following example shows.</span></span>  
  
```vb  
Dim result = Await someWebAccessMethodAsync(url)  
```  
  
 <span data-ttu-id="68a36-106">Můžete však oddělit, vytvoření úlohy z čeká na úlohy, pokud má jinou práci provedete program, který nezávisí na dokončení úlohy.</span><span class="sxs-lookup"><span data-stu-id="68a36-106">However, you can separate creating the task from awaiting the task if your program has other work to accomplish that doesn’t depend on the completion of the task.</span></span>  
  
```vb  
' The following line creates and starts the task.  
Dim myTask = someWebAccessMethodAsync(url)  
  
' While the task is running, you can do other work that does not depend  
' on the results of the task.  
' . . . . .  
  
' The application of Await suspends the rest of this method until the task is   
' complete.  
Dim result = Await myTask  
```  
  
 <span data-ttu-id="68a36-107">Mezi počáteční úlohu a čeká na jeho, můžete spustit další úlohy.</span><span class="sxs-lookup"><span data-stu-id="68a36-107">Between starting a task and awaiting it, you can start other tasks.</span></span> <span data-ttu-id="68a36-108">Další úlohy implicitně paralelní spuštění, ale jsou vytvořeny žádné další vlákna.</span><span class="sxs-lookup"><span data-stu-id="68a36-108">The additional tasks implicitly run in parallel, but no additional threads are created.</span></span>  
  
 <span data-ttu-id="68a36-109">Následující program spustí tři asynchronní webové stahování a pak je čeká v pořadí, ve kterém jsou volány.</span><span class="sxs-lookup"><span data-stu-id="68a36-109">The following program starts three asynchronous web downloads and then awaits them in the order in which they’re called.</span></span> <span data-ttu-id="68a36-110">Všimněte si, při spuštění programu, který úlohy není vždy dokončit v pořadí, ve kterém byly vytvořeny nebo očekáváno.</span><span class="sxs-lookup"><span data-stu-id="68a36-110">Notice, when you run the program, that the tasks don’t always finish in the order in which they’re created and awaited.</span></span> <span data-ttu-id="68a36-111">Spuštění spustit, když vytvoříte a jeden nebo více úkolů může dokončit před metodu dosáhne await výrazy.</span><span class="sxs-lookup"><span data-stu-id="68a36-111">They start to run when they’re created, and one or more of the tasks might finish before the method reaches the await expressions.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68a36-112">K dokončení tohoto projektu, musíte mít Visual Studio 2012 nebo vyšší a rozhraní .NET Framework 4.5 nebo vyšší v počítači nainstalována.</span><span class="sxs-lookup"><span data-stu-id="68a36-112">To complete this project, you must have Visual Studio 2012 or higher and the .NET Framework 4.5 or higher installed on your computer.</span></span>  
  
 <span data-ttu-id="68a36-113">Další příklad, která se spouští ve stejnou dobu více úloh, najdete v části [postupy: rozšíření návodu asynchronních podle pomocí metody Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span><span class="sxs-lookup"><span data-stu-id="68a36-113">For another example that starts multiple tasks at the same time, see [How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md).</span></span>  
  
 <span data-ttu-id="68a36-114">Si můžete stáhnout kód v tomto příkladu z [ukázky kódu vývojáře](http://go.microsoft.com/fwlink/?LinkId=254906).</span><span class="sxs-lookup"><span data-stu-id="68a36-114">You can download the code for this example from [Developer Code Samples](http://go.microsoft.com/fwlink/?LinkId=254906).</span></span>  
  
### <a name="to-set-up-the-project"></a><span data-ttu-id="68a36-115">Vytvoření projektu</span><span class="sxs-lookup"><span data-stu-id="68a36-115">To set up the project</span></span>  
  
1.  <span data-ttu-id="68a36-116">Pokud chcete nastavit aplikaci WPF, proveďte následující kroky.</span><span class="sxs-lookup"><span data-stu-id="68a36-116">To set up a WPF application, complete the following steps.</span></span> <span data-ttu-id="68a36-117">Najdete podrobné pokyny pro tyto kroky v [návod: přístup k webu pomocí modifikátoru Async a Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span><span class="sxs-lookup"><span data-stu-id="68a36-117">You can find detailed instructions for these steps in [Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md).</span></span>  
  
    -   <span data-ttu-id="68a36-118">Vytvořte aplikaci WPF, která obsahuje textové pole a tlačítko.</span><span class="sxs-lookup"><span data-stu-id="68a36-118">Create a WPF application that contains a text box and a button.</span></span> <span data-ttu-id="68a36-119">Název tlačítka `startButton`a název textového pole `resultsTextBox`.</span><span class="sxs-lookup"><span data-stu-id="68a36-119">Name the button `startButton`, and name the text box `resultsTextBox`.</span></span>  
  
    -   <span data-ttu-id="68a36-120">Přidat odkaz pro <xref:System.Net.Http>.</span><span class="sxs-lookup"><span data-stu-id="68a36-120">Add a reference for <xref:System.Net.Http>.</span></span>  
  
    -   <span data-ttu-id="68a36-121">V souboru MainWindow.xaml.vb, přidejte `Imports` příkaz pro `System.Net.Http`.</span><span class="sxs-lookup"><span data-stu-id="68a36-121">In the MainWindow.xaml.vb file, add an `Imports` statement for `System.Net.Http`.</span></span>  
  
### <a name="to-add-the-code"></a><span data-ttu-id="68a36-122">Přidání kódu</span><span class="sxs-lookup"><span data-stu-id="68a36-122">To add the code</span></span>  
  
1.  <span data-ttu-id="68a36-123">V okně návrhu MainWindow.xaml, dvakrát klikněte na tlačítko vytvořit `startButton_Click` obslužné rutiny událostí v MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="68a36-123">In the design window, MainWindow.xaml, double-click the button to create the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
2.  <span data-ttu-id="68a36-124">Zkopírujte následující kód a vložte jej do textu `startButton_Click` v MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="68a36-124">Copy the following code, and paste it into the body of `startButton_Click` in MainWindow.xaml.vb.</span></span>  
  
    ```vb  
    resultsTextBox.Clear()  
    Await CreateMultipleTasksAsync()  
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    ```  
  
     <span data-ttu-id="68a36-125">Kód volá asynchronní metodu, `CreateMultipleTasksAsync`, jednotky, které se aplikace.</span><span class="sxs-lookup"><span data-stu-id="68a36-125">The code calls an asynchronous method, `CreateMultipleTasksAsync`, which drives the application.</span></span>  
  
3.  <span data-ttu-id="68a36-126">Do projektu přidejte následující metody podpory:</span><span class="sxs-lookup"><span data-stu-id="68a36-126">Add the following support methods to the project:</span></span>  
  
    -   <span data-ttu-id="68a36-127">`ProcessURLAsync`používá <xref:System.Net.Http.HttpClient> metoda pro stažení obsahu webu, jako bajtové pole.</span><span class="sxs-lookup"><span data-stu-id="68a36-127">`ProcessURLAsync` uses an <xref:System.Net.Http.HttpClient> method to download the contents of a website as a byte array.</span></span> <span data-ttu-id="68a36-128">V případě metody podporu `ProcessURLAsync` pak zobrazí a vrátí délku pole.</span><span class="sxs-lookup"><span data-stu-id="68a36-128">The support method, `ProcessURLAsync` then displays and returns the length of the array.</span></span>  
  
    -   <span data-ttu-id="68a36-129">`DisplayResults`Zobrazí počet bajtů v bajtové pole pro každou adresu URL.</span><span class="sxs-lookup"><span data-stu-id="68a36-129">`DisplayResults` displays the number of bytes in the byte array for each URL.</span></span> <span data-ttu-id="68a36-130">Toto zobrazení zobrazí, když každý úkol dokončí stahování.</span><span class="sxs-lookup"><span data-stu-id="68a36-130">This display shows when each task has finished downloading.</span></span>  
  
     <span data-ttu-id="68a36-131">Zkopírujte následující metody a vložte je po `startButton_Click` obslužné rutiny událostí v MainWindow.xaml.vb.</span><span class="sxs-lookup"><span data-stu-id="68a36-131">Copy the following methods, and paste them after the `startButton_Click` event handler in MainWindow.xaml.vb.</span></span>  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
4.  <span data-ttu-id="68a36-132">Nakonec zadejte metoda `CreateMultipleTasksAsync`, který provede následující kroky.</span><span class="sxs-lookup"><span data-stu-id="68a36-132">Finally, define method `CreateMultipleTasksAsync`, which performs the following steps.</span></span>  
  
    -   <span data-ttu-id="68a36-133">Deklaruje metodu `HttpClient` objekt, který potřebujete přístup k metodě <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> v `ProcessURLAsync`.</span><span class="sxs-lookup"><span data-stu-id="68a36-133">The method declares an `HttpClient` object,which you need  to access method <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> in `ProcessURLAsync`.</span></span>  
  
    -   <span data-ttu-id="68a36-134">Metoda vytvoří a spustí tři úlohy typu <xref:System.Threading.Tasks.Task%601>, kde `TResult` je celé číslo.</span><span class="sxs-lookup"><span data-stu-id="68a36-134">The method creates and starts three tasks of type <xref:System.Threading.Tasks.Task%601>, where `TResult` is an integer.</span></span> <span data-ttu-id="68a36-135">Když každý úkol dokončí, `DisplayResults` zobrazí adresa URL úkolu a délka stažený obsah.</span><span class="sxs-lookup"><span data-stu-id="68a36-135">As each task finishes, `DisplayResults` displays the task's URL and the length of the downloaded contents.</span></span> <span data-ttu-id="68a36-136">Vzhledem k tomu, že úlohy běží asynchronně, pořadí, ve kterém se zobrazí výsledky se může lišit od pořadí, ve kterém bylo deklarováno.</span><span class="sxs-lookup"><span data-stu-id="68a36-136">Because the tasks are running asynchronously, the order in which the results appear might differ from the order in which they were declared.</span></span>  
  
    -   <span data-ttu-id="68a36-137">Metoda čeká na dokončení každé úlohy.</span><span class="sxs-lookup"><span data-stu-id="68a36-137">The method awaits the completion of each task.</span></span> <span data-ttu-id="68a36-138">Každý `Await` operátor pozastaví spuštění `CreateMultipleTasksAsync` dokončení awaited úloh.</span><span class="sxs-lookup"><span data-stu-id="68a36-138">Each `Await` operator suspends execution of `CreateMultipleTasksAsync` until the awaited task is finished.</span></span> <span data-ttu-id="68a36-139">Operátor také načte návratová hodnota z volání `ProcessURLAsync` z každé dokončené úlohy.</span><span class="sxs-lookup"><span data-stu-id="68a36-139">The operator also retrieves the return value from the call to `ProcessURLAsync` from each completed task.</span></span>  
  
    -   <span data-ttu-id="68a36-140">Když byly dokončeny úlohy a byly získány celočíselné hodnoty, metoda sečte délek weby a zobrazí výsledek.</span><span class="sxs-lookup"><span data-stu-id="68a36-140">When the tasks have been completed and the integer values have been retrieved, the method sums the lengths of the websites and displays the result.</span></span>  
  
     <span data-ttu-id="68a36-141">Zkopírujte následující metodu a vložte jej do řešení.</span><span class="sxs-lookup"><span data-stu-id="68a36-141">Copy the following method, and paste it into your solution.</span></span>  
  
    ```vb  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
    ```  
  
5.  <span data-ttu-id="68a36-142">Zvolte klávesy F5 spusťte program a potom vyberte **spustit** tlačítko.</span><span class="sxs-lookup"><span data-stu-id="68a36-142">Choose the F5 key to run the program, and then choose the **Start** button.</span></span>  
  
     <span data-ttu-id="68a36-143">Spusťte program pro ověření, že tři úlohy není vždy dokončit ve stejném pořadí a pořadí, ve kterém dokončit není nutně pořadí, ve které jste vytvořili a očekávaná několikrát.</span><span class="sxs-lookup"><span data-stu-id="68a36-143">Run the program several times to verify that the three tasks don’t always finish in the same order and that the order in which they finish isn't necessarily the order in which they’re created and awaited.</span></span>  
  
## <a name="example"></a><span data-ttu-id="68a36-144">Příklad</span><span class="sxs-lookup"><span data-stu-id="68a36-144">Example</span></span>  
 <span data-ttu-id="68a36-145">Následující kód obsahuje kompletní příklad.</span><span class="sxs-lookup"><span data-stu-id="68a36-145">The following code contains the full example.</span></span>  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
        resultsTextBox.Clear()  
        Await CreateMultipleTasksAsync()  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a><span data-ttu-id="68a36-146">Viz také</span><span class="sxs-lookup"><span data-stu-id="68a36-146">See Also</span></span>  
 [<span data-ttu-id="68a36-147">Návod: Přístup k webu pomocí modifikátoru Async a operátoru Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a36-147">Walkthrough: Accessing the Web by Using Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [<span data-ttu-id="68a36-148">Asynchronní programování pomocí modifikátoru Async a operátoru Await (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a36-148">Asynchronous Programming with Async and Await (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [<span data-ttu-id="68a36-149">Postupy: rozšíření návodu asynchronních úloh pomocí metody Task.WhenAll (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a36-149">How to: Extend the Async Walkthrough by Using Task.WhenAll (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)