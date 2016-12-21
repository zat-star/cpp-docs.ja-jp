---
title: "コンパイラの警告 (レベル 3) C4398 | Microsoft Docs"
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
  - "C4398"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4398"
ms.assetid: b6221432-9fed-4272-a547-a73f587904e6
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 3) C4398
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'変数' : プロセスごとのグローバル オブジェクトは複数の appdomain と共に動作しない可能性があります。\_\_declspec\(appdomain\) を使用することを考慮してください  
  
 [\_\_clrcall](../../cpp/clrcall.md) 呼び出し規約を持つ仮想関数がネイティブ型である場合、アプリケーション ドメインごとの vtable が作成されます。  このような変数は、複数のアプリケーション ドメインで使用される場合に適切に修正されない可能性があります。  
  
 この警告を解決するには、既定で appdomain ごとにグローバル変数を作成する **\/clr:pure** を指定してコンパイルするか、変数を `__declspec(appdomain)` で明示的にマークします。  
  
 詳細については、「[appdomain](../Topic/appdomain.md)」および「[アプリケーション ドメインと Visual C\+\+](../../dotnet/application-domains-and-visual-cpp.md)」を参照してください。  
  
## 使用例  
 次の例では C4398 エラーが生成されます。  
  
```  
// C4398.cpp  
// compile with: /clr /W3 /c  
struct S {  
   virtual void f( System::String ^ );   // String^ parameter makes function __clrcall  
};  
  
S glob_s;   // C4398  
__declspec(appdomain) S glob_s2;   // OK  
```