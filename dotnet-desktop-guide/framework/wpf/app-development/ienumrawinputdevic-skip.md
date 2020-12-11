---
title: IEnumRAWINPUTDEVIC:Skip
ms.date: 03/30/2017
helpviewer_keywords:
- Skip method [WPF]
ms.assetid: c967b0f8-1c6a-459c-8c16-d4f08918ab65
ms.openlocfilehash: a74f71345a22f6d766c2d5966ca5d2cb33ab756e
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96984348"
---
# <a name="ienumrawinputdevicskip"></a><span data-ttu-id="29149-102">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="29149-102">IEnumRAWINPUTDEVIC:Skip</span></span>
<span data-ttu-id="29149-103">[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) の次回の呼び出しで列挙型の `celt` 要素が返されないように、次のこの要素をスキップするよう列挙子に指示します。</span><span class="sxs-lookup"><span data-stu-id="29149-103">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="29149-104">構文</span><span class="sxs-lookup"><span data-stu-id="29149-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip( [in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="29149-105">パラメーター</span><span class="sxs-lookup"><span data-stu-id="29149-105">Parameters</span></span>  
 `celt`  
  
 <span data-ttu-id="29149-106">[in] スキップする要素の数。</span><span class="sxs-lookup"><span data-stu-id="29149-106">[in] Number of elements to be skipped.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="29149-107">プロパティ値/戻り値</span><span class="sxs-lookup"><span data-stu-id="29149-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="29149-108">HRESULT:指定された要素の数が `celt` の場合は S_OK。それ以外の場合は S_FALSE。</span><span class="sxs-lookup"><span data-stu-id="29149-108">HRESULT: S_OK if the number of elements supplied is `celt`; S_FALSE otherwise.</span></span>
