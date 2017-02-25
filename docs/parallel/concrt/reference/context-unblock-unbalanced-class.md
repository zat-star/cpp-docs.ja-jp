---
title: "context_unblock_unbalanced クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::context_unblock_unbalanced"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "context_unblock_unbalanced クラス"
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 20
---
# context_unblock_unbalanced クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、`Block` オブジェクトの `Unblock` メソッドと `Context` メソッドの呼び出しが正しく対になっていない場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[context_unblock_unbalanced::context_unblock_unbalanced コンス トラクター](#context_unblock_unbalanced__context_unblock_unbalanced_constructor)|オーバーロードされます。 `context_unblock_unbalanced` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 呼び出し、 `Block` と `Unblock` のメソッド、 `Context` オブジェクトのペアを正しく常にする必要があります。 同時実行ランタイムは、操作を任意の順序で実行できます。 呼び出しなど `Block` への呼び出しを続けて `Unblock`, 、またはその逆です。 たとえば、2 回の呼び出しをする場合は、この例外がスローされます、 `Unblock` メソッドで発生した行の `Context` ブロックされていないオブジェクトです。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namecontextunblockunbalancedcontextunblockunbalancedconstructora-contextunblockunbalancedcontextunblockunbalanced-constructor"></a><a name="context_unblock_unbalanced__context_unblock_unbalanced_constructor"></a>  context_unblock_unbalanced::context_unblock_unbalanced コンス トラクター  
 `context_unblock_unbalanced` オブジェクトを構築します。  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)
