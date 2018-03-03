---
title: "IID_PPV_ARGS_Helper 関数 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/IID_PPV_ARGS_Helper
dev_langs:
- C++
helpviewer_keywords:
- IID_PPV_ARGS_Helper function
ms.assetid: afee9b23-8df1-4575-903f-e9ba748418f0
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9839fe71439fde54545a18ef107cec178b8bdcd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="iidppvargshelper-function"></a>IID_PPV_ARGS_Helper 関数
指定された引数の型がから派生していることを確認、`IUnknown`インターフェイスです。  
  
> [!IMPORTANT]
>  このテンプレートの特殊化では、WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。 使用して[IID_PPV_ARGS](http://msdn.microsoft.com/library/windows/desktop/ee330727.aspx)代わりにします。  
  
## <a name="syntax"></a>構文  
  
```  
template<  
   typename T  
>  
void** IID_PPV_ARGS_Helper(  
   _Inout_ Microsoft::WRL::Details::ComPtrRef<T> pp  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 引数の型`pp`です。  
  
 `pp`  
 二重間接ポインター。  
  
## <a name="return-value"></a>戻り値  
 引数`pp`ポインターにキャスト、ポインター-に-を-`void`です。  
  
## <a name="remarks"></a>コメント  
 場合、コンパイル時エラーが生成されたテンプレート パラメーター`T`から派生していない`IUnknown`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** client.h  
  
## <a name="see-also"></a>参照  
 [参照 (Windows ランタイム ライブラリ)](http://msdn.microsoft.com/en-us/00000000-0000-0000-0000-000000000000)