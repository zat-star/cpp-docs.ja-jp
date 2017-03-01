---
title: "accelerator_view_removed クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator_view_removed
dev_langs:
- C++
helpviewer_keywords:
- amprt/Concurrency::accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 6e7a56a3315dc38a9e7def2144f3a2f8efd363fc
ms.lasthandoff: 02/24/2017

---
# <a name="acceleratorviewremoved-class"></a>accelerator_view_removed クラス
基になる DirectX の呼び出しが Windows のタイムアウトの検出と回復機構が原因で失敗した場合にスローされる例外。  
  
## <a name="syntax"></a>構文  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[accelerator_view_removed コンス トラクター](#ctor)|`accelerator_view_removed` クラスの新しいインスタンスを初期化します。|  

### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get_view_removed_reason メソッド](#get_view_removed_reason)|原因を示す HRESULT エラー コードを返し、`accelerator_view`オブジェクトの削除。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** amprt.h  
  
 **名前空間:** Concurrency  

## <a name="a-namectora-acceleratorviewremoved"></a><a name="ctor"></a>accelerator_view_removed 

新しいインスタンスを初期化、 [accelerator_view_removed](accelerator-view-removed-class.md)クラスです。  
  
### <a name="syntax"></a>構文  
  
```  
explicit accelerator_view_removed(  
    const char * _Message,  
    HRESULT _View_removed_reason ) throw();  
  
explicit accelerator_view_removed(  
    HRESULT _View_removed_reason ) throw();  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明。  
  
 `_View_removed_reason`  
 削除の原因を示す HRESULT エラー コード、`accelerator_view`オブジェクトです。  
  
### <a name="return-value"></a>戻り値  
 Accelerator_view_removed クラスの新しいインスタンス。  
  
## <a name="a-namegetviewremovedreasonmethoda-getviewremovedreason"></a><a name="get_view_removed_reason_method"></a>get_view_removed_reason 

原因を示す HRESULT エラー コードを返し、`accelerator_view`オブジェクトの削除。  
  
### <a name="syntax"></a>構文  
  
```  
HRESULT get_view_removed_reason() const throw();  
```  
  
 
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

