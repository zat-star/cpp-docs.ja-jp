---
title: "コンパイラの警告 (レベル 1) C4935 | Microsoft Docs"
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
  - "C4935"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4935"
ms.assetid: a36c56d3-571a-44dd-bb0f-bcc6b020e134
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# コンパイラの警告 (レベル 1) C4935
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アセンブリ アクセス指定子が 'access' から変更されました  
  
 型のアセンブリ表示設定が変更されました。 コンパイラは、最後に見つかった指定子を使用します。 たとえば、事前宣言のアセンブリ表示設定は、クラス定義のアセンブリ表示設定とは異なる場合があります。  
  
 C4935 が発生するのは **\/clr:oldSyntax** を使用した場合だけです。  
  
 次の例では C4935 が生成されます。  
  
```  
// C4935.cpp // compile with: /clr:oldSyntax /W1 /c public __gc public class X {   // C4935 int i; };  
```