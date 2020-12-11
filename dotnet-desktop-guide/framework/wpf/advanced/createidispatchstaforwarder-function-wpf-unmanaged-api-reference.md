---
title: CreateIDispatchSTAForwarder 関数 - WPF のアンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: f7f60c53125eaaafe88b8777f3b560d5d1e083b2
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96982340"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="85cb1-102">CreateIDispatchSTAForwarder 関数 (WPF のアンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="85cb1-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="85cb1-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしますが、独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="85cb1-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="85cb1-104">スレッドおよびウィンドウの管理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="85cb1-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85cb1-105">構文</span><span class="sxs-lookup"><span data-stu-id="85cb1-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="85cb1-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="85cb1-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="85cb1-107">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="85cb1-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="85cb1-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="85cb1-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="85cb1-109">`IDispatch` インターフェイスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="85cb1-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="85cb1-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="85cb1-110">ppForwarder</span></span>  
 <span data-ttu-id="85cb1-111">`IDispatch` インターフェイスのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="85cb1-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85cb1-112">必要条件</span><span class="sxs-lookup"><span data-stu-id="85cb1-112">Requirements</span></span>  
 <span data-ttu-id="85cb1-113">**プラットフォーム:** 「[.NET Framework システム要件](/dotnet/framework/get-started/system-requirements)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="85cb1-113">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>  
  
 <span data-ttu-id="85cb1-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="85cb1-114">**DLL:**</span></span>  
  
 <span data-ttu-id="85cb1-115">.NET Framework 3.0 および 3.5 の場合:PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="85cb1-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="85cb1-116">.NET Framework 4 以降の場合:PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="85cb1-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="85cb1-117">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85cb1-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85cb1-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="85cb1-118">See also</span></span>

- [<span data-ttu-id="85cb1-119">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="85cb1-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
