---
title: DateTime XAML 構文
ms.date: 03/30/2017
helpviewer_keywords:
- DateTime XAML syntax [WPF], strings for
- DateTime XAML syntax [WPF], where used
- short date format [WPF], DateTime
- DateTime XAML syntax [WPF]
- DateTime XAML text [WPF]
- DateTime XAML syntax [WPF], format strings for
ms.assetid: 5901710a-609b-40c8-9d65-f0016cd9090b
ms.openlocfilehash: dc7291f09c44f8a0b616bf38c1c90eb92ec906e6
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982335"
---
# <a name="datetime-xaml-syntax"></a><span data-ttu-id="6e840-102">DateTime XAML 構文</span><span class="sxs-lookup"><span data-stu-id="6e840-102">DateTime XAML Syntax</span></span>
<span data-ttu-id="6e840-103"><xref:System.Windows.Controls.Calendar> や <xref:System.Windows.Controls.DatePicker> などの一部のコントロールには、<xref:System.DateTime> 型を使用するプロパティが存在します。</span><span class="sxs-lookup"><span data-stu-id="6e840-103">Some controls, such as <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker>, have properties that use the <xref:System.DateTime> type.</span></span> <span data-ttu-id="6e840-104">これらのコントロールに対する日付または時刻の初期値は、分離コードで実行時に指定するのが一般的です。ただし、日付または時刻の初期値を XAML で指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6e840-104">Although you typically specify an initial date or time for these controls in the code-behind at run time, you can specify an initial date or time in XAML.</span></span> <span data-ttu-id="6e840-105">WPF XAML パーサーでは、組み込みの XAML テキスト構文を使用して、<xref:System.DateTime> の値が解析されます。</span><span class="sxs-lookup"><span data-stu-id="6e840-105">The WPF XAML parser handles parsing of <xref:System.DateTime> values using a built-in XAML text syntax.</span></span> <span data-ttu-id="6e840-106">このトピックでは、<xref:System.DateTime> の XAML テキスト構文の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e840-106">This topic describes the specifics of the <xref:System.DateTime> XAML text syntax.</span></span>  

<a name="where_datetime_xaml_syntax_is_used"></a>
## <a name="when-to-use-datetime-xaml-syntax"></a><span data-ttu-id="6e840-107">DateTime XAML 構文が使用される状況</span><span class="sxs-lookup"><span data-stu-id="6e840-107">When To Use DateTime XAML Syntax</span></span>  
 <span data-ttu-id="6e840-108">日付は必ずしも XAML で設定する必要はありません。また、XAML で設定することが適切とは言えない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="6e840-108">Setting dates in XAML is not always necessary and may not even be desirable.</span></span> <span data-ttu-id="6e840-109">たとえば、<xref:System.DateTime.Now%2A?displayProperty=nameWithType> プロパティを使用すると、実行時に日付を初期化できます。また、カレンダーに対する日付の調整も、ユーザーの入力に基づいてコードビハインドですべて行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6e840-109">For example, you could use the <xref:System.DateTime.Now%2A?displayProperty=nameWithType> property to initialize a date at run time, or you could do all your date adjustments for a calendar in the code-behind based on user input.</span></span> <span data-ttu-id="6e840-110">ただし、コントロール テンプレートの <xref:System.Windows.Controls.Calendar> や <xref:System.Windows.Controls.DatePicker> に日付をハードコーディングすることが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="6e840-110">However, there are scenarios where you may want to hard-code dates into a <xref:System.Windows.Controls.Calendar> and <xref:System.Windows.Controls.DatePicker> in a control template.</span></span> <span data-ttu-id="6e840-111">このようなシナリオでは、<xref:System.DateTime> XAML 構文を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e840-111">The <xref:System.DateTime> XAML syntax must be used for these scenarios.</span></span>  
  
### <a name="datetime-xaml-syntax-is-a-native-behavior"></a><span data-ttu-id="6e840-112">DateTime XAML 構文はネイティブの動作</span><span class="sxs-lookup"><span data-stu-id="6e840-112">DateTime XAML Syntax is a Native Behavior</span></span>  
 <span data-ttu-id="6e840-113"><xref:System.DateTime> は、CLR の基底クラス ライブラリで定義されているクラスです。</span><span class="sxs-lookup"><span data-stu-id="6e840-113"><xref:System.DateTime> is a class that is defined in the base class libraries of the CLR.</span></span> <span data-ttu-id="6e840-114">基底クラス ライブラリと CLR の他のライブラリとの関連性のため、<xref:System.ComponentModel.TypeConverterAttribute> をクラスに適用し、型コンバーターを使用して XAML 文字列を処理し、ランタイム オブジェクト モデルの <xref:System.DateTime> に変換することはできません。</span><span class="sxs-lookup"><span data-stu-id="6e840-114">Because of how the base class libraries relate to the rest of the CLR, it is not possible to apply <xref:System.ComponentModel.TypeConverterAttribute> to the class and use a type converter to process strings from XAML and convert them to <xref:System.DateTime> in the run time object model.</span></span> <span data-ttu-id="6e840-115">変換動作を提供する `DateTimeConverter` クラスは存在しません。このトピックで説明する変換動作は、WPF XAML パーサーのネイティブな動作です。</span><span class="sxs-lookup"><span data-stu-id="6e840-115">There is no `DateTimeConverter` class that provides the conversion behavior; the conversion behavior described in this topic is native to the WPF XAML parser.</span></span>  
  
<a name="format_strings_for_datetime_xaml_syntax"></a>
## <a name="format-strings-for-datetime-xaml-syntax"></a><span data-ttu-id="6e840-116">DateTime XAML 構文の書式指定文字列</span><span class="sxs-lookup"><span data-stu-id="6e840-116">Format Strings for DateTime XAML Syntax</span></span>  
 <span data-ttu-id="6e840-117"><xref:System.DateTime> の形式は、書式指定文字列で指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e840-117">You can specify the format of a <xref:System.DateTime> with a format string.</span></span> <span data-ttu-id="6e840-118">書式指定文字列は、値を作成するときに使用できるテキスト構文を形式化します。</span><span class="sxs-lookup"><span data-stu-id="6e840-118">Format strings formalize the text syntax that can be used to create a value.</span></span> <span data-ttu-id="6e840-119">既存の WPF コントロールの <xref:System.DateTime> 値では、一般に、<xref:System.DateTime> の日付要素のみが使用され、時刻要素は使用されません。</span><span class="sxs-lookup"><span data-stu-id="6e840-119"><xref:System.DateTime> values for the existing WPF controls generally only use the date components of <xref:System.DateTime> and not the time components.</span></span>  
  
 <span data-ttu-id="6e840-120"><xref:System.DateTime> を XAML で指定する場合、どの書式指定文字列でも代用できます。</span><span class="sxs-lookup"><span data-stu-id="6e840-120">When specifying a <xref:System.DateTime> in XAML, you can use any of the format strings interchangeably.</span></span>  
  
 <span data-ttu-id="6e840-121">また、このトピックで特に示されていない形式および書式指定文字列も使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e840-121">You can also use formats and format strings that are not specifically shown in this topic.</span></span> <span data-ttu-id="6e840-122">技術的には、<xref:System.DateTime> 値を XAML で指定すると、WPF XAML パーサーによって解析されるときに、<xref:System.DateTime.Parse%2A?displayProperty=nameWithType> が内部的に呼び出されます。したがって、XAML の入力では、<xref:System.DateTime.Parse%2A?displayProperty=nameWithType> によって受け付けられる任意の文字列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6e840-122">Technically, the XAML for any <xref:System.DateTime> value that is specified and then parsed by the WPF XAML parser uses an internal  call to <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>, therefore you could use any string accepted by <xref:System.DateTime.Parse%2A?displayProperty=nameWithType> for your XAML input.</span></span> <span data-ttu-id="6e840-123">詳細については、「<xref:System.DateTime.Parse%2A?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e840-123">For more information, see <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6e840-124">DateTime XAML 構文でネイティブ変換を行う場合は常に、<xref:System.Globalization.CultureInfo> として `en-us` を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e840-124">The DateTime XAML syntax always uses `en-us` as the <xref:System.Globalization.CultureInfo> for its native conversion.</span></span> <span data-ttu-id="6e840-125">これは、XAML 内の <xref:System.Windows.FrameworkElement.Language%2A> 値または `xml:lang` 値による影響を受けません。XAML の属性レベルでの型変換は、コンテキストなしで動作するためです。</span><span class="sxs-lookup"><span data-stu-id="6e840-125">This is not influenced by <xref:System.Windows.FrameworkElement.Language%2A> value or `xml:lang` value in the XAML, because XAML attribute-level type conversion acts without that context.</span></span> <span data-ttu-id="6e840-126">日や月を表示する順序などにはカルチャによる違いがあるため、ここで示した書式指定文字列は補完しないでください。</span><span class="sxs-lookup"><span data-stu-id="6e840-126">Do not attempt to interpolate the format strings shown here due to cultural variations, such as the order in which day and month appear.</span></span> <span data-ttu-id="6e840-127">ここで示した書式指定文字列は、その他のカルチャ設定に関係なく、XAML を解析する場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="6e840-127">The format strings shown here are the exact format strings used when parsing the XAML regardless of other culture settings.</span></span>  
  
 <span data-ttu-id="6e840-128">以降のセクションでは、<xref:System.DateTime> の一般的な書式指定文字列について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e840-128">The following sections describe some of the common <xref:System.DateTime> format strings.</span></span>  
  
### <a name="short-date-pattern-d"></a><span data-ttu-id="6e840-129">短い形式の日付パターン ("d")</span><span class="sxs-lookup"><span data-stu-id="6e840-129">Short Date Pattern ("d")</span></span>  
 <span data-ttu-id="6e840-130">XAML における <xref:System.DateTime> の短い日付形式は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6e840-130">The following shows the short date format for a <xref:System.DateTime> in XAML:</span></span>  
  
 `M/d/YYYY`  
  
 <span data-ttu-id="6e840-131">これは、WPF コントロールでの一般的な使用法で、必要なすべての情報を指定するための最も簡単な形式です。タイム ゾーン オフセットと時刻要素を誤って指定した場合でも影響を受けないため、他の形式ではなく、この形式の使用をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e840-131">This is the simplest form that specifies all necessary information for typical usages by WPF controls, and cannot be influenced by accidental time zone offsets versus a time component, and is therefore recommended over the other formats.</span></span>  
  
 <span data-ttu-id="6e840-132">たとえば、2010 年 6 月 1 日を指定するには、次の文字列を使用します。</span><span class="sxs-lookup"><span data-stu-id="6e840-132">For example, to specify the date of June 1, 2010, use the following string:</span></span>  
  
 `3/1/2010`  
  
 <span data-ttu-id="6e840-133">詳細については、「<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e840-133">For more information, see <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>.</span></span>  
  
### <a name="sortable-datetime-pattern-s"></a><span data-ttu-id="6e840-134">並べ替えできる DateTime のパターン ("s")</span><span class="sxs-lookup"><span data-stu-id="6e840-134">Sortable DateTime Pattern ("s")</span></span>  
 <span data-ttu-id="6e840-135">XAML における並べ替え可能な <xref:System.DateTime> のパターンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6e840-135">The following shows the sortable <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `yyyy'-'MM'-'dd'T'HH':'mm':'ss`  
  
 <span data-ttu-id="6e840-136">たとえば、2010 年 6 月 1 日を指定するには、次の文字列を使用します (時刻要素はすべて 0 として入力されます)。</span><span class="sxs-lookup"><span data-stu-id="6e840-136">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `2010-06-01T000:00:00`  
  
### <a name="rfc1123-pattern-r"></a><span data-ttu-id="6e840-137">RFC1123 パターン ("r")</span><span class="sxs-lookup"><span data-stu-id="6e840-137">RFC1123 Pattern ("r")</span></span>  
 <span data-ttu-id="6e840-138">RFC1123 パターンの利点は、カルチャに依存しないために、RFC1123 パターンが使用されている他の日付ジェネレーターから入力された文字列を使用できることです。</span><span class="sxs-lookup"><span data-stu-id="6e840-138">The RFC1123 pattern is useful because it could be a string input from other date generators that also use the RFC1123 pattern for culture invariant reasons.</span></span> <span data-ttu-id="6e840-139">XAML における RFC1123 の <xref:System.DateTime> パターンを次に示します。</span><span class="sxs-lookup"><span data-stu-id="6e840-139">The following shows the RFC1123 <xref:System.DateTime> pattern in XAML:</span></span>  
  
 `ddd, dd MMM yyyy HH':'mm':'ss 'UTC'`  
  
 <span data-ttu-id="6e840-140">たとえば、2010 年 6 月 1 日を指定するには、次の文字列を使用します (時刻要素はすべて 0 として入力されます)。</span><span class="sxs-lookup"><span data-stu-id="6e840-140">For example, to specify the date of June 1, 2010, use the following string (time components are all entered as 0):</span></span>  
  
 `Mon, 01 Jun 2010 00:00:00 UTC`  
  
### <a name="other-formats-and-patterns"></a><span data-ttu-id="6e840-141">その他の形式とパターン</span><span class="sxs-lookup"><span data-stu-id="6e840-141">Other Formats and Patterns</span></span>  
 <span data-ttu-id="6e840-142">既に説明したように、XAML における <xref:System.DateTime> では、<xref:System.DateTime.Parse%2A?displayProperty=nameWithType> に対する入力として受け付けられる任意の文字列を指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e840-142">As stated previously, a <xref:System.DateTime> in XAML can be specified as any string that is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6e840-143">これには、その他の形式化された形式 (例: <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>) および特定の <xref:System.Globalization.DateTimeFormatInfo> フォームとして形式化されていない形式が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6e840-143">This includes other formalized formats (for example <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>), and formats that are not formalized as a particular <xref:System.Globalization.DateTimeFormatInfo> form.</span></span> <span data-ttu-id="6e840-144">たとえば、`YYYY/mm/dd` という形式は、<xref:System.DateTime.Parse%2A?displayProperty=nameWithType> に対する入力として受け付けられます。</span><span class="sxs-lookup"><span data-stu-id="6e840-144">For example, the form `YYYY/mm/dd` is acceptable as input for <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6e840-145">このトピックでは、使用可能な形式の一部を説明します。標準的な使用手順としては、短い形式の日付パターンをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e840-145">This topic does not attempt to describe all possible formats that work, and instead recommends the short date pattern as a standard practice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e840-146">関連項目</span><span class="sxs-lookup"><span data-stu-id="6e840-146">See also</span></span>

- [<span data-ttu-id="6e840-147">XAML の概要 (WPF)</span><span class="sxs-lookup"><span data-stu-id="6e840-147">XAML Overview (WPF)</span></span>](/dotnet/desktop-wpf/fundamentals/xaml)
