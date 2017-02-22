---
title: "コンパイラ エラー C3771 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3771"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3771"
ms.assetid: 68c23b25-7f21-4eaa-8f7e-38fda1130a69
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# コンパイラ エラー C3771
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

"identifier" : フレンド宣言が一番近い名前空間スコープに見つかりませんでした  
  
 指定したテンプレート *identifier* のクラス テンプレート宣言が、現在の名前空間内に見つかりません。  
  
### このエラーを解決するには  
  
-   テンプレート識別子のクラス テンプレート宣言が現在の名前空間で定義されていること、またはテンプレート識別子が完全修飾名であることを確認します。  
  
## 使用例  
 次のコード例では、名前空間 `NA` でクラス テンプレートと関数を宣言しますが、名前空間 `NB` でフレンド関数テンプレートを宣言しようとします。  
  
```  
// C3771.cpp // compile with: /c namespace NA { template<class T> class A { void aFunction(T t) {}; }; } // using namespace NA; namespace NB { class X { template<class T> friend void A<T>::aFunction(T); // C3771 // try the following line instead //      template<class T> friend void NA::A<T>::aFunction(T); // or try "using namespace NA;" instead. }; }  
```  
  
## 参照  
 [テンプレートの仕様](../Topic/Template%20Specifications.md)