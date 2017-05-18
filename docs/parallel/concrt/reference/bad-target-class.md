---
title: "bad_target クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
dev_langs:
- C++
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 145aa17b4589fb572f3b6594360ec69db5e15287
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="badtarget-class"></a>bad_target クラス
このクラスは、実行する操作の無効なターゲットへのポインターがメッセージング ブロックに渡された場合にスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```
class bad_target : public std::exception;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[bad_target](#ctor)|オーバーロードされます。 `bad_target` オブジェクトを構築します。|  
  
## <a name="remarks"></a>コメント  
 保持していない予約を解放したり、別のターゲットで予約されているメッセージが処理しようとしています。 ターゲットなどの理由には、通常この例外がスローされます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrt.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a>bad_target 

 `bad_target` オブジェクトを構築します。  
  
```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```  
  
### <a name="parameters"></a>パラメーター  
 `_Message`  
 エラーの説明メッセージ。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)




