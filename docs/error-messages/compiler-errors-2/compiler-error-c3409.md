---
title: "コンパイラ エラー C3409 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3409"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3409"
ms.assetid: e372d9fa-230c-4b28-b6d3-6ad81ccf9dbb
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3409
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

空の属性ブロックは認められません。  
  
 角かっこは[属性](../../windows/cpp-attributes-reference.md)ブロックとして解釈されましたが、属性が見つかりませんでした。  
  
 コンパイラは、ラムダ式の定義の一部に角かっこを使用した場合に、このエラーを生成することがあります。  このエラーは、角かっこがラムダ式の定義または属性ブロックの一部かどうかがコンパイラで識別できない場合に発生します。  ラムダ式の詳細については、「[ラムダ式](../../cpp/lambda-expressions-in-cpp.md)」を参照してください。  
  
### このエラーを解決するには  
  
1.  角かっこが属性ブロックの一部の場合、次のいずれかを実行します。  
  
    1.  属性ブロック内で、1 つ以上の属性を指定します。  
  
    2.  属性ブロックを削除します。  
  
2.  角かっこがラムダ式の一部の場合、次の操作を実行します。  
  
    1.  ラムダ式が有効な構文規則に従っていることを確認します。  
  
         ラムダ式の構文の詳細については、「[ラムダ式の構文](../../cpp/lambda-expression-syntax.md)」を参照してください。  
  
## 使用例  
 次のコードでは、C3409 が生成されます。  
  
```  
// C3409.cpp  
// compile with: /c  
#include <windows.h>  
[]   // C3409  
class a {};  
  
// OK  
[object, uuid("00000000-0000-0000-0000-000000000000")]  
__interface x {};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000001")]  
class b : public x {};  
```  
  
## 使用例  
 次の例では、ラムダ式に `mutable` 仕様が使用されていて、パラメーター リストが指定されていないため、C3409 が発生します。  角かっこがラムダ式の定義または属性ブロックの一部かどうかが、コンパイラで識別できません。  
  
```  
// C3409b.cpp  
  
int main()  
{  
   [] mutable {}();  
}  
```  
  
## 参照  
 [属性](../../windows/cpp-attributes-reference.md)   
 [ラムダ式](../../cpp/lambda-expressions-in-cpp.md)   
 [ラムダ式の構文](../../cpp/lambda-expression-syntax.md)