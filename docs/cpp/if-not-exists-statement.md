---
title: "__if_not_exists ステートメント | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__if_not_exists"
  - "__if_not_exists_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__if_not_exists キーワード [C++]"
ms.assetid: a2f322d4-e96f-4a32-954e-4323d20c6e32
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# __if_not_exists ステートメント
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`__if_not_exists` ステートメントは、指定された識別子があるかどうかをテストします。  ID が存在しない場合、指定されたステートメント ブロックが実行されます。  
  
## 構文  
  
```  
__if_not_exists ( identifier ) {   
statements  
};  
```  
  
#### パラメーター  
  
|パラメーター|説明|  
|------------|--------|  
|`identifier`|存在をテストしたい識別子。|  
|`statements`|`identifier`  が存在しない場合に実行する 1 つ以上のステートメント。|  
  
## 解説  
  
> [!CAUTION]
>  最も信頼できる結果を得るには、次の制約に基づいて `__if_not_exists` ステートメントを使用します。  
  
-   テンプレートではなく、単純型にのみ `__if_not_exists` ステートメントを適用します。  
  
-   クラスの内部または外部の識別子に `__if_not_exists` ステートメントを適用します。  ローカル変数に `__if_not_exists` ステートメントを適用しないでください。  
  
-   `__if_not_exists` ステートメントは関数の本体でのみ使用します。  関数本体の外側では、`__if_not_exists` ステートメントは完全に定義された型のみテストできます。  
  
-   オーバーロードされた関数をテストする場合、特定の形式のオーバーロードはテストできません。  
  
 [\_\_if\_exists](../cpp/if-exists-statement.md) ステートメントは、`__if_not_exists` ステートメントを補完します。  
  
## 使用例  
 `__if_not_exists` の使用例については、「[\_\_if\_exists ステートメント](../cpp/if-exists-statement.md)」を参照してください。  
  
## 参照  
 [選択ステートメント](../cpp/selection-statements-cpp.md)   
 [C\+\+ キーワード](../cpp/keywords-cpp.md)   
 [\_\_if\_exists ステートメント](../cpp/if-exists-statement.md)