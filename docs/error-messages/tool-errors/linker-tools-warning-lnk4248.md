---
title: "リンカー ツールの警告 LNK4248 | Microsoft Docs"
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
  - "LNK4248"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK4248"
ms.assetid: e40523ff-e3cb-4ba6-ab79-23f0f339f6cf
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# リンカー ツールの警告 LNK4248
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

未解決の typeref トークン \('トークン'\) \('型'\) です。イメージを実行できません。  
  
 MSIL メタデータに型の定義がありません。  
  
 LNK4248 は、\(**\/clr** を指定してコンパイルされた\) MSIL モジュールに型の事前宣言しかない場合に、その型が MSIL モジュールで参照され、さらにその MSIL モジュールがその型の定義を持つネイティブ モジュールにリンクされると発生することがあります。  
  
 この場合、リンカーがネイティブな型定義を MSIL メタデータに提供することにより、正しい動作が実行されることがあります。  
  
 ただし、事前の型宣言が CLR 型の場合は、リンカーのネイティブ型定義が正しくない可能性があります。  
  
 詳細については、「[\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md)」を参照してください。  
  
### このエラーを解決するには  
  
1.  MSIL モジュールで型定義を提供します。  
  
## 使用例  
 次の例では LNK4248 エラーが生成されます。  解決するには、構造体 A を定義します。  
  
```  
// LNK4248.cpp  
// compile with: /clr /W1  
// LNK4248 expected  
struct A;  
void Test(A*){}  
  
int main() {  
   Test(0);  
}  
```  
  
## 使用例  
 次のサンプルでは、型の事前定義が行われています。  
  
```  
// LNK4248_2.cpp  
// compile with: /clr /c  
class A;   // provide a definition for A here to resolve  
A * newA();  
int valueA(A * a);  
  
int main() {  
   A * a = newA();  
   return valueA(a);  
}  
```  
  
## 使用例  
 次の例では LNK4248 エラーが生成されます。  
  
```  
// LNK4248_3.cpp  
// compile with: /c  
// post-build command: link LNK4248_2.obj LNK4248_3.obj  
class A {  
public:   
   int b;  
};  
  
A* newA() {  
   return new A;  
}  
  
int valueA(A * a) {  
   return (int)a;  
}  
```