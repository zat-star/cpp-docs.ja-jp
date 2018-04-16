---
title: "_ _if_not_exists ステートメント |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __if_not_exists_cpp
dev_langs:
- C++
helpviewer_keywords:
- __if_not_exists keyword [C++]
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2342354528811f415a9c9aeb819e2c0e7cec6646
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ifnotexists-statement"></a>__if_not_exists ステートメント
`__if_not_exists` ステートメントは、指定された識別子があるかどうかをテストします。 ID が存在しない場合、指定されたステートメント ブロックが実行されます。  
  
## <a name="syntax"></a>構文  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### <a name="parameters"></a>パラメーター  
  
|パラメーター|説明|  
|---------------|-----------------|  
|`identifier`|存在をテストしたい識別子。|  
|`statements`|場合に実行する 1 つまたは複数のステートメント`identifier`存在しません。|  
  
## <a name="remarks"></a>コメント  
  
> [!CAUTION]
>  最も信頼できる結果を得るには、次の制約に基づいて `__if_not_exists` ステートメントを使用します。  
  
-   テンプレートではなく、単純型にのみ `__if_not_exists` ステートメントを適用します。  
  
-   クラスの内部または外部の識別子に `__if_not_exists` ステートメントを適用します。 ローカル変数に `__if_not_exists` ステートメントを適用しないでください。  
  
-   `__if_not_exists` ステートメントは関数の本体でのみ使用します。 関数本体の外側では、`__if_not_exists` ステートメントは完全に定義された型のみテストできます。  
  
-   オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。  
  
 補完する、`__if_not_exists`ステートメントは、 [_ _if_exists](../cpp/if-exists-statement.md)ステートメントです。  
  
## <a name="example"></a>例  
 使用する方法の例については`__if_not_exists`を参照してください[_ _if_exists ステートメント](../cpp/if-exists-statement.md)です。  
  
## <a name="see-also"></a>参照  
 [選択ステートメント](../cpp/selection-statements-cpp.md)   
 [キーワード](../cpp/keywords-cpp.md)   
 [__if_exists ステートメント](../cpp/if-exists-statement.md)