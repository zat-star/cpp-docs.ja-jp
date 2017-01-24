---
title: "コンパイラ エラー C2316 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2316"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2316"
ms.assetid: 9ad08eb5-060b-4eb0-8d66-0dc134f7bf67
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C2316
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'exception': デストラクターまたはコピー コンストラクターにアクセスできないためキャッチできません  
  
 値または参照によって例外がキャッチされましたが、コピー コンストラクターや代入演算子にアクセスできませんでした。  
  
 このコードは、以前のバージョンのコンパイラによって受け入れられましたが、エラーになります。  
  
## 使用例  
 次の例では C2316 が生成されます。  
  
```  
// C2316.cpp // compile with: /EHsc #include <stdio.h> extern "C" int printf_s(const char*, ...); struct B { public: B() {} // Delete the following line to resolve. private: // copy constructor B(const B&) { } }; void f(const B&) { } int main() { try { B aB; f(aB); } catch (B b) {   // C2316 printf_s("Caught an exception!\n"); } }  
```