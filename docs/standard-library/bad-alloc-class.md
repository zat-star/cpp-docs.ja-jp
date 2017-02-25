---
title: "bad_alloc クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::bad_alloc"
  - "new/std:bad_alloc"
  - "bad_alloc"
  - "std.bad_alloc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_alloc クラス"
ms.assetid: 6429a8e6-5a49-4907-8d56-f4a4ec8131d0
caps.latest.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 26
---
# bad_alloc クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

このクラスは、割り当て要求が成功しなかったことを示すためにスローされる例外を記述します。  
  
## <a name="syntax"></a>構文  
  
```  
class bad_alloc : public exception {  
    bad_alloc();
virtual ~bad_alloc();

};  
```  
  
## <a name="remarks"></a>解説  
 によって返される値 **何** 実装定義の C 文字列します。 このメンバー関数は、いずれも例外をスローしません。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** \< 新規作成>  
  
 **名前空間:** std  
  
## <a name="example"></a>例  
  
```  
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
 **ヘッダー:** \< 新規作成>  
  
## <a name="see-also"></a>参照
 [exception クラス](../standard-library/exception-class1.md)  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)

