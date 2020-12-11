---
title: IEnumRAWINPUTDEVIC:Next
ms.date: 03/30/2017
helpviewer_keywords:
- Next method [WPF]
ms.assetid: 3698b44d-510e-4d18-b32b-85f17188ee26
ms.openlocfilehash: c7450a9ababa9cf3cb02d572f5ed84f0791d74e4
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96974321"
---
# <a name="ienumrawinputdevicnext"></a><span data-ttu-id="78fa8-102">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="78fa8-102">IEnumRAWINPUTDEVIC:Next</span></span>
<span data-ttu-id="78fa8-103">列挙子の一覧に含まれる次の `celt` 個の [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 構造体を列挙し、それを `pceltFetched` で列挙された要素の実際の数とともに `rgelt` で返します。</span><span class="sxs-lookup"><span data-stu-id="78fa8-103">Enumerates the next `celt` [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78fa8-104">構文</span><span class="sxs-lookup"><span data-stu-id="78fa8-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
      [in] ULONG celt,  
      [out, size_is(celt), length_is(*pceltFetched)] RAWINPUTDEVICE *rgelt,  
      [out] ULONG *pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="78fa8-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="78fa8-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="78fa8-106">[in] `rgelt` で返される [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) 構造体の数。</span><span class="sxs-lookup"><span data-stu-id="78fa8-106">[in] Number of [RAWINPUTDEVICE](/windows/desktop/api/winuser/ns-winuser-rawinputdevice) structures returned in `rgelt`.</span></span>  
  
 `rgelt`  
  
 <span data-ttu-id="78fa8-107">[out] 列挙された RAWINPUTDEVICE 構造体を受け取る size celt (またはそれ以上) の配列。</span><span class="sxs-lookup"><span data-stu-id="78fa8-107">[out] Array of size celt (or larger) to receive enumerated RAWINPUTDEVICE structures.</span></span>  
  
 `pceltFetched`  
  
 <span data-ttu-id="78fa8-108">[out] `rgelt` に実際に指定された要素の数へのポインター。</span><span class="sxs-lookup"><span data-stu-id="78fa8-108">[out] Pointer to the number of elements actually supplied in `rgelt`.</span></span> <span data-ttu-id="78fa8-109">`NULL` が 1 の場合、呼び出し元は `rgelt` に渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="78fa8-109">Caller can pass in `NULL` if `rgelt` is one.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="78fa8-110">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="78fa8-110">Property Value/Return Value</span></span>  
 <span data-ttu-id="78fa8-111">HRESULT:指定された要素の数が `celt` の場合は S_OK。それ以外の場合は S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="78fa8-111">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
