---
title: ProgressBar コントロールによって表示される値を設定する
description: Windows フォーム ProgressBar コントロールによって表示される値を設定する方法について説明します。 使用できる方法は複数あります。
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- ProgressBar control [Windows Forms], setting value displayed
- progress controls [Windows Forms], setting value displayed
ms.assetid: 0e5010ad-1e9a-4271-895e-5a3d24d37a26
ms.openlocfilehash: 75fe1b416636471d797a39134f45a05c972c9d39
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982815"
---
# <a name="how-to-set-the-value-displayed-by-the-windows-forms-progressbar-control"></a><span data-ttu-id="4895f-104">方法: Windows フォーム ProgressBar コントロールによって表示される値を設定する</span><span class="sxs-lookup"><span data-stu-id="4895f-104">How to: Set the Value Displayed by the Windows Forms ProgressBar Control</span></span>
> [!IMPORTANT]
> <span data-ttu-id="4895f-105"><xref:System.Windows.Forms.ToolStripProgressBar> コントロールは、<xref:System.Windows.Forms.ProgressBar> コントロールに代わると共に追加の機能を提供します。ただし、<xref:System.Windows.Forms.ProgressBar> コントロールは、下位互換性を保つ目的および将来使用する目的で保持されます。</span><span class="sxs-lookup"><span data-stu-id="4895f-105">The <xref:System.Windows.Forms.ToolStripProgressBar> control replaces and adds functionality to the <xref:System.Windows.Forms.ProgressBar> control; however, the <xref:System.Windows.Forms.ProgressBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="4895f-106">.NET Framework には、コントロール内に特定の値を表示するさまざまな方法が用意されて <xref:System.Windows.Forms.ProgressBar> います。</span><span class="sxs-lookup"><span data-stu-id="4895f-106">The .NET Framework gives you several different ways to display a given value within the <xref:System.Windows.Forms.ProgressBar> control.</span></span> <span data-ttu-id="4895f-107">どの方法を選択するかは、当面のタスクや、解決する問題によって異なります。</span><span class="sxs-lookup"><span data-stu-id="4895f-107">Which approach you choose will depend on the task at hand or the problem you are solving.</span></span> <span data-ttu-id="4895f-108">次の表に、選択できる方法を示します。</span><span class="sxs-lookup"><span data-stu-id="4895f-108">The following table shows the approaches you can choose.</span></span>  
  
|<span data-ttu-id="4895f-109">アプローチ</span><span class="sxs-lookup"><span data-stu-id="4895f-109">Approach</span></span>|<span data-ttu-id="4895f-110">説明</span><span class="sxs-lookup"><span data-stu-id="4895f-110">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="4895f-111">コントロールの値を <xref:System.Windows.Forms.ProgressBar> 直接設定します。</span><span class="sxs-lookup"><span data-stu-id="4895f-111">Set the value of the <xref:System.Windows.Forms.ProgressBar> control directly.</span></span>|<span data-ttu-id="4895f-112">この方法は、データソースからのレコードの読み取りなど、関連する項目の合計がわかっているタスクに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4895f-112">This approach is useful for tasks where you know the total of the item measured that will be involved, such as reading records from a data source.</span></span> <span data-ttu-id="4895f-113">また、値を1回または2回だけ設定する必要がある場合は、これを簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4895f-113">Additionally, if you only need to set the value once or twice, this is an easy way to do it.</span></span> <span data-ttu-id="4895f-114">最後に、進行状況バーに表示される値を小さくする必要がある場合に、このプロセスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4895f-114">Finally, use this process if you need to decrease the value displayed by the progress bar.</span></span>|  
|<span data-ttu-id="4895f-115"><xref:System.Windows.Forms.ProgressBar>固定値で表示を増やします。</span><span class="sxs-lookup"><span data-stu-id="4895f-115">Increase the <xref:System.Windows.Forms.ProgressBar> display by a fixed value.</span></span>|<span data-ttu-id="4895f-116">この方法は、最小値と最大値の間に単純なカウント (経過時間、または既知の合計から処理されたファイルの数など) を表示する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="4895f-116">This approach is useful when you are displaying a simple count between the minimum and maximum, such as elapsed time or the number of files that have been processed out of a known total.</span></span>|  
|<span data-ttu-id="4895f-117"><xref:System.Windows.Forms.ProgressBar>変化する値で表示を増やします。</span><span class="sxs-lookup"><span data-stu-id="4895f-117">Increase the <xref:System.Windows.Forms.ProgressBar> display by a value that varies.</span></span>|<span data-ttu-id="4895f-118">この方法は、表示された値をさまざまな量の回数だけ変更する必要がある場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="4895f-118">This approach is useful when you need to change the displayed value a number of times in different amounts.</span></span> <span data-ttu-id="4895f-119">たとえば、一連のファイルをディスクに書き込んでいる間に消費されているハードディスク領域の量を示します。</span><span class="sxs-lookup"><span data-stu-id="4895f-119">An example would be showing the amount of hard-disk space being consumed while writing a series of files to the disk.</span></span>|  
  
 <span data-ttu-id="4895f-120">プログレスバーに表示される値を設定する最も直接的な方法は、プロパティを設定することです <xref:System.Windows.Forms.ProgressBar.Value%2A> 。</span><span class="sxs-lookup"><span data-stu-id="4895f-120">The most direct way to set the value displayed by a progress bar is by setting the <xref:System.Windows.Forms.ProgressBar.Value%2A> property.</span></span> <span data-ttu-id="4895f-121">これは、デザイン時または実行時に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="4895f-121">This can be done either at design time or at run time.</span></span>  
  
### <a name="to-set-the-progressbar-value-directly"></a><span data-ttu-id="4895f-122">ProgressBar 値を直接設定するには</span><span class="sxs-lookup"><span data-stu-id="4895f-122">To set the ProgressBar value directly</span></span>  
  
1. <span data-ttu-id="4895f-123"><xref:System.Windows.Forms.ProgressBar>コントロールの <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 値と値を設定 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> します。</span><span class="sxs-lookup"><span data-stu-id="4895f-123">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="4895f-124">コードで、コントロールのプロパティを、設定 <xref:System.Windows.Forms.ProgressBar.Value%2A> した最小値と最大値の間の整数値に設定します。</span><span class="sxs-lookup"><span data-stu-id="4895f-124">In code, set the control's <xref:System.Windows.Forms.ProgressBar.Value%2A> property to an integer value between the minimum and maximum values you have established.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="4895f-125"><xref:System.Windows.Forms.ProgressBar.Value%2A>プロパティとプロパティによって確立された境界の外側でプロパティを設定した場合 <xref:System.Windows.Forms.ProgressBar.Minimum%2A> <xref:System.Windows.Forms.ProgressBar.Maximum%2A> 、コントロールは例外をスロー <xref:System.ArgumentException> します。</span><span class="sxs-lookup"><span data-stu-id="4895f-125">If you set the <xref:System.Windows.Forms.ProgressBar.Value%2A> property outside the boundaries established by the <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> properties, the control throws an <xref:System.ArgumentException> exception.</span></span>  
  
     <span data-ttu-id="4895f-126">次のコード例は、値を直接設定する方法を示してい <xref:System.Windows.Forms.ProgressBar> ます。</span><span class="sxs-lookup"><span data-stu-id="4895f-126">The following code example illustrates how to set the <xref:System.Windows.Forms.ProgressBar> value directly.</span></span> <span data-ttu-id="4895f-127">このコードは、データソースからレコードを読み取り、データレコードが読み取られるたびに進行状況バーとラベルを更新します。</span><span class="sxs-lookup"><span data-stu-id="4895f-127">The code reads records from a data source and updates the progress bar and label every time a data record is read.</span></span> <span data-ttu-id="4895f-128">この例では、フォームに <xref:System.Windows.Forms.Label> コントロール、 <xref:System.Windows.Forms.ProgressBar> コントロール、 `CustomerRow` およびフィールドとフィールドを持つという行を持つデータテーブルが `FirstName` あることが必要です `LastName` 。</span><span class="sxs-lookup"><span data-stu-id="4895f-128">This example requires that your form has a <xref:System.Windows.Forms.Label> control, a <xref:System.Windows.Forms.ProgressBar> control, and a data table with a row called `CustomerRow` with `FirstName` and `LastName` fields.</span></span>  
  
    ```vb  
    Public Sub CreateNewRecords()  
       ' Sets the progress bar's Maximum property to  
       ' the total number of records to be created.  
       ProgressBar1.Maximum = 20  
  
       ' Creates a new record in the dataset.  
       ' NOTE: The code below will not compile, it merely  
       ' illustrates how the progress bar would be used.  
       Dim anyRow As CustomerRow = DatasetName.ExistingTable.NewRow  
       anyRow.FirstName = "Stephen"  
       anyRow.LastName = "James"  
       ExistingTable.Rows.Add(anyRow)  
  
       ' Increases the value displayed by the progress bar.  
       ProgressBar1.Value += 1  
       ' Updates the label to show that a record was read.  
       Label1.Text = "Records Read = " & ProgressBar1.Value.ToString()  
    End Sub  
    ```  
  
    ```csharp  
    public void createNewRecords()  
    {  
       // Sets the progress bar's Maximum property to  
       // the total number of records to be created.  
       progressBar1.Maximum = 20;  
  
       // Creates a new record in the dataset.  
       // NOTE: The code below will not compile, it merely  
       // illustrates how the progress bar would be used.  
       CustomerRow anyRow = DatasetName.ExistingTable.NewRow();  
       anyRow.FirstName = "Stephen";  
       anyRow.LastName = "James";  
       ExistingTable.Rows.Add(anyRow);  
  
       // Increases the value displayed by the progress bar.  
       progressBar1.Value += 1;  
       // Updates the label to show that a record was read.  
       label1.Text = "Records Read = " + progressBar1.Value.ToString();  
    }  
    ```  
  
     一定の間隔で進行状況を表示している場合は、値を設定してから、 <xref:System.Windows.Forms.ProgressBar> その間隔でコントロールの値を増やすメソッドを呼び出すことができます。 <span data-ttu-id="4895f-130">これは、タイマーや、進行状況を全体に対する割合として測定しないその他のシナリオに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="4895f-130">This is useful for timers and other scenarios where you are not measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-fixed-value"></a><span data-ttu-id="4895f-131">プログレスバーを固定値で増やすには</span><span class="sxs-lookup"><span data-stu-id="4895f-131">To increase the progress bar by a fixed value</span></span>  
  
1. <span data-ttu-id="4895f-132"><xref:System.Windows.Forms.ProgressBar>コントロールの <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 値と値を設定 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> します。</span><span class="sxs-lookup"><span data-stu-id="4895f-132">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="4895f-133">コントロールのプロパティを、 <xref:System.Windows.Forms.ProgressBar.Step%2A> その量を表す整数に設定して、進行状況バーの表示値を増やします。</span><span class="sxs-lookup"><span data-stu-id="4895f-133">Set the control's <xref:System.Windows.Forms.ProgressBar.Step%2A> property to an integer representing the amount to increase the progress bar's displayed value.</span></span>  
  
3. <span data-ttu-id="4895f-134">メソッドを呼び出し <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> て、プロパティで設定された量によって表示される値を変更し <xref:System.Windows.Forms.ProgressBar.Step%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="4895f-134">Call the <xref:System.Windows.Forms.ProgressBar.PerformStep%2A> method to change the value displayed by the amount set in the <xref:System.Windows.Forms.ProgressBar.Step%2A> property.</span></span>  
  
     <span data-ttu-id="4895f-135">次のコード例は、進行状況バーがコピー操作でファイルの数を保持する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4895f-135">The following code example illustrates how a progress bar can maintain a count of the files in a copy operation.</span></span>  
  
     <span data-ttu-id="4895f-136">次の例では、各ファイルがメモリに読み込まれると、進行状況バーとラベルが更新され、読み取られたファイルの合計が反映されます。</span><span class="sxs-lookup"><span data-stu-id="4895f-136">In the following example, as each file is read into memory, the progress bar and label are updated to reflect the total files read.</span></span> <span data-ttu-id="4895f-137">この例では、フォームにコントロールとコントロールが含まれている必要があり <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.ProgressBar> ます。</span><span class="sxs-lookup"><span data-stu-id="4895f-137">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
    ```vb  
    Public Sub LoadFiles()  
       ' Sets the progress bar's minimum value to a number representing  
       ' no operations complete -- in this case, no files read.  
       ProgressBar1.Minimum = 0  
       ' Sets the progress bar's maximum value to a number representing  
       ' all operations complete -- in this case, all five files read.  
       ProgressBar1.Maximum = 5  
       ' Sets the Step property to amount to increase with each iteration.  
       ' In this case, it will increase by one with every file read.  
       ProgressBar1.Step = 1  
  
       ' Dimensions a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be copied into memory,  
       ' so the loop will execute 5 times.  
       For i = 0 To 4  
          ' Insert code to copy a file  
          ProgressBar1.PerformStep()  
          ' Update the label to show that a file was read.  
          Label1.Text = "# of Files Read = " & ProgressBar1.Value.ToString  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void loadFiles()  
    {  
       // Sets the progress bar's minimum value to a number representing  
       // no operations complete -- in this case, no files read.  
       progressBar1.Minimum = 0;  
       // Sets the progress bar's maximum value to a number representing  
       // all operations complete -- in this case, all five files read.  
       progressBar1.Maximum = 5;  
       // Sets the Step property to amount to increase with each iteration.  
       // In this case, it will increase by one with every file read.  
       progressBar1.Step = 1;  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be copied into memory,  
       // so the loop will execute 5 times.  
       for (int i = 0; i <= 4; i++)  
       {  
          // Inserts code to copy a file  
          progressBar1.PerformStep();  
          // Updates the label to show that a file was read.  
          label1.Text = "# of Files Read = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
     最後に、各増加が一意の値になるように、進行状況バーによって表示される値を増やすことができます。 <span data-ttu-id="4895f-139">これは、さまざまなサイズのファイルをハードディスクに書き込む場合や、進行状況を全体の割合として測定する場合など、一連の一意の操作を追跡する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="4895f-139">This is useful when you are keeping track of a series of unique operations, such as writing files of different sizes to a hard disk, or measuring progress as a percentage of the whole.</span></span>  
  
### <a name="to-increase-the-progress-bar-by-a-dynamic-value"></a><span data-ttu-id="4895f-140">動的な値で進行状況バーを拡大するには</span><span class="sxs-lookup"><span data-stu-id="4895f-140">To increase the progress bar by a dynamic value</span></span>  
  
1. <span data-ttu-id="4895f-141"><xref:System.Windows.Forms.ProgressBar>コントロールの <xref:System.Windows.Forms.ProgressBar.Minimum%2A> 値と値を設定 <xref:System.Windows.Forms.ProgressBar.Maximum%2A> します。</span><span class="sxs-lookup"><span data-stu-id="4895f-141">Set the <xref:System.Windows.Forms.ProgressBar> control's <xref:System.Windows.Forms.ProgressBar.Minimum%2A> and <xref:System.Windows.Forms.ProgressBar.Maximum%2A> values.</span></span>  
  
2. <span data-ttu-id="4895f-142">指定し <xref:System.Windows.Forms.ProgressBar.Increment%2A> た整数によって表示される値を変更するには、メソッドを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="4895f-142">Call the <xref:System.Windows.Forms.ProgressBar.Increment%2A> method to change the value displayed by an integer you specify.</span></span>  
  
     <span data-ttu-id="4895f-143">次のコード例は、コピー操作中にどの程度のディスク領域が使用されたかを、進行状況バーで計算する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="4895f-143">The following code example illustrates how a progress bar can calculate how much disk space has been used during a copy operation.</span></span>  
  
     <span data-ttu-id="4895f-144">次の例では、各ファイルがハードディスクに書き込まれると、進行状況バーとラベルが更新され、使用可能なハードディスク領域の容量が反映されます。</span><span class="sxs-lookup"><span data-stu-id="4895f-144">In the following example, as each file is written to the hard disk, the progress bar and label are updated to reflect the amount of hard-disk space available.</span></span> <span data-ttu-id="4895f-145">この例では、フォームにコントロールとコントロールが含まれている必要があり <xref:System.Windows.Forms.Label> <xref:System.Windows.Forms.ProgressBar> ます。</span><span class="sxs-lookup"><span data-stu-id="4895f-145">This example requires that your form has a <xref:System.Windows.Forms.Label> control and a <xref:System.Windows.Forms.ProgressBar> control.</span></span>  
  
    ```vb  
    Public Sub ReadFiles()  
       ' Sets the progress bar's minimum value to a number
       ' representing the hard disk space before the files are read in.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example and  
       ' will not compile.  
       ProgressBar1.Minimum = AvailableDiskSpace()  
       ' Sets the progress bar's maximum value to a number
       ' representing the total hard disk space.  
       ' You will most likely have to set this using a system call.  
       ' NOTE: The code below is meant to be an example
       ' and will not compile.  
       ProgressBar1.Maximum = TotalDiskSpace()  
  
       ' Dimension a counter variable.  
       Dim i As Integer  
       ' Uses a For...Next loop to iterate through the operations to be  
       ' completed. In this case, five files are to be written to the disk,  
       ' so it will execute the loop 5 times.  
       For i = 1 To 5  
          ' Insert code to read a file into memory and update file size.  
          ' Increases the progress bar's value based on the size of
          ' the file currently being written.  
          ProgressBar1.Increment(FileSize)  
          ' Updates the label to show available drive space.  
          Label1.Text = "Current Disk Space Used = " &_
          ProgressBar1.Value.ToString()  
       Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void readFiles()  
    {  
       // Sets the progress bar's minimum value to a number
       // representing the hard disk space before the files are read in.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example and
       // will not compile.  
       progressBar1.Minimum = AvailableDiskSpace();  
       // Sets the progress bar's maximum value to a number
       // representing the total hard disk space.  
       // You will most likely have to set this using a system call.  
       // NOTE: The code below is meant to be an example
       // and will not compile.  
       progressBar1.Maximum = TotalDiskSpace();  
  
       // Uses a for loop to iterate through the operations to be  
       // completed. In this case, five files are to be written  
       // to the disk, so it will execute the loop 5 times.  
       for (int i = 1; i<= 5; i++)  
       {  
          // Insert code to read a file into memory and update file size.  
          // Increases the progress bar's value based on the size of
          // the file currently being written.  
          progressBar1.Increment(FileSize);  
          // Updates the label to show available drive space.  
          label1.Text = "Current Disk Space Used = " + progressBar1.Value.ToString();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4895f-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="4895f-146">See also</span></span>

- <xref:System.Windows.Forms.ProgressBar>
- <xref:System.Windows.Forms.ToolStripProgressBar>
- [<span data-ttu-id="4895f-147">ProgressBar コントロールの概要</span><span class="sxs-lookup"><span data-stu-id="4895f-147">ProgressBar Control Overview</span></span>](progressbar-control-overview-windows-forms.md)
- [<span data-ttu-id="4895f-148">ProgressBar コントロール</span><span class="sxs-lookup"><span data-stu-id="4895f-148">ProgressBar Control</span></span>](progressbar-control-windows-forms.md)
