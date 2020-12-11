---
title: ProcessUnhandledException 関数 - WPF アンマネージド API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 7de12e0d21a6add88ce602ea00b7f7b3aaf0c197
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96983995"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="acc13-102">ProcessUnhandledException 関数 (WPF アンマネージド API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="acc13-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="acc13-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしますが、独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="acc13-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="acc13-104">例外処理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="acc13-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acc13-105">構文</span><span class="sxs-lookup"><span data-stu-id="acc13-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="acc13-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="acc13-106">Parameters</span></span>  
 <span data-ttu-id="acc13-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="acc13-107">errorMsg</span></span>  
 <span data-ttu-id="acc13-108">エラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="acc13-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="acc13-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="acc13-109">Requirements</span></span>  
 <span data-ttu-id="acc13-110">**プラットフォーム:** 「[.NET Framework システム要件](/dotnet/framework/get-started/system-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="acc13-110">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="acc13-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="acc13-111">**DLL:**</span></span>  
  
 <span data-ttu-id="acc13-112">.NET Framework 3.0 および 3.5 の場合: PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="acc13-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="acc13-113">.NET Framework 4 以降の場合: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="acc13-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="acc13-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="acc13-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acc13-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="acc13-115">See also</span></span>

- [<span data-ttu-id="acc13-116">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="acc13-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
