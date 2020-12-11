---
title: '方法: イメージ メタデータを読み取る'
desription: Learn how to read the Windows Forms PropertyItems property of an Image object to retrieve all the metadata from a file.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- metadata [Windows Forms], property item
- metadata [Windows Forms], reading image
ms.assetid: 72ec0b31-0be7-444a-9575-1dbcb864e0be
ms.openlocfilehash: 814cb17feba1e1e3a42b2bc403b0b4c828caf90e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96981291"
---
# <a name="how-to-read-image-metadata"></a><span data-ttu-id="c44a7-102">方法: イメージ メタデータを読み取る</span><span class="sxs-lookup"><span data-stu-id="c44a7-102">How to: Read Image Metadata</span></span>

<span data-ttu-id="c44a7-103">一部のイメージファイルには、イメージの機能を確認するために読み取ることができるメタデータが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c44a7-103">Some image files contain metadata that you can read to determine features of the image.</span></span> <span data-ttu-id="c44a7-104">たとえば、デジタル写真には、イメージのキャプチャに使用されるカメラのメーカーとモデルを決定するために読み取ることができるメタデータが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="c44a7-104">For example, a digital photograph might contain metadata that you can read to determine the make and model of the camera used to capture the image.</span></span> <span data-ttu-id="c44a7-105">GDI + を使用すると、既存のメタデータを読み取ることができます。また、イメージファイルに新しいメタデータを書き込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="c44a7-105">With GDI+, you can read existing metadata, and you can also write new metadata to image files.</span></span>

<span data-ttu-id="c44a7-106">GDI + は、オブジェクトに個々のメタデータを格納 <xref:System.Drawing.Imaging.PropertyItem> します。</span><span class="sxs-lookup"><span data-stu-id="c44a7-106">GDI+ stores an individual piece of metadata in a <xref:System.Drawing.Imaging.PropertyItem> object.</span></span> <span data-ttu-id="c44a7-107"><xref:System.Drawing.Image.PropertyItems%2A>オブジェクトのプロパティを読み取って <xref:System.Drawing.Image> 、ファイルからすべてのメタデータを取得できます。</span><span class="sxs-lookup"><span data-stu-id="c44a7-107">You can read the <xref:System.Drawing.Image.PropertyItems%2A> property of an <xref:System.Drawing.Image> object to retrieve all the metadata from a file.</span></span> <span data-ttu-id="c44a7-108">プロパティは、 <xref:System.Drawing.Image.PropertyItems%2A> オブジェクトの配列を返し <xref:System.Drawing.Imaging.PropertyItem> ます。</span><span class="sxs-lookup"><span data-stu-id="c44a7-108">The <xref:System.Drawing.Image.PropertyItems%2A> property returns an array of <xref:System.Drawing.Imaging.PropertyItem> objects.</span></span>

<span data-ttu-id="c44a7-109"><xref:System.Drawing.Imaging.PropertyItem>オブジェクトには、、、 `Id` `Value` `Len` 、およびの4つのプロパティがあります `Type` 。</span><span class="sxs-lookup"><span data-stu-id="c44a7-109">A <xref:System.Drawing.Imaging.PropertyItem> object has the following four properties: `Id`, `Value`, `Len`, and `Type`.</span></span>

## <a name="id"></a><span data-ttu-id="c44a7-110">Id</span><span class="sxs-lookup"><span data-stu-id="c44a7-110">Id</span></span>

<span data-ttu-id="c44a7-111">メタデータ項目を識別するタグ。</span><span class="sxs-lookup"><span data-stu-id="c44a7-111">A tag that identifies the metadata item.</span></span> <span data-ttu-id="c44a7-112">次の表に、に割り当てることができる値をいくつか <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 示します。</span><span class="sxs-lookup"><span data-stu-id="c44a7-112">Some values that can be assigned to <xref:System.Drawing.Imaging.PropertyItem.Id%2A> are shown in the following table:</span></span>

|<span data-ttu-id="c44a7-113">16 進数値</span><span class="sxs-lookup"><span data-stu-id="c44a7-113">Hexadecimal value</span></span>|<span data-ttu-id="c44a7-114">説明</span><span class="sxs-lookup"><span data-stu-id="c44a7-114">Description</span></span>|
|-----------------------|-----------------|
|<span data-ttu-id="c44a7-115">0x0320</span><span class="sxs-lookup"><span data-stu-id="c44a7-115">0x0320</span></span><br /><br /> <span data-ttu-id="c44a7-116">0x010F</span><span class="sxs-lookup"><span data-stu-id="c44a7-116">0x010F</span></span><br /><br /> <span data-ttu-id="c44a7-117">0x0110</span><span class="sxs-lookup"><span data-stu-id="c44a7-117">0x0110</span></span><br /><br /> <span data-ttu-id="c44a7-118">0x9003</span><span class="sxs-lookup"><span data-stu-id="c44a7-118">0x9003</span></span><br /><br /> <span data-ttu-id="c44a7-119">0x829A</span><span class="sxs-lookup"><span data-stu-id="c44a7-119">0x829A</span></span><br /><br /> <span data-ttu-id="c44a7-120">0x5090</span><span class="sxs-lookup"><span data-stu-id="c44a7-120">0x5090</span></span><br /><br /> <span data-ttu-id="c44a7-121">0x5091</span><span class="sxs-lookup"><span data-stu-id="c44a7-121">0x5091</span></span>|<span data-ttu-id="c44a7-122">イメージのタイトル</span><span class="sxs-lookup"><span data-stu-id="c44a7-122">Image title</span></span><br /><br /> <span data-ttu-id="c44a7-123">装置の製造元</span><span class="sxs-lookup"><span data-stu-id="c44a7-123">Equipment manufacturer</span></span><br /><br /> <span data-ttu-id="c44a7-124">装置モデル</span><span class="sxs-lookup"><span data-stu-id="c44a7-124">Equipment model</span></span><br /><br /> <span data-ttu-id="c44a7-125">ExifDTOriginal</span><span class="sxs-lookup"><span data-stu-id="c44a7-125">ExifDTOriginal</span></span><br /><br /> <span data-ttu-id="c44a7-126">Exif 公開時間</span><span class="sxs-lookup"><span data-stu-id="c44a7-126">Exif exposure time</span></span><br /><br /> <span data-ttu-id="c44a7-127">輝度テーブル</span><span class="sxs-lookup"><span data-stu-id="c44a7-127">Luminance table</span></span><br /><br /> <span data-ttu-id="c44a7-128">クロミナンステーブル</span><span class="sxs-lookup"><span data-stu-id="c44a7-128">Chrominance table</span></span>|

## <a name="value"></a><span data-ttu-id="c44a7-129">値</span><span class="sxs-lookup"><span data-stu-id="c44a7-129">Value</span></span>

<span data-ttu-id="c44a7-130">値の配列です。</span><span class="sxs-lookup"><span data-stu-id="c44a7-130">An array of values.</span></span> <span data-ttu-id="c44a7-131">値の形式は、プロパティによって決まり <xref:System.Drawing.Imaging.PropertyItem.Type%2A> ます。</span><span class="sxs-lookup"><span data-stu-id="c44a7-131">The format of the values is determined by the <xref:System.Drawing.Imaging.PropertyItem.Type%2A> property.</span></span>

## <a name="len"></a><span data-ttu-id="c44a7-132">Len</span><span class="sxs-lookup"><span data-stu-id="c44a7-132">Len</span></span>

<span data-ttu-id="c44a7-133">プロパティが指す値の配列の長さ (バイト単位) <xref:System.Drawing.Imaging.PropertyItem.Value%2A> 。</span><span class="sxs-lookup"><span data-stu-id="c44a7-133">The length (in bytes) of the array of values pointed to by the <xref:System.Drawing.Imaging.PropertyItem.Value%2A> property.</span></span>

## <a name="type"></a><span data-ttu-id="c44a7-134">Type</span><span class="sxs-lookup"><span data-stu-id="c44a7-134">Type</span></span>

<span data-ttu-id="c44a7-135">プロパティが指す配列内の値のデータ型 `Value` 。</span><span class="sxs-lookup"><span data-stu-id="c44a7-135">The data type of the values in the array pointed to by the `Value` property.</span></span> <span data-ttu-id="c44a7-136">次の表に、プロパティ値によって示される形式を `Type` 示します。</span><span class="sxs-lookup"><span data-stu-id="c44a7-136">The formats indicated by the `Type` property values are shown in the following table:</span></span>

|<span data-ttu-id="c44a7-137">数値</span><span class="sxs-lookup"><span data-stu-id="c44a7-137">Numeric value</span></span>|<span data-ttu-id="c44a7-138">説明</span><span class="sxs-lookup"><span data-stu-id="c44a7-138">Description</span></span>|
|-------------------|-----------------|
|<span data-ttu-id="c44a7-139">1</span><span class="sxs-lookup"><span data-stu-id="c44a7-139">1</span></span>|<span data-ttu-id="c44a7-140">`Byte`。</span><span class="sxs-lookup"><span data-stu-id="c44a7-140">A `Byte`</span></span>|
|<span data-ttu-id="c44a7-141">2</span><span class="sxs-lookup"><span data-stu-id="c44a7-141">2</span></span>|<span data-ttu-id="c44a7-142">`Byte`ASCII としてエンコードされたオブジェクトの配列</span><span class="sxs-lookup"><span data-stu-id="c44a7-142">An array of `Byte` objects encoded as ASCII</span></span>|
|<span data-ttu-id="c44a7-143">3</span><span class="sxs-lookup"><span data-stu-id="c44a7-143">3</span></span>|<span data-ttu-id="c44a7-144">16ビット整数</span><span class="sxs-lookup"><span data-stu-id="c44a7-144">A 16-bit integer</span></span>|
|<span data-ttu-id="c44a7-145">4</span><span class="sxs-lookup"><span data-stu-id="c44a7-145">4</span></span>|<span data-ttu-id="c44a7-146">32ビット整数</span><span class="sxs-lookup"><span data-stu-id="c44a7-146">A 32-bit integer</span></span>|
|<span data-ttu-id="c44a7-147">5</span><span class="sxs-lookup"><span data-stu-id="c44a7-147">5</span></span>|<span data-ttu-id="c44a7-148">有理数を表す2つのオブジェクトの配列 `Byte`</span><span class="sxs-lookup"><span data-stu-id="c44a7-148">An array of two `Byte` objects that represent a rational number</span></span>|
|<span data-ttu-id="c44a7-149">6</span><span class="sxs-lookup"><span data-stu-id="c44a7-149">6</span></span>|<span data-ttu-id="c44a7-150">使用されていない</span><span class="sxs-lookup"><span data-stu-id="c44a7-150">Not used</span></span>|
|<span data-ttu-id="c44a7-151">7</span><span class="sxs-lookup"><span data-stu-id="c44a7-151">7</span></span>|<span data-ttu-id="c44a7-152">未定義。</span><span class="sxs-lookup"><span data-stu-id="c44a7-152">Undefined</span></span>|
|<span data-ttu-id="c44a7-153">8</span><span class="sxs-lookup"><span data-stu-id="c44a7-153">8</span></span>|<span data-ttu-id="c44a7-154">使用されていない</span><span class="sxs-lookup"><span data-stu-id="c44a7-154">Not used</span></span>|
|<span data-ttu-id="c44a7-155">9</span><span class="sxs-lookup"><span data-stu-id="c44a7-155">9</span></span>|`SLong`|
|<span data-ttu-id="c44a7-156">10</span><span class="sxs-lookup"><span data-stu-id="c44a7-156">10</span></span>|`SRational`|

## <a name="example"></a><span data-ttu-id="c44a7-157">例</span><span class="sxs-lookup"><span data-stu-id="c44a7-157">Example</span></span>
  
<span data-ttu-id="c44a7-158">次のコード例では、ファイル内の7つのメタデータを読み取り、表示し `FakePhoto.jpg` ます。</span><span class="sxs-lookup"><span data-stu-id="c44a7-158">The following code example reads and displays the seven pieces of metadata in the file `FakePhoto.jpg`.</span></span> <span data-ttu-id="c44a7-159">リスト内の2番目の (インデックス 1) プロパティ項目には、 <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (装置の製造元) と <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII エンコードされたバイト配列) があります。</span><span class="sxs-lookup"><span data-stu-id="c44a7-159">The second (index 1) property item in the list has <xref:System.Drawing.Imaging.PropertyItem.Id%2A> 0x010F (equipment manufacturer) and <xref:System.Drawing.Imaging.PropertyItem.Type%2A> 2 (ASCII-encoded byte array).</span></span> <span data-ttu-id="c44a7-160">このコード例では、そのプロパティ項目の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="c44a7-160">The code example displays the value of that property item.</span></span>

[!code-csharp[System.Drawing.WorkingWithImages#51](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/CS/Class1.cs#51)]
[!code-vb[System.Drawing.WorkingWithImages#51](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.WorkingWithImages/VB/Class1.vb#51)]

<span data-ttu-id="c44a7-161">このコードでは、次のような出力が生成されます。</span><span class="sxs-lookup"><span data-stu-id="c44a7-161">The code produces output similar to the following:</span></span>

```output
 Property Item 0
  
 id: 0x320
  
 type: 2

 length: 16 bytes
  
 Property Item 1
  
 id: 0x10f
  
 type: 2
  
 length: 17 bytes
  
 Property Item 2
  
 id: 0x110
  
 type: 2
  
 length: 7 bytes
  
 Property Item 3
  
 id: 0x9003
  
 type: 2
  
 length: 20 bytes
  
 Property Item 4
  
 id: 0x829a
  
 type: 5
  
 length: 8 bytes
  
 Property Item 5
  
 id: 0x5090
  
 type: 3
  
 length: 128 bytes
  
 Property Item 6
  
 id: 0x5091
  
 type: 3
  
 length: 128 bytes
  
 The equipment make is Northwind Camera.
 ```

## <a name="compiling-the-code"></a><span data-ttu-id="c44a7-162">コードのコンパイル</span><span class="sxs-lookup"><span data-stu-id="c44a7-162">Compiling the Code</span></span>

<span data-ttu-id="c44a7-163">前の例は、Windows フォームで使用するように設計されてい <xref:System.Windows.Forms.PaintEventArgs> `e` ます。これは、イベントハンドラーのパラメーターであるを必要とし <xref:System.Windows.Forms.Control.Paint> ます。</span><span class="sxs-lookup"><span data-stu-id="c44a7-163">The preceding example is designed for use with Windows Forms, and it requires <xref:System.Windows.Forms.PaintEventArgs> `e`, which is a parameter of the <xref:System.Windows.Forms.Control.Paint> event handler.</span></span> <span data-ttu-id="c44a7-164">フォームのイベントを処理 <xref:System.Windows.Forms.Control.Paint> し、このコードを描画イベントハンドラーに貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="c44a7-164">Handle the form's <xref:System.Windows.Forms.Control.Paint> event and paste this code into the paint event handler.</span></span> <span data-ttu-id="c44a7-165">を `FakePhoto.jpg` システム上で有効なイメージ名とパスに置き換えて、名前空間をインポートする必要があり `System.Drawing.Imaging` ます。</span><span class="sxs-lookup"><span data-stu-id="c44a7-165">You must replace `FakePhoto.jpg` with an image name and path valid on your system and import the `System.Drawing.Imaging` namespace.</span></span>

## <a name="see-also"></a><span data-ttu-id="c44a7-166">関連項目</span><span class="sxs-lookup"><span data-stu-id="c44a7-166">See also</span></span>

- [<span data-ttu-id="c44a7-167">イメージ、ビットマップ、およびメタファイル</span><span class="sxs-lookup"><span data-stu-id="c44a7-167">Images, Bitmaps, and Metafiles</span></span>](images-bitmaps-and-metafiles.md)
- [<span data-ttu-id="c44a7-168">イメージ、ビットマップ、アイコン、およびメタファイルの操作</span><span class="sxs-lookup"><span data-stu-id="c44a7-168">Working with Images, Bitmaps, Icons, and Metafiles</span></span>](working-with-images-bitmaps-icons-and-metafiles.md)
