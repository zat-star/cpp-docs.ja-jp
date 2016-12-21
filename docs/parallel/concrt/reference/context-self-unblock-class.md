---
title: "context_self_unblock クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::context_self_unblock"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "context_self_unblock クラス"
ms.assetid: 9601cd28-4f40-4c2e-89ab-747068956331
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# context_self_unblock クラス
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

このクラスは、同じコンテキストから `Unblock` オブジェクトの `Context` メソッドが呼び出された場合にスローされる例外を表します。 これは、特定のコンテキストがそれ自体のブロックを解除しようとしたことを示します。  
  
## <a name="syntax"></a>構文  
  
```  
class context_self_unblock : public std::exception;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[context_self_unblock::context_self_unblock コンス トラクター](#context_self_unblock__context_self_unblock_constructor)|オーバーロードされます。 `context_self_unblock` オブジェクトを構築します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `context_self_unblock`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namecontextselfunblockcontextselfunblockconstructora-contextselfunblockcontextselfunblock-constructor"></a><a name="context_self_unblock__context_self_unblock_constructor"></a>  context_self_unblock::context_self_unblock コンス トラクター  
 `context_self_unblock` オブジェクトを構築します。  
  
```  
explicit _CRTIMP context_self_unblock(_In_z_ const char* _Message) throw();

 
context_self_unblock() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)
