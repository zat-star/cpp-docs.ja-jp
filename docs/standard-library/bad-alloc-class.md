---
title: "bad_alloc クラス |Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- new/std::bad_alloc
dev_langs:
- C++
helpviewer_keywords:
- bad_alloc class
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d338b155eaebd7678e611dd38b8e1ef230545eb5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="badalloc-class"></a>bad_alloc クラス
このクラスは、割り当て要求が成功しなかったことを示すためにスローされる例外を記述します。  
  
## <a name="syntax"></a>構文  
  
```  
class bad_alloc : public exception {  
    bad_alloc();
virtual ~bad_alloc();

};  
```  
  
## <a name="remarks"></a>コメント  
 **what** が返す値は、実装で定義された C 文字列です。 このメンバー関数は、いずれも例外をスローしません。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<new>  
  
 **名前空間:** std  
  
## <a name="example"></a>例  
  
```cpp  
// bad_alloc.cpp  
// compile with: /EHsc  
#include<new>  
#include<iostream>  
using namespace std;  
  
int main() {  
   char* ptr;  
   try {  
      ptr = new char[(~unsigned int((int)0)/2) - 1];  
      delete[] ptr;  
   }  
   catch( bad_alloc &ba) {  
      cout << ba.what( ) << endl;  
   }  
}  
```  
  
## <a name="sample-output"></a>出力例  
  
```  
bad allocation  
```  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \<new>  
  
## <a name="see-also"></a>参照
 [exception クラス](../standard-library/exception-class.md)  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

