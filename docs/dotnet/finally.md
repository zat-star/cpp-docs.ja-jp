---
title: "finally | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "finally キーワード [C++]"
ms.assetid: b55f3c8e-1af0-43e8-bcfb-99c3685d2578
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# finally
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`try` と `catch` 句に加えて、CLR の例外処理は `finally` 句をサポートします。  セマンティクスは構造化例外処理 \(SEH\) の `__finally` ブロックと同じです。  `__finally` ブロックは `try` または `catch` ブロックに進むことができます。  
  
## 解説  
 `finally` ブロックの目的は、発生した例外の後に残っているリソースをクリーンアップすることです。  例外がスローされなくてが `finally` ブロックが必ず実行されることに注意してください。  `catch` ブロックはマネージ例外が `try` 関連のブロック内でスローされれば場合にのみ実行されます。  
  
 `finally` は状況依存のキーワードです。詳細については、「[状況依存のキーワード](../windows/context-sensitive-keywords-cpp-component-extensions.md)」を参照してください。  
  
## 使用例  
 次の例では `finally` の単純なブロックを示します。:  
  
```  
// keyword__finally.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyException: public System::Exception{};  
  
void ThrowMyException() {  
   throw gcnew MyException;  
}  
  
int main() {  
   try {  
      ThrowMyException();  
   }  
   catch ( MyException^ e ) {  
      Console::WriteLine(  "in catch" );  
      Console::WriteLine( e->GetType() );  
   }  
   finally {  
      Console::WriteLine(  "in finally" );  
   }  
}  
```  
  
  **catch**  
**MyException**  
**最終的に**   
## 参照  
 [Exception Handling](../windows/exception-handling-cpp-component-extensions.md)