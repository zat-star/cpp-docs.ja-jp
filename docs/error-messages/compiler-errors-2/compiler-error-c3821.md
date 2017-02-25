---
title: "コンパイラ エラー C3821 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3821"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3821"
ms.assetid: 2b327c7a-5faf-443c-ae82-944fae25b4df
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラ エラー C3821
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数': マネージ型または関数は、アンマネージ関数で使用できません。  
  
 インライン アセンブリまたは [setjmp](../../c-runtime-library/reference/setjmp.md) を持つ関数には、値の型またはマネージ クラスを含めることはできません。  このエラーを解決するには、インライン アセンブリと `setjmp` を削除するか、またはマネージ オブジェクトを削除します。  
  
 vararg 関数でローカルな寿命を使おうとした場合も、C3821 エラーが発生します。詳細については、「[Variable Argument Lists \(...\) \(C\+\+\/CLI\)](../../windows/variable-argument-lists-dot-dot-dot-cpp-cli.md)」および「[参照型の C\+\+ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)」を参照してください。  
  
## 使用例  
 次の例では C3821 エラーが生成されます。  
  
```  
// C3821a.cpp  
// compile with: /clr /c  
public ref struct R {};  
void test1(...) {  
   R r;   // C3821  
}  
```  
  
## 使用例  
 次の例では C3821 エラーが生成されます。  
  
```  
// C3821b.cpp  
// compile with: /clr  
// processor: /x86  
ref class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A ^a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```  
  
## 使用例  
 次の例では C3821 エラーが生成されます。  
  
```  
// C3821c.cpp  
// compile with: /clr:oldSyntax  
// processor: /x86  
__gc  class A {  
   public:  
   int i;  
};  
  
int main() {  
   // cannot use managed classes in this function  
   A *a;     
  
   __asm {  
      nop  
   }  
} // C3821  
```