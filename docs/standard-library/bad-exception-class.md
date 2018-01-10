---
title: "bad_exception クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: exception/std::bad_exception
dev_langs: C++
helpviewer_keywords: bad_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b5b91f3019a46aa011f95ae26434456d1e41de08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="badexception-class"></a>bad_exception クラス
このクラスは、予期しないハンドラーからスローされる例外を記述します。  
  
## <a name="syntax"></a>構文  
  
```  
class bad_exception    : public exception {};  
```  
  
## <a name="remarks"></a>コメント  
 [unexpected](../standard-library/exception-functions.md#unexpected) は、`bad_exception` が関数のスロー リストに含まれている場合には、終了の代わりに、または [set_unexpected](../standard-library/exception-functions.md#set_unexpected) で指定された別の関数を呼び出す代わりに、`bad_exception` をスローします。  
  
 **what** が返す値は、実装で定義された C 文字列です。 このメンバー関数は、いずれも例外をスローしません。  
  
 `bad_exception` クラスで継承されたメンバーの一覧については、「[exception クラス](../standard-library/exception-class.md)」を参照してください。  
  
## <a name="example"></a>例  
 `bad_exception` をスローする [unexpected](../standard-library/exception-functions.md#unexpected) の使用例については、「[set_unexpected](../standard-library/exception-functions.md#set_unexpected)」を参照してください。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<exception>  
  
 **名前空間:** std  
  
## <a name="see-also"></a>参照  
[exception クラス](../standard-library/exception-class.md) [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

