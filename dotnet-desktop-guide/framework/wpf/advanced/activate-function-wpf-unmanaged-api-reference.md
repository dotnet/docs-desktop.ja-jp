---
title: Activate 関数 - WPF アンマネージ API リファレンス
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- Activate
api_location:
- PresentationHost_v0400.dll
ms.assetid: 1400329c-b598-465f-80f2-e3dabf044811
ms.openlocfilehash: c97069613a96009d0b9bb84e55c37b29c2d3ea5b
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974682"
---
# <a name="activate-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="b2c20-102">Activate 関数 (WPF アンマネージ API リファレンス)</span><span class="sxs-lookup"><span data-stu-id="b2c20-102">Activate Function (WPF Unmanaged API Reference)</span></span>

<span data-ttu-id="b2c20-103">この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしますが、独自に作成したコードから直接使用するためのものではありません。</span><span class="sxs-lookup"><span data-stu-id="b2c20-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>

<span data-ttu-id="b2c20-104">ウィンドウの管理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="b2c20-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>

## <a name="syntax"></a><span data-ttu-id="b2c20-105">構文</span><span class="sxs-lookup"><span data-stu-id="b2c20-105">Syntax</span></span>

```cpp
void Activate(
    const ActivateParameters* pParameters,
    __deref_out_ecount(1) LPUNKNOWN* ppInner,
    );
```

## <a name="parameters"></a><span data-ttu-id="b2c20-106">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b2c20-106">Parameters</span></span>

`pParameters`\
<span data-ttu-id="b2c20-107">ウィンドウのアクティベーション パラメーターへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b2c20-107">A pointer to the window's activation parameters.</span></span>

`ppInner`\
<span data-ttu-id="b2c20-108"><xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> オブジェクトへのポインターを含む単一要素バッファーのアドレスへのポインター。</span><span class="sxs-lookup"><span data-stu-id="b2c20-108">A pointer to the address of a single-element buffer that contains a pointer to an <xref:Microsoft.VisualStudio.OLE.Interop.IOleDocument> object.</span></span>

## <a name="requirements"></a><span data-ttu-id="b2c20-109">必要条件</span><span class="sxs-lookup"><span data-stu-id="b2c20-109">Requirements</span></span>

<span data-ttu-id="b2c20-110">**プラットフォーム:** 「[.NET Framework システム要件](/dotnet/framework/get-started/system-requirements)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b2c20-110">**Platforms:** See [.NET Framework System Requirements](/dotnet/framework/get-started/system-requirements).</span></span>

<span data-ttu-id="b2c20-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="b2c20-111">**DLL:**</span></span>

<span data-ttu-id="b2c20-112">.NET Framework 3.0 および 3.5 の場合:PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="b2c20-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>

<span data-ttu-id="b2c20-113">.NET Framework 4 以降の場合:PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="b2c20-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>

<span data-ttu-id="b2c20-114">**.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2c20-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b2c20-115">関連項目</span><span class="sxs-lookup"><span data-stu-id="b2c20-115">See also</span></span>

- [<span data-ttu-id="b2c20-116">WPF のアンマネージ API リファレンス</span><span class="sxs-lookup"><span data-stu-id="b2c20-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
