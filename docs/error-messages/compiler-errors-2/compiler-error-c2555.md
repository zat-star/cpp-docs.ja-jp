---
title: "コンパイラ エラー C2555 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2555"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2555"
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# コンパイラ エラー C2555
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

' class1::function1': オーバーライドする仮想関数の戻り値の型が異なり、'class2::function2' の covariant ではありません。  
  
 仮想関数と派生したオーバーライド関数のパラメーター リストは同じですが、戻り値の型が異なっています。  派生クラスのオーバーライド関数と基本クラスの仮想関数で、戻り値の型だけが異なると無効です。  
  
 このエラーを解決するには、仮想関数を呼び出した後に戻り値をキャストします。  
  
 \/clr を指定してコンパイルした場合に、このエラーが発生することもあります。たとえば、次に示すように、Visual C\+\+ は C\# 宣言と等価になります。  
  
```  
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);  
```  
  
 is  
  
```  
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];  
```  
  
 C2555 の詳細については、サポート技術情報の「BUG: C2555 On Virtual Functions with Covariant Return Types \(Q240862\)」を参照してください。  
  
 次の例では警告 C2555 が生成されます。  
  
```  
// C2555.cpp  
// compile with: /c  
struct X {  
   virtual void func();  
};  
struct Y : X {  
   char func();  // C2555  
   void func2();   // OK  
};  
```