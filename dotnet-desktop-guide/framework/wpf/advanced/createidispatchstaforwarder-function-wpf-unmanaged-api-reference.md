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
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a>CreateIDispatchSTAForwarder 関数 (WPF のアンマネージ API リファレンス)
この API は、Windows Presentation Foundation (WPF) インフラストラクチャをサポートしますが、独自に作成したコードから直接使用するためのものではありません。  
  
 スレッドおよびウィンドウの管理のために Windows Presentation Foundation (WPF) インフラストラクチャによって使用されます。  
  
## <a name="syntax"></a>構文  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a>パラメーター  
  
## <a name="property-valuereturn-value"></a>プロパティ値/戻り値  
 pDispatchDelegate  
 `IDispatch` インターフェイスへのポインター。  
  
 ppForwarder  
 `IDispatch` インターフェイスのアドレスへのポインター。  
  
## <a name="requirements"></a>必要条件  
 **プラットフォーム:** 「[.NET Framework システム要件](/dotnet/framework/get-started/system-requirements)」をご覧ください。  
  
 **DLL:**  
  
 .NET Framework 3.0 および 3.5 の場合:PresentationHostDLL.dll  
  
 .NET Framework 4 以降の場合:PresentationHost_v0400.dll  
  
 **.NET Framework のバージョン:** [!INCLUDE[net_current_v30plus](../../../includes/net-current-v30plus-md.md)]  
  
## <a name="see-also"></a>関連項目

- [WPF のアンマネージ API リファレンス](wpf-unmanaged-api-reference.md)
