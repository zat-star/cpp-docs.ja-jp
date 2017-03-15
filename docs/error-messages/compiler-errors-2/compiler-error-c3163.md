---
title: "コンパイラ エラー C3163 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3163"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3163"
ms.assetid: 17dcafa3-f416-4e04-a232-f9569218ba75
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C3163
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'コンストラクト': 属性が前の宣言と整合しません。  
  
 定義に適用された属性が宣言に適用された属性と競合しています。  
  
 C3163 を解決する方法の 1 つは、事前宣言の属性を削除することです。  事前宣言の属性は、定義の属性を超過しない必要があります。  
  
 C3163 エラーの原因の 1 つとしては、Microsoft のソース コード注釈言語 \(SAL\) に関するものがあります。  **\/analyze** フラグを使用してプロジェクトをコンパイルしない限り、SAL マクロは展開しません。  \/analyze を使用しないでコンパイルしてエラーがなかったプログラムを \/analyze オプションを指定して再コンパイルすると、C3163 エラーをスローすることがあります。  SAL の詳細については、「[SAL 注釈](../../c-runtime-library/sal-annotations.md)」を参照してください。  
  
## 使用例  
 次の例では C3163 エラーが生成されます。  
  
```  
// C3163.cpp  
// compile with: /clr /c  
using namespace System;  
  
[CLSCompliant(true)] void f();  
[CLSCompliant(false)] void f() {}   // C3163  
// try the following line instead  
// [CLSCompliant(true)] void f() {}  
```  
  
## 参照  
 [SAL 注釈](../../c-runtime-library/sal-annotations.md)