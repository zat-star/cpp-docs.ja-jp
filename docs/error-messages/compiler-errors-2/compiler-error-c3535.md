---
title: "コンパイラ エラー C3535 | Microsoft Docs"
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
  - "C3535"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3535"
ms.assetid: 24449c98-f681-484d-a00b-32533dca3a88
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3535
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1' の型を 'type2' から推測できません  
  
 `auto` キーワードを使用して宣言された変数の型が、初期化子式の型から推測できません。  たとえば、このエラーは初期化子式が型ではない `void` を評価する場合に発生します。  
  
### このエラーを解決するには  
  
1.  初期化子式の型が `void` ではないことを確認します。  
  
2.  宣言が基本型に対するポインターでないことを確認します。  詳細については、「[基本型](../../cpp/fundamental-types-cpp.md)」を参照してください。  
  
3.  宣言が型に対するポインターの場合、初期化子式がポインター型であることを確認します。  
  
## 使用例  
 次の例では、初期化子式が `void` を評価するため、C3535 が発生します。  
  
```  
// C3535a.cpp  
// Compile with /Zc:auto  
void f(){}  
int main()  
{  
   auto x = f();   //C3535  
   return 0;  
}  
```  
  
## 使用例  
 次の例では、ステートメントが変数 `x` を推測される型へのポインターとして宣言していますが、初期化子式の型が double のため、C3535 が発生します。  その結果、コンパイラは変数のデータ型を推測できません。  
  
```  
// C3535b.cpp  
// Compile with /Zc:auto  
int main()  
{  
   auto* x = 123.0;   // C3535  
   return 0;  
}  
```  
  
## 使用例  
 次の例では、変数 `p` が推測される型へのポインターを宣言していますが、初期化子式がポインター型でないため、C3535 が発生します。  
  
```  
// C3535c.cpp  
// Compile with /Zc:auto  
class A { };  
A x;  
auto *p = x;  // C3535  
```  
  
## 参照  
 [auto キーワード](../../cpp/auto-keyword.md)   
 [基本型](../../cpp/fundamental-types-cpp.md)