---
title: ファイルとデータへのより安全なアクセス
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- security [Windows Forms], file access
- registry [Windows Forms]
- data access [Windows Forms]
- database access (Windows Forms security)
- data [Windows Forms], secure access
- file access [Windows Forms]
- security [Windows Forms], data access
ms.assetid: 3cd3e55b-2f5e-40dd-835d-f50f7ce08967
ms.openlocfilehash: 880b5414143b827dabb0ff1fb0a16649ace5a035
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983172"
---
# <a name="more-secure-file-and-data-access-in-windows-forms"></a><span data-ttu-id="fbe82-102">Windows フォームにおけるファイルおよびデータへのより安全なアクセス</span><span class="sxs-lookup"><span data-stu-id="fbe82-102">More Secure File and Data Access in Windows Forms</span></span>

<span data-ttu-id="fbe82-103">.NET Framework は、リソースとデータを保護するためにアクセス許可を使用します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-103">The .NET Framework uses permissions to help protect resources and data.</span></span> <span data-ttu-id="fbe82-104">アプリケーションでデータを読み取りまたは書き込みできる場所は、アプリケーションに付与されるアクセス許可に依存します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-104">Where your application can read or write data depends on the permissions granted to the application.</span></span> <span data-ttu-id="fbe82-105">部分信頼環境でアプリケーションを実行すると、データにアクセス許可がないか、またはデータにアクセスする方法を変更しなければならない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fbe82-105">When your application runs in a partial trust environment, you might not have access to your data or you might have to change the way you access the data.</span></span>  
  
 <span data-ttu-id="fbe82-106">セキュリティの制限が発生した場合、アクセス許可をアサートする (アプリケーションに付与されていると仮定した場合)、または部分信頼で動作するよう作成されたバージョンの機能を使用するという 2 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="fbe82-106">When you encounter a security restriction, you have two options: assert the permission (assuming it has been granted to your application), or use a version of the feature written to work in partial trust.</span></span> <span data-ttu-id="fbe82-107">次のセクションでは、部分信頼環境で実行されているアプリケーションからファイル、データベース、およびレジストリ アクセスを操作する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-107">The following sections discuss how to work with file, database, and registry access from applications that are running in a partial trust environment.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fbe82-108">既定では、ClickOnce 配置を生成するツールは、これらの展開を実行するコンピューターから完全信頼を要求するように既定で設定されています。</span><span class="sxs-lookup"><span data-stu-id="fbe82-108">By default, tools that generate ClickOnce deployments default these deployments to requesting Full Trust from the computers on which they run.</span></span> <span data-ttu-id="fbe82-109">部分信頼でを実行するという追加のセキュリティ上の利点が必要な場合は、Visual Studio またはいずれかの Windows SDK ツール (Mage.exe または MageUI.exe) でこの既定値を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbe82-109">If you decide you want the added security benefits of running in partial trust, you must change this default in either Visual Studio or one of the Windows SDK tools (Mage.exe or MageUI.exe).</span></span> <span data-ttu-id="fbe82-110">Windows フォームセキュリティの詳細と、アプリケーションの適切な信頼レベルを決定する方法については、「 [Windows フォームの概要」の「セキュリティ](security-in-windows-forms-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbe82-110">For more information about Windows Forms security, and on how to determine the appropriate trust level for your application, see [Security in Windows Forms Overview](security-in-windows-forms-overview.md).</span></span>  
  
## <a name="file-access"></a><span data-ttu-id="fbe82-111">ファイル アクセス</span><span class="sxs-lookup"><span data-stu-id="fbe82-111">File Access</span></span>  

 <span data-ttu-id="fbe82-112">クラスは、 <xref:System.Security.Permissions.FileIOPermission> .NET Framework 内のファイルとフォルダーへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-112">The <xref:System.Security.Permissions.FileIOPermission> class controls file and folder access in the .NET Framework.</span></span> <span data-ttu-id="fbe82-113">既定では、セキュリティ システムは、ローカルのイントラネットやインターネット ゾーンなどの部分信頼環境に <xref:System.Security.Permissions.FileIOPermission> を付与しません。</span><span class="sxs-lookup"><span data-stu-id="fbe82-113">By default, the security system does not grant the <xref:System.Security.Permissions.FileIOPermission> to partial trust environments such as the local intranet and Internet zones.</span></span> <span data-ttu-id="fbe82-114">ただし、ファイルへのアクセスを必要とするアプリケーションは、アプリケーションの設計を変更するかファイルにアクセスする別の方法を使用すると、引き続きこれらの環境で機能することが可能です。</span><span class="sxs-lookup"><span data-stu-id="fbe82-114">However, an application that requires file access can still function in these environments if you modify the design of your application or use different methods to access files.</span></span> <span data-ttu-id="fbe82-115">既定では、ローカル イントラネット ゾーンに、同じサイトと同じディレクトリにアクセスして、その起点のサイトに接続し、インストール ディレクトリから読み取るための権限が付与されます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-115">By default, the local intranet zone is granted the right to have same site access and same directory access, to connect back to the site of its origin, and to read from its installation directory.</span></span> <span data-ttu-id="fbe82-116">既定では、インターネット ゾーンは、起点のサイトに接続する権限のみが付与されます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-116">By default, the Internet zone, is only granted the right to connect back to the site of its origin.</span></span>  
  
### <a name="user-specified-files"></a><span data-ttu-id="fbe82-117">ユーザー指定のファイル</span><span class="sxs-lookup"><span data-stu-id="fbe82-117">User-Specified Files</span></span>  

 <span data-ttu-id="fbe82-118">ファイルへのアクセス許可を持たないときに処理する方法の 1 つは、<xref:System.Windows.Forms.OpenFileDialog> クラスまたは <xref:System.Windows.Forms.SaveFileDialog> クラスを使用して、特定のファイル情報の入力をユーザーに求める方法です。</span><span class="sxs-lookup"><span data-stu-id="fbe82-118">One way to deal with not having file access permission is to prompt the user to provide specific file information by using the <xref:System.Windows.Forms.OpenFileDialog> or <xref:System.Windows.Forms.SaveFileDialog> class.</span></span> <span data-ttu-id="fbe82-119">このユーザーの操作では、アプリケーションが悪意を持ってプライベート ファイルを読み込んだり、重要なファイルを上書きしたりできないことを、ある程度保証できます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-119">This user interaction helps provide some assurance that the application cannot maliciously load private files or overwrite important files.</span></span> <span data-ttu-id="fbe82-120"><xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> メソッドと <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> メソッドは、ユーザーが指定したファイルのファイル ストリームを開くことで、ファイルの読み取りアクセスと書き込みアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-120">The <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> and <xref:System.Windows.Forms.SaveFileDialog.OpenFile%2A> methods provide read and write file access by opening the file stream for the file that the user specified.</span></span> <span data-ttu-id="fbe82-121">メソッドは、ファイルのパスを隠すことで、ユーザーのファイルの保護にも役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-121">The methods also help protect the user's file by obscuring the file's path.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fbe82-122">これらのアクセス許可は、アプリケーションが、インターネット ゾーン内かイントラネット ゾーン内かに応じて異なります。</span><span class="sxs-lookup"><span data-stu-id="fbe82-122">These permissions differ depending on whether your application is in the Internet zone or Intranet zone.</span></span> <span data-ttu-id="fbe82-123">インターネット ゾーンのアプリケーションは <xref:System.Windows.Forms.OpenFileDialog> のみを使用できますが、イントラネット アプリケーションは、無制限のファイル ダイアログのアクセス許可を持っています。</span><span class="sxs-lookup"><span data-stu-id="fbe82-123">Internet zone applications can only use the <xref:System.Windows.Forms.OpenFileDialog>, whereas Intranet applications have unrestricted file dialog permission.</span></span>  
  
 <span data-ttu-id="fbe82-124"><xref:System.Security.Permissions.FileDialogPermission> クラスは、アプリケーションで使用できるファイル ダイアログ ボックスの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-124">The <xref:System.Security.Permissions.FileDialogPermission> class specifies what type of file dialog box your application can use.</span></span> <span data-ttu-id="fbe82-125">次の表は、各 <xref:System.Windows.Forms.FileDialog> クラスを使用するために必要な値を示しています。</span><span class="sxs-lookup"><span data-stu-id="fbe82-125">The following table shows the value you must have to use each <xref:System.Windows.Forms.FileDialog> class.</span></span>  
  
|<span data-ttu-id="fbe82-126">クラス</span><span class="sxs-lookup"><span data-stu-id="fbe82-126">Class</span></span>|<span data-ttu-id="fbe82-127">必要なアクセス権の値</span><span class="sxs-lookup"><span data-stu-id="fbe82-127">Required access value</span></span>|  
|-----------|---------------------------|  
|<xref:System.Windows.Forms.OpenFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Open>|  
|<xref:System.Windows.Forms.SaveFileDialog>|<xref:System.Security.Permissions.FileDialogPermissionAccess.Save>|  
  
> [!NOTE]
> <span data-ttu-id="fbe82-128"><xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> メソッドが実際に呼び出されるまでは、特定のアクセス許可は要求されません。</span><span class="sxs-lookup"><span data-stu-id="fbe82-128">The specific permission is not requested until the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method is actually called.</span></span>  
  
 <span data-ttu-id="fbe82-129">ファイル ダイアログ ボックスを表示するためのアクセス許可は、<xref:System.Windows.Forms.FileDialog>、<xref:System.Windows.Forms.OpenFileDialog>、および <xref:System.Windows.Forms.SaveFileDialog> の各クラスのすべてのメンバーに対するフルアクセスをアプリケーションに付与しません。</span><span class="sxs-lookup"><span data-stu-id="fbe82-129">Permission to display a file dialog box does not grant your application full access to all members of the <xref:System.Windows.Forms.FileDialog>, <xref:System.Windows.Forms.OpenFileDialog>, and <xref:System.Windows.Forms.SaveFileDialog> classes.</span></span> <span data-ttu-id="fbe82-130">各メソッドを呼び出すために必要なアクセス許可については、.NET Framework クラスライブラリのドキュメントで、そのメソッドのリファレンストピックを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbe82-130">For the exact permissions that are required to call each method, see the reference topic for that method in the .NET Framework class library documentation.</span></span>  
  
 <span data-ttu-id="fbe82-131">次のコード例では、<xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> メソッドを使用して、ユーザーが指定したファイルを <xref:System.Windows.Forms.RichTextBox> コントロールに開きます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-131">The following code example uses the <xref:System.Windows.Forms.OpenFileDialog.OpenFile%2A> method to open a user-specified file into a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="fbe82-132">この例では、<xref:System.Security.Permissions.FileDialogPermission> および関連付けられた <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> 列挙値が必要です。</span><span class="sxs-lookup"><span data-stu-id="fbe82-132">The example requires <xref:System.Security.Permissions.FileDialogPermission> and the associated <xref:System.Security.Permissions.FileDialogPermissionAttribute.Open%2A> enumeration value.</span></span> <span data-ttu-id="fbe82-133">例では、保存機能を無効にする必要があるかどうかを判断するために、<xref:System.Security.SecurityException> を処理する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="fbe82-133">The example demonstrates how to handle the <xref:System.Security.SecurityException> to determine whether the save feature should be disabled.</span></span> <span data-ttu-id="fbe82-134">この例では、<xref:System.Windows.Forms.Form> が `ButtonOpen` という名前の <xref:System.Windows.Forms.Button> コントロールと、`RtfBoxMain` という名前の <xref:System.Windows.Forms.RichTextBox> コントロールを必要とします。</span><span class="sxs-lookup"><span data-stu-id="fbe82-134">This example requires that your <xref:System.Windows.Forms.Form> has a <xref:System.Windows.Forms.Button> control named `ButtonOpen`, and a <xref:System.Windows.Forms.RichTextBox> control named `RtfBoxMain`.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fbe82-135">保存機能のプログラミング ロジックは、この例では表示されません。</span><span class="sxs-lookup"><span data-stu-id="fbe82-135">The programming logic for the save feature is not shown in the example.</span></span>  
  
```vb  
Private Sub ButtonOpen_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles ButtonOpen.Click
  
    Dim editingFileName as String = ""  
    Dim saveAllowed As Boolean = True  
  
    ' Displays the OpenFileDialog.  
    If (OpenFileDialog1.ShowDialog() = DialogResult.OK) Then  
        Dim userStream as System.IO.Stream  
        Try
            ' Opens the file stream for the file selected by the user.  
            userStream =OpenFileDialog1.OpenFile()
            Me.RtfBoxMain.LoadFile(userStream, _  
                RichTextBoxStreamType.PlainText)  
        Finally  
            userStream.Close()  
        End Try  
  
        ' Tries to get the file name selected by the user.  
        ' Failure means that the application does not have  
        ' unrestricted permission to the file.  
        Try
            editingFileName = OpenFileDialog1.FileName  
        Catch ex As Exception  
            If TypeOf ex Is System.Security.SecurityException Then
                ' The application does not have unrestricted permission
                ' to the file so the save feature will be disabled.  
                saveAllowed = False
            Else
                Throw ex  
            End If  
        End Try  
    End If  
End Sub  
```  
  
```csharp  
private void ButtonOpen_Click(object sender, System.EventArgs e)
{  
    String editingFileName = "";  
    Boolean saveAllowed = true;  
  
    // Displays the OpenFileDialog.  
    if (openFileDialog1.ShowDialog() == DialogResult.OK)
    {  
        // Opens the file stream for the file selected by the user.  
        using (System.IO.Stream userStream = openFileDialog1.OpenFile())
        {  
            this.RtfBoxMain.LoadFile(userStream,  
                RichTextBoxStreamType.PlainText);  
            userStream.Close();  
        }  
  
        // Tries to get the file name selected by the user.  
        // Failure means that the application does not have  
        // unrestricted permission to the file.  
        try
        {  
            editingFileName = openFileDialog1.FileName;  
        }
        catch (Exception ex)
        {  
            if (ex is System.Security.SecurityException)
            {  
                // The application does not have unrestricted permission
                // to the file so the save feature will be disabled.  
                saveAllowed = false;
            }
            else
            {  
                throw ex;  
            }  
        }  
    }  
}  
```  
  
> [!NOTE]
> <span data-ttu-id="fbe82-136">Visual C# では、イベントハンドラーを有効にするコードを追加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-136">In Visual C#, ensure that you add code to enable the event handler.</span></span> <span data-ttu-id="fbe82-137">前の例でのコードを使用することで、次のコードではイベント ハンドラー `this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);` を有効にする方法を示します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-137">By using the code from the previous example, the following code shows how to enable the event handler.`this.ButtonOpen.Click += newSystem.Windows.Forms.EventHandler(this.ButtonOpen_Click);`</span></span>  
  
### <a name="other-files"></a><span data-ttu-id="fbe82-138">その他のファイル</span><span class="sxs-lookup"><span data-stu-id="fbe82-138">Other Files</span></span>  

 <span data-ttu-id="fbe82-139">場合によって、アプリケーション設定を保存しなければならないという場合など、ユーザーが指定しないファイルへの読み取りまたは書き込みを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fbe82-139">Sometimes you will need to read or write to files that the user does not specify, such as when you must persist application settings.</span></span> <span data-ttu-id="fbe82-140">ローカルのイントラネット ゾーンとインターネット ゾーンでは、アプリケーションにローカル ファイルにデータを格納するためのアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="fbe82-140">In the local intranet and Internet zones, your application will not have permission to store data in a local file.</span></span> <span data-ttu-id="fbe82-141">ただし、アプリケーションが分離ストレージにデータを格納できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fbe82-141">However, your application will be able to store data in isolated storage.</span></span> <span data-ttu-id="fbe82-142">分離ストレージは (特定の記憶場所ではなく) 抽象的なデータ コンパートメントであり、データが保存される実際のディレクトリの場所を含む、ストアと呼ばれる 1 つ以上の分離ストレージ ファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-142">Isolated storage is an abstract data compartment (not a specific storage location) that contains one or more isolated storage files, called stores, that contain the actual directory locations where data is stored.</span></span> <span data-ttu-id="fbe82-143"><xref:System.Security.Permissions.FileIOPermission> のようなファイルのアクセス許可は必要なく、代わりに <xref:System.Security.Permissions.IsolatedStoragePermission> クラスが分離ストレージのアクセス許可を制御します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-143">File access permissions like <xref:System.Security.Permissions.FileIOPermission> are not required; instead, the <xref:System.Security.Permissions.IsolatedStoragePermission> class controls the permissions for isolated storage.</span></span> <span data-ttu-id="fbe82-144">既定では、ローカル イントラネット ゾーンとインターネット ゾーンで実行されているアプリケーションが、分離ストレージを使用してデータを格納できます。ただし、ディスク クォータのように設定が変わることがあります。</span><span class="sxs-lookup"><span data-stu-id="fbe82-144">By default, applications that are running in the local intranet and Internet zones can store data using isolated storage; however, settings like disk quota can vary.</span></span> <span data-ttu-id="fbe82-145">分離ストレージの詳細については、「 [分離ストレージ](/dotnet/standard/io/isolated-storage)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbe82-145">For more information about isolated storage, see [Isolated Storage](/dotnet/standard/io/isolated-storage).</span></span>  
  
 <span data-ttu-id="fbe82-146">次の例では、分離ストレージを使用して、ストアにあるファイルにデータを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-146">The following example uses isolated storage to write data to a file located in a store.</span></span> <span data-ttu-id="fbe82-147">この例では、<xref:System.Security.Permissions.IsolatedStorageFilePermission> および <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> 列挙値が必要です。</span><span class="sxs-lookup"><span data-stu-id="fbe82-147">The example requires <xref:System.Security.Permissions.IsolatedStorageFilePermission> and the <xref:System.Security.Permissions.IsolatedStorageContainment.DomainIsolationByUser> enumeration value.</span></span> <span data-ttu-id="fbe82-148">例では、分離ストレージ内のファイルに対する、<xref:System.Windows.Forms.Button> コントロールの特定のプロパティ値の読み取りと書き込みを示しています。</span><span class="sxs-lookup"><span data-stu-id="fbe82-148">The example demonstrates reading and writing certain property values of the <xref:System.Windows.Forms.Button> control to a file in isolated storage.</span></span> <span data-ttu-id="fbe82-149">`Read` 関数はアプリケーションの起動後に呼び出され、`Write` 関数はアプリケーションの終了前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-149">The `Read` function would be called after the application starts and the `Write` function would be called before the application ends.</span></span> <span data-ttu-id="fbe82-150">この例では、 `Read` 関数と関数が、と `Write` <xref:System.Windows.Forms.Form> いう名前のコントロールを含むのメンバーとして存在する必要があり <xref:System.Windows.Forms.Button> `MainButton` ます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-150">The example requires that the `Read` and `Write` functions exist as members of a <xref:System.Windows.Forms.Form> that contains a <xref:System.Windows.Forms.Button> control named `MainButton`.</span></span>  
  
```vb  
' Reads the button options from the isolated storage. Uses Default values
' for the button if the options file does not exist.  
Public Sub Read()
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try  
        ' Checks to see if the options.txt file exists.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
  
            ' Opens the file because it exists.  
            Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _
                 (filename, IO.FileMode.Open,isoStore)  
            Dim reader as System.IO.StreamReader  
            Try
                reader = new System.IO.StreamReader(isos)  
  
                ' Reads the values stored.  
                Dim converter As System.ComponentModel.TypeConverter  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _
                    (GetType(Color))  
  
                Me.MainButton.BackColor = _
                        CType(converter.ConvertFromString _
                         (reader.ReadLine()), Color)  
                me.MainButton.ForeColor = _  
                        CType(converter.ConvertFromString _
                         (reader.ReadLine()), Color)  
  
                converter = System.ComponentModel.TypeDescriptor.GetConverter _
                    (GetType(Font))  
                me.MainButton.Font = _  
                        CType(converter.ConvertFromString _
                         (reader.ReadLine()), Font)  
  
            Catch ex As Exception  
                Debug.WriteLine("Cannot read options " + _  
                    ex.ToString())  
            Finally  
                reader.Close()  
            End Try  
        End If  
  
    Catch ex As Exception  
        Debug.WriteLine("Cannot read options " + ex.ToString())  
    End Try  
End Sub  
  
' Writes the button options to the isolated storage.  
Public Sub Write()
    Dim isoStore As System.IO.IsolatedStorage.IsolatedStorageFile = _  
        System.IO.IsolatedStorage.IsolatedStorageFile. _
        GetUserStoreForDomain()  
  
    Dim filename As String = "options.txt"  
    Try
        ' Checks if the file exists, and if it does, tries to delete it.  
        If (isoStore.GetFileNames(filename).GetLength(0) <> 0) Then  
            isoStore.DeleteFile(filename)  
        End If  
    Catch ex As Exception  
        Debug.WriteLine("Cannot delete file " + ex.ToString())  
    End Try  
  
    ' Creates the options.txt file and writes the button options to it.  
    Dim writer as System.IO.StreamWriter  
    Try
        Dim isos As New System.IO.IsolatedStorage.IsolatedStorageFileStream _
             (filename, IO.FileMode.CreateNew, isoStore)  
  
        writer = New System.IO.StreamWriter(isos)  
        Dim converter As System.ComponentModel.TypeConverter  
  
        converter = System.ComponentModel.TypeDescriptor.GetConverter _
           (GetType(Color))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.BackColor))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.ForeColor))  
  
        converter = System.ComponentModel TypeDescriptor.GetConverter _
           (GetType(Font))  
        writer.WriteLine(converter.ConvertToString( _  
            Me.MainButton.Font))  
  
    Catch ex as Exception  
        Debug.WriteLine("Cannot write options " + ex.ToString())  
  
    Finally  
        writer.Close()  
    End Try  
End Sub  
```  
  
```csharp  
// Reads the button options from the isolated storage. Uses default values
// for the button if the options file does not exist.  
public void Read()
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try  
    {  
        // Checks to see if the options.txt file exists.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)
        {  
            // Opens the file because it exists.  
            System.IO.IsolatedStorage.IsolatedStorageFileStream isos =
                new System.IO.IsolatedStorage.IsolatedStorageFileStream  
                    (filename, System.IO.FileMode.Open,isoStore);  
            System.IO.StreamReader reader = null;  
            try
            {  
                reader = new System.IO.StreamReader(isos);  
  
                // Reads the values stored.  
                TypeConverter converter ;  
                converter = TypeDescriptor.GetConverter(typeof(Color));  
  
                this.MainButton.BackColor =
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
                this.MainButton.ForeColor =
                 (Color)(converter.ConvertFromString(reader.ReadLine()));  
  
                converter = TypeDescriptor.GetConverter(typeof(Font));  
                this.MainButton.Font =
                  (Font)(converter.ConvertFromString(reader.ReadLine()));  
            }  
            catch (Exception ex)  
            {
                System.Diagnostics.Debug.WriteLine  
                     ("Cannot read options " + ex.ToString());  
            }  
            finally  
            {  
                reader.Close();  
            }  
        }  
    }
    catch (Exception ex)
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot read options " + ex.ToString());  
    }  
}  
  
// Writes the button options to the isolated storage.  
public void Write()
{  
    System.IO.IsolatedStorage.IsolatedStorageFile isoStore =
        System.IO.IsolatedStorage.IsolatedStorageFile.  
        GetUserStoreForDomain();  
  
    string filename = "options.txt";  
    try
    {  
        // Checks if the file exists and, if it does, tries to delete it.  
        if (isoStore.GetFileNames(filename).GetLength(0) != 0)
        {  
            isoStore.DeleteFile(filename);  
        }  
    }  
    catch (Exception ex)
    {  
        System.Diagnostics.Debug.WriteLine  
            ("Cannot delete file " + ex.ToString());  
    }  
  
    // Creates the options file and writes the button options to it.  
    System.IO.StreamWriter writer = null;  
    try
    {  
        System.IO.IsolatedStorage.IsolatedStorageFileStream isos = new
            System.IO.IsolatedStorage.IsolatedStorageFileStream(filename,
            System.IO.FileMode.CreateNew,isoStore);  
  
        writer = new System.IO.StreamWriter(isos);  
        TypeConverter converter ;  
  
        converter = TypeDescriptor.GetConverter(typeof(Color));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.BackColor));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.ForeColor));  
  
        converter = TypeDescriptor.GetConverter(typeof(Font));  
        writer.WriteLine(converter.ConvertToString(  
            this.MainButton.Font));  
  
    }  
    catch (Exception ex)  
    {
        System.Diagnostics.Debug.WriteLine  
           ("Cannot write options " + ex.ToString());  
    }  
    finally  
    {  
        writer.Close();  
    }  
}  
```  
  
## <a name="database-access"></a><span data-ttu-id="fbe82-151">データベース アクセス</span><span class="sxs-lookup"><span data-stu-id="fbe82-151">Database Access</span></span>  

 <span data-ttu-id="fbe82-152">データベースにアクセスするために必要なアクセス許可は、データベース プロバイダーに応じて異なります。ただし、適切なアクセス許可で実行されているアプリケーションのみがデータ接続を使用してデータベースにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-152">The permissions required to access a database vary based on the database provider; however, only applications that are running with the appropriate permissions can access a database through a data connection.</span></span> <span data-ttu-id="fbe82-153">データベースへのアクセスに必要な権限の詳細については、「 [コードアクセスセキュリティと ADO.NET](/dotnet/framework/data/adonet/code-access-security)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbe82-153">For more information about the permissions that are required to access a database, see [Code Access Security and ADO.NET](/dotnet/framework/data/adonet/code-access-security).</span></span>  
  
 <span data-ttu-id="fbe82-154">アプリケーションを部分信頼で実行するためにデータベースに直接アクセスできない場合は、データにアクセスする別の方法として Web サービスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-154">If you cannot directly access a database because you want your application to run in partial trust, you can use a Web service as an alternative means to access your data.</span></span> <span data-ttu-id="fbe82-155">Web サービスは、ネットワーク経由でプログラムでアクセスできるソフトウェアです。</span><span class="sxs-lookup"><span data-stu-id="fbe82-155">A Web service is a piece of software that can be programmatically accessed over a network.</span></span> <span data-ttu-id="fbe82-156">Web サービスを使用すると、アプリケーションはコード グループのゾーンにまたがるデータを共有できます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-156">With Web services, applications can share data across code group zones.</span></span> <span data-ttu-id="fbe82-157">既定では、ローカル イントラネット ゾーンとインターネット ゾーンのアプリケーションに、元のサイトへのアクセス権が付与され、同じサーバーにホストされる Web サービスを呼び出すことができます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-157">By default, applications in the local intranet and Internet zones are granted the right to access their sites of origin, which enables them to call a Web service hosted on the same server.</span></span> <span data-ttu-id="fbe82-158">詳細については、「 [ASP.NET AJAX の Web サービス](/previous-versions/aspnet/bb398785(v=vs.100)) 」または「 [Windows Communication Foundation](/dotnet/framework/wcf/index)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fbe82-158">For more information see [Web Services in ASP.NET AJAX](/previous-versions/aspnet/bb398785(v=vs.100)) or [Windows Communication Foundation](/dotnet/framework/wcf/index).</span></span>  
  
## <a name="registry-access"></a><span data-ttu-id="fbe82-159">レジストリへのアクセス</span><span class="sxs-lookup"><span data-stu-id="fbe82-159">Registry Access</span></span>  

 <span data-ttu-id="fbe82-160"><xref:System.Security.Permissions.RegistryPermission> クラスは、オペレーティング システムのレジストリへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-160">The <xref:System.Security.Permissions.RegistryPermission> class controls access to the operating system registry.</span></span> <span data-ttu-id="fbe82-161">既定では、ローカルで実行されているアプリケーションのみが、レジストリにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-161">By default, only applications that are running locally can access the registry.</span></span>  <span data-ttu-id="fbe82-162"><xref:System.Security.Permissions.RegistryPermission> はレジストリにアクセスしようとする権利のみをアプリケーションに付与します。オペレーティング システムは、引き続きレジストリのセキュリティを強制するため、アクセスが成功するかどうかは保証されません。</span><span class="sxs-lookup"><span data-stu-id="fbe82-162"><xref:System.Security.Permissions.RegistryPermission> only grants an application the right to try registry access; it does not guarantee access will succeed, because the operating system still enforces security on the registry.</span></span>  
  
 <span data-ttu-id="fbe82-163">部分信頼の下のレジストリにアクセスすることはできないため、データを格納するその他のメソッドを検索する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="fbe82-163">Because you cannot access the registry under partial trust, you may need to find other methods of storing your data.</span></span> <span data-ttu-id="fbe82-164">アプリケーション設定を保存する場合、レジストリの代わりに分離ストレージを使用します。</span><span class="sxs-lookup"><span data-stu-id="fbe82-164">When you store application settings, use isolated storage instead of the registry.</span></span> <span data-ttu-id="fbe82-165">また、分離ストレージを使用して、その他のアプリケーション固有のファイルを格納することもできます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-165">Isolated storage can also be used to store other application-specific files.</span></span> <span data-ttu-id="fbe82-166">既定では、アプリケーションの発生元のサイトへのアクセスがアプリケーションに付与されているため、サーバーまたは元のサイトに関するグローバルなアプリケーションの情報を格納することもできます。</span><span class="sxs-lookup"><span data-stu-id="fbe82-166">You can also store global application information about the server or site of origin, because by default an application is granted the right to access the site of its origin.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbe82-167">関連項目</span><span class="sxs-lookup"><span data-stu-id="fbe82-167">See also</span></span>

- [<span data-ttu-id="fbe82-168">Windows フォームでのより安全な印刷</span><span class="sxs-lookup"><span data-stu-id="fbe82-168">More Secure Printing in Windows Forms</span></span>](more-secure-printing-in-windows-forms.md)
- [<span data-ttu-id="fbe82-169">Windows フォームのセキュリティに関するその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="fbe82-169">Additional Security Considerations in Windows Forms</span></span>](additional-security-considerations-in-windows-forms.md)
- [<span data-ttu-id="fbe82-170">Windows フォームのセキュリティの概要</span><span class="sxs-lookup"><span data-stu-id="fbe82-170">Security in Windows Forms Overview</span></span>](security-in-windows-forms-overview.md)
- [<span data-ttu-id="fbe82-171">Windows フォームのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="fbe82-171">Windows Forms Security</span></span>](windows-forms-security.md)
- [<span data-ttu-id="fbe82-172">Mage.exe (マニフェストの生成および編集ツール)</span><span class="sxs-lookup"><span data-stu-id="fbe82-172">Mage.exe (Manifest Generation and Editing Tool)</span></span>](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)
- [<span data-ttu-id="fbe82-173">MageUI.exe (マニフェスト生成および編集ツールのグラフィカル クライアント)</span><span class="sxs-lookup"><span data-stu-id="fbe82-173">MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)</span></span>](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)
