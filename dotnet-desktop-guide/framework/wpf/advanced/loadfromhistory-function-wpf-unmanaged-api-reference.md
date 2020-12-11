---
title: LoadFromHistory 関数 - WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: fa5851658fd21e222a277ea78ad8dcd53009bf17
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984891"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="2f484-102">LoadFromHistory 関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="2f484-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="2f484-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしますが、独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="2f484-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="2f484-104">ウィンドウの管理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="2f484-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f484-105">構文</span><span class="sxs-lookup"><span data-stu-id="2f484-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f484-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="2f484-106">Parameters</span></span>  
 <span data-ttu-id="2f484-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="2f484-107">pHistoryStream</span></span>  
 <span data-ttu-id="2f484-108">履歴情報のストリームへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2f484-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="2f484-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="2f484-109">pBindCtx</span></span>  
 <span data-ttu-id="2f484-110">バインド コンテキストへのポインター。</span><span class="sxs-lookup"><span data-stu-id="2f484-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f484-111">必要条件</span><span class="sxs-lookup"><span data-stu-id="2f484-111">Requirements</span></span>  
 <span data-ttu-id="2f484-112">**プラットフォーム:** 「[.NET Framework システム要件](/dotnet/framework/get-started/system-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2f484-112">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="2f484-113">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="2f484-113">**DLL:**</span></span>  
  
 <span data-ttu-id="2f484-114">.NET Framework 3.0 および 3.5 の場合: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="2f484-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="2f484-115">.NET Framework 4 以降の場合: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="2f484-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="2f484-116">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2f484-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f484-117">関連項目</span><span class="sxs-lookup"><span data-stu-id="2f484-117">See also</span></span>

- [<span data-ttu-id="2f484-118">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="2f484-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
