---
title: "bad_exception クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.bad_exception"
  - "bad_exception"
  - "std::bad_exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_exception クラス"
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# bad_exception クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このクラスは、予期しないハンドラーからスローされる例外を表します。  
  
## <a name="syntax"></a>構文  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>解説  
 [予期しない](../Topic/%3Cexception%3E%20functions.md#unexpected) をスロー、 `bad_exception` で指定された別の関数を呼び出す代わりに、または終了ではなく [set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) 場合 `bad_exception` 関数の throw のリストに含まれています。  
  
 によって返される値 **何** 実装定義の C 文字列します。 このメンバー関数は、いずれも例外をスローしません。  
  
 継承されたメンバーの一覧については、 `bad_exception` を参照してください [例外クラス](../standard-library/exception-class1.md)します。  
  
## <a name="example"></a>例  
 参照してください [set_unexpected](../Topic/%3Cexception%3E%20functions.md#set_unexpected) の使用例については [予期しない](../Topic/%3Cexception%3E%20functions.md#unexpected) スロー、 `bad_exception`です。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \< 例外>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
[exception クラス](../standard-library/exception-class1.md)
 [、C++ 標準ライブラリ内のスレッドの安全性](../standard-library/thread-safety-in-the-cpp-standard-library.md)

