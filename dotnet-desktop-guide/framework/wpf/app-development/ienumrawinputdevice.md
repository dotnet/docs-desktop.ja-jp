---
title: IEnumRAWINPUTDEVICE
ms.date: 03/30/2017
helpviewer_keywords:
- IEnumRAWINPUTDEVICE interface [WPF]
ms.assetid: 88c8b389-a48b-46b9-b895-8ed7b1e26fea
ms.openlocfilehash: 5249d7ea359db5d5c58ae87600f61048b465b4c1
ms.sourcegitcommit: 9f6df084c53a3da0ea657ed0d708a72213683084
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "96985484"
---
# <a name="ienumrawinputdevice"></a><span data-ttu-id="793bf-102">IEnumRAWINPUTDEVICE</span><span class="sxs-lookup"><span data-stu-id="793bf-102">IEnumRAWINPUTDEVICE</span></span>
<span data-ttu-id="793bf-103">このインターフェイスは、未加工入力デバイスを列挙し、 PresentationHost.exe でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="793bf-103">This interface enumerates the raw input devices, and is only used by PresentationHost.exe.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="793bf-104">この API は、ローカル クライアント コンピューターでの使用のみを目的とし、サポートされています。</span><span class="sxs-lookup"><span data-stu-id="793bf-104">This API is only intended and supported for use on the local client machine</span></span>  
  
## <a name="members"></a><span data-ttu-id="793bf-105">メンバー</span><span class="sxs-lookup"><span data-stu-id="793bf-105">Members</span></span>  
  
|<span data-ttu-id="793bf-106">メンバー</span><span class="sxs-lookup"><span data-stu-id="793bf-106">Member</span></span>|<span data-ttu-id="793bf-107">説明</span><span class="sxs-lookup"><span data-stu-id="793bf-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="793bf-108">IEnumRAWINPUTDEVIC:Next</span><span class="sxs-lookup"><span data-stu-id="793bf-108">IEnumRAWINPUTDEVIC:Next</span></span>](ienumrawinputdevic-next.md)|<span data-ttu-id="793bf-109">次の `celt` 要素 (つまり RAWINPUTDEVICE 構造体) を、列挙子の一覧で列挙するとともに、それを `rgelt` で列挙された要素の実際の数とともに `pceltFetched` で返します。</span><span class="sxs-lookup"><span data-stu-id="793bf-109">Enumerates the next `celt` elements (that is, RAWINPUTDEVICE structures) in the enumerator's list, returning them in `rgelt` along with the actual number of enumerated elements in `pceltFetched`.</span></span>|  
|[<span data-ttu-id="793bf-110">IEnumRAWINPUTDEVIC:Skip</span><span class="sxs-lookup"><span data-stu-id="793bf-110">IEnumRAWINPUTDEVIC:Skip</span></span>](ienumrawinputdevic-skip.md)|<span data-ttu-id="793bf-111">[IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) の次回の呼び出しで列挙型の `celt` 要素が返されないように、次のこの要素をスキップするよう列挙子に指示します。</span><span class="sxs-lookup"><span data-stu-id="793bf-111">Instructs the enumerator to skip the next `celt` elements in the enumeration so that the next call to [IEnumRAWINPUTDEVIC:Next](ienumrawinputdevic-next.md) will not return those elements.</span></span>|  
|[<span data-ttu-id="793bf-112">IEnumRAWINPUTDEVIC:Reset</span><span class="sxs-lookup"><span data-stu-id="793bf-112">IEnumRAWINPUTDEVIC:Reset</span></span>](ienumrawinputdevic-reset.md)|<span data-ttu-id="793bf-113">列挙のシーケンスを最初にリセットします。</span><span class="sxs-lookup"><span data-stu-id="793bf-113">Resets the enumeration sequence to the beginning.</span></span>|  
|[<span data-ttu-id="793bf-114">IEnumRAWINPUTDEVIC:Clone</span><span class="sxs-lookup"><span data-stu-id="793bf-114">IEnumRAWINPUTDEVIC:Clone</span></span>](ienumrawinputdevic-clone.md)|<span data-ttu-id="793bf-115">同じリストを反復処理するため、現在の列挙子と同じ状態の別の未加工入力デバイスの列挙子を作成します。</span><span class="sxs-lookup"><span data-stu-id="793bf-115">Creates another raw input device enumerator with the same state as the current enumerator to iterate over the same list.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="793bf-116">関連項目</span><span class="sxs-lookup"><span data-stu-id="793bf-116">See also</span></span>

- [<span data-ttu-id="793bf-117">生の入力について</span><span class="sxs-lookup"><span data-stu-id="793bf-117">About Raw Input</span></span>](/windows/desktop/inputdev/about-raw-input)
