---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983127"
---
# <a name="getcustomui"></a><span data-ttu-id="2893c-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="2893c-102">GetCustomUI</span></span>
<span data-ttu-id="2893c-103">実装されている場合、ホストから進行状況とエラーのカスタム メッセージを取得するために、PresentationHost.exe によって呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2893c-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2893c-104">構文</span><span class="sxs-lookup"><span data-stu-id="2893c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="2893c-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2893c-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="2893c-106">[out] ホストから提供された進行状況ユーザー インターフェイスが格納されているアセンブリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2893c-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="2893c-107">[out] ホストから提供された進行状況ユーザー インターフェイスであるクラスの名前。可能であれば、<xref:System.Windows.Controls.Page> を含む XAML ファイルが最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="2893c-107">[out] The name of the class that is the host-supplied progress user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="2893c-108">このクラスは、`pwzProgressAssemblyName` によって指定されているアセンブリに存在します。</span><span class="sxs-lookup"><span data-stu-id="2893c-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="2893c-109">[out] ホストから提供されたエラー ユーザー インターフェイスが格納されているアセンブリへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2893c-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="2893c-110">[out] ホストから提供されたエラー ユーザー インターフェイスであるクラスの名前。可能であれば、<xref:System.Windows.Controls.Page> を含む XAML ファイルが最上位の要素です。</span><span class="sxs-lookup"><span data-stu-id="2893c-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="2893c-111">このクラスは、`pwzErrorAssemblyName` によって指定されているアセンブリに存在します。</span><span class="sxs-lookup"><span data-stu-id="2893c-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2893c-112">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="2893c-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="2893c-113">HRESULT:無視されます。</span><span class="sxs-lookup"><span data-stu-id="2893c-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2893c-114">コメント</span><span class="sxs-lookup"><span data-stu-id="2893c-114">Remarks</span></span>  
 <span data-ttu-id="2893c-115">ホスト アプリケーションには、PresentationHost.exe の既定のユーザー インターフェイスが準拠していない可能性がある特定のテーマが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2893c-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="2893c-116">その場合は、ホスト アプリケーションで [GetCustomUI](getcustomui.md) を実装して、進行状況とエラーのユーザー インターフェイスを PresentationHost.exe に返すことができます。</span><span class="sxs-lookup"><span data-stu-id="2893c-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="2893c-117">[GetCustomUI](getcustomui.md) は、既定のユーザーインターフェイスを使用する前に、常にを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="2893c-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="2893c-118">この関数は、PresentationHost の初期化の間に 1 回呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="2893c-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2893c-119">関連項目</span><span class="sxs-lookup"><span data-stu-id="2893c-119">See also</span></span>

- [<span data-ttu-id="2893c-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="2893c-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
