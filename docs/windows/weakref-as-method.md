---
title: Weakref::as メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::As
dev_langs:
- C++
helpviewer_keywords:
- As method
ms.assetid: 7173da62-b3fe-44d6-aea4-1aa97e69b221
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 034664c91af422aed26f27b924827238b26a9134
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/22/2018
---
# <a name="weakrefas-method"></a>WeakRef::As メソッド
指定された ComPtr ポインター パラメーターを、指定されたインターフェイスを表すように設定します。  
  
## <a name="syntax"></a>構文  
  
```  
  
template<typename U>  
HRESULT As(  
   _Out_ ComPtr<U>* ptr  
);  
  
template<typename U>  
HRESULT As(  
   _Out_ Details::ComPtrRef<ComPtr<U>> ptr  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `U`  
 インターフェイス ID。  
  
 `ptr`  
 この操作の完了時の、パラメーター `U`を表すオブジェクト。  
  
## <a name="return-value"></a>戻り値  
  
-   この操作が成功すると S_OK になります。失敗すると HRESULT (操作が失敗した理由を示す) になり、 `ptr` は `nullptr`に設定されます。  
  
-   この操作が成功すると S_OK になりますが、現在の WeakRef オブジェクトは既に解放されています。 パラメーターを `ptr` を `nullptr`に設定します。  
  
-   この操作が成功すると S_OK になりますが、現在の WeakRef オブジェクトはパラメーター `U`から派生しません。 パラメーター `ptr` は `nullptr`に設定されます。  
  
## <a name="remarks"></a>コメント  
 `U` が IWeakReference の場合、エラーが生成されます。あるいは、IInspectable から派生しません。  
  
 最初のテンプレートは、コードで使用する必要があるフォームです。 2 番目のテンプレートは、 [auto](../cpp/auto-cpp.md) 型推論キーワードなどの C++ 言語の機能をサポートしている内部ヘルパーの特殊化です。  
  
 Windows 10 SDK 以降では、弱い参照を取得できなかった場合、このメソッドは WeakRef インスタンスを `nullptr` に設定しません。そのため、 `nullptr`の WeakRef を確認するエラー チェック コードは避けてください。 代わりに、確認`ptr`の`nullptr`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [WeakRef クラス](../windows/weakref-class.md)