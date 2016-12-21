---
title: "コンパイラ エラー C3073 | Microsoft Docs"
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
  - "C3073"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3073"
ms.assetid: b24b9b8b-f9fb-4c3c-a1a0-97fad2081bfc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3073
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'型' : ref クラスには、ユーザー定義されたコピー コンストラクターがありません  
  
 [\/clr \(共通言語ランタイムのコンパイル\)](../../build/reference/clr-common-language-runtime-compilation.md) コンパイルでは、コンパイラは参照型のコピー コンストラクターを生成しません。  参照型のインスタンスがコピーされることがわかっている場合は、**\/clr** コンパイルで、その型の独自のコピー コンストラクターを定義する必要があります。  
  
 詳細については、「[参照型の C\+\+ スタック セマンティクス](../../dotnet/cpp-stack-semantics-for-reference-types.md)」を参照してください。  
  
## 使用例  
 次の例では C3073 エラーが生成されます。  
  
```  
// C3073.cpp  
// compile with: /clr  
ref class R {  
public:  
   R(int) {}  
};  
  
ref class S {  
public:  
   S(int) {}  
   S(const S %rhs) {}   // copy constructor  
};  
  
void f(R) {}  
void f2(S) {}  
void f3(R%){}  
  
int main() {  
   R r(1);  
   f(r);   // C3073  
   f3(r);   // OK  
  
   S s(1);  
   f2(s);   // OK  
}  
```