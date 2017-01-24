---
title: "コンパイラ エラー C3068 | Microsoft Docs"
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
  - "C3068"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3068"
ms.assetid: 613e3447-b4a8-4268-a661-297bed63ccdf
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3068
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'関数' : 'naked' 関数は、C\+\+ 例外が発生した場合に、アンワインディングを必要とするオブジェクトを含むことはできません  
  
 例外をスローした [naked](../Topic/naked%20\(C++\).md) 関数でスタック アンワインドを実行できませんでした。この関数で一時オブジェクトが作成され、C\+\+ 例外処理 \([\/EHsc](../../build/reference/eh-exception-handling-model.md)\) が指定されたためです。  
  
 このエラーを解決するには、以下の操作の少なくとも 1 つを実行します。  
  
-   \/EHsc を指定してコンパイルしません。  
  
-   関数は `naked` のマークを付けません。  
  
-   関数で一時オブジェクトを作成しません。  
  
 関数がスタックに一時オブジェクトを作成する場合、関数が例外をスローする場合、および C\+\+ 例外処理が有効な場合は、例外がスローされるとコンパイラはスタックをクリーンアップします。  
  
 例外がスローされると、prolog および epilog と呼ばれる naked 関数には存在しないコンパイラ生成のコードが、関数に対して実行されます。  
  
## 使用例  
 次の例では警告 C3068 が生成されます。  
  
```  
// C3068.cpp  
// compile with: /EHsc  
// processor: x86  
class A {  
public:  
   A(){}  
   ~A(){}  
};  
  
void b(A){}  
  
__declspec(naked) void c() {  
   b(A());   // C3068   
};  
```