---
title: "once_flag 構造体 | Microsoft Docs"
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
  - "mutex/std::once_flag"
dev_langs: 
  - "C++"
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# once_flag 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`struct` を表し、初期化コードは一度だけ呼び出される、複数の実行スレッドの前にことを保証するために、テンプレート関数 [call\_once](../Topic/call_once%20Function.md) で使用されています。  
  
## 構文  
  
```cpp  
struct once_flag  
{  
   constexpr once_flag() noexcept;  
   once_flag(const once_flag&);  
   once_flag& operator=(const once_flag&);  
};  
```  
  
## 解説  
 `once_flag` `struct` に既定のコンストラクターがあります。  
  
 型 `once_flag` オブジェクトを作成できます。コピーできません。  
  
## 必要条件  
 **ヘッダー:** mutex  
  
 **名前空間:** std  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)