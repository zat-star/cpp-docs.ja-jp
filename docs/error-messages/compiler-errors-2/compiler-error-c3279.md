---
title: "コンパイラ エラー C3279 | Microsoft Docs"
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
  - "C3279"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3279"
ms.assetid: 639afc20-984c-4a95-be35-8bf9409f02d5
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラ エラー C3279
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cli 名前空間で宣言されたクラス テンプレートの明示的なインスタンス生成と同様に、部分的または明示的な特殊化は許可されていません  
  
 `cli` 名前空間は、Microsoft によって定義され、擬似テンプレートが含まれています。 Visual C\+\+ コンパイラでは、この名前空間におけるユーザー定義、部分的、および明示的な特殊化は許可されず、クラス テンプレートの明示的なインスタンス化も許可されません。  
  
 次の例では C3279 が生成されます。  
  
```  
// C3279.cpp // compile with: /clr namespace cli { template <> ref class array<int> {};   // C3279 template <typename T> ref class array<T, 2> {};   // C3279 }  
```