---
title: "context_unblock_unbalanced クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::context_unblock_unbalanced
dev_langs:
- C++
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: 20
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 7341ff5d10b7f7752c49f18ea9b810824e347b1c
ms.lasthandoff: 02/24/2017

---
# <a name="contextunblockunbalanced-class"></a>context_unblock_unbalanced クラス
このクラスは、`Block` オブジェクトの `Unblock` メソッドと `Context` メソッドの呼び出しが正しく対になっていない場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[context_unblock_unbalanced コンス トラクター](#ctor)|オーバーロードされます。 `context_unblock_unbalanced` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 呼び出し、`Block`と`Unblock`のメソッド、`Context`オブジェクトのペアを正しく常にする必要があります。 同時実行ランタイムは、操作を任意の順序で実行できます。 呼び出しなど`Block`への呼び出しを続けて`Unblock`、またはその逆です。 たとえば、2 回の呼び出しをする場合は、この例外がスローされます、`Unblock`メソッドで発生した行の`Context`ブロックされていないオブジェクトです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namectora-contextunblockunbalanced"></a><a name="ctor"></a>context_unblock_unbalanced 

 `context_unblock_unbalanced` オブジェクトを構築します。  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

