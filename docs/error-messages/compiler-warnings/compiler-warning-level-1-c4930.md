---
title: "コンパイラの警告 (レベル 1) C4930 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4930"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4930"
ms.assetid: 89a206c9-c536-4186-8e81-1cde3e7f4f5b
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラの警告 (レベル 1) C4930
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'prototype' : プロトタイプされている関数が呼び出されませんでした \(変数の定義が意図されていますか?\)。  
  
 未使用の関数プロトタイプが見つかりました。  プロトタイプが変数宣言として指定されている場合は、左右のかっこを削除してください。  
  
 次の例では警告 C4930 が生成されます。  
  
```  
// C4930.cpp  
// compile with: /W1  
class Lock {  
public:  
   int i;  
};  
  
void f() {  
   Lock theLock();   // C4930  
   // try the following line instead  
   // Lock theLock;  
}  
  
int main() {  
}  
```  
  
 コンパイラが関数のプロトタイプ宣言と関数の呼び出しとを区別できなかった場合にも C4930 が発生します。  
  
 次の例では警告 C4930 が生成されます。  
  
```  
// C4930b.cpp  
// compile with: /EHsc /W1  
  
class BooleanException  
{  
   bool _result;  
  
public:  
   BooleanException(bool result)  
      : _result(result)  
   {  
   }  
  
   bool GetResult() const  
   {  
      return _result;  
   }  
};  
  
template<class T = BooleanException>  
class IfFailedThrow  
{  
public:  
   IfFailedThrow(bool result)  
   {  
      if (!result)  
      {  
         throw T(result);  
      }  
   }  
};  
  
class MyClass  
{  
public:  
   bool MyFunc()  
   {  
      try  
      {  
         IfFailedThrow<>(MyMethod()); // C4930  
  
         // try one of the following lines instead  
         // IfFailedThrow<> ift(MyMethod());  
         // IfFailedThrow<>(this->MyMethod());  
         // IfFailedThrow<>((*this).MyMethod());  
  
         return true;  
      }  
      catch (BooleanException e)  
      {  
         return e.GetResult();  
      }  
   }  
  
private:  
   bool MyMethod()  
   {  
      return true;  
   }  
};  
  
int main()  
{  
   MyClass myClass;  
   myClass.MyFunc();  
}  
```  
  
 上の例では、引数を 1 つも受け取らないメソッドの結果が、名前のないローカル クラス変数のコンストラクターの引数として渡されています。  このようなあいまいな呼び出しを解決するには、ローカル変数に名前を付けるか、メソッド呼び出しのプレフィックスとしてオブジェクト インスタンスを \(適切なポインタメンバー演算子を付けて\) 指定します。