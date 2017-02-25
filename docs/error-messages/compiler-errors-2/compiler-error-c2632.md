---
title: "コンパイラ エラー C2632 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2632"
ms.assetid: b15a6b1b-42d2-4e1b-8660-e6bfde61052d
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラ エラー C2632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type1' の後に 'type2' を記述するのは正しくありません。  
  
 このエラーは、2 つの型指定子の間にコードがないと発生する場合があります。  
  
 次の例では警告 C2632 が生成されます。  
  
```  
// C2632.cpp  
int float i;   // C2632  
```  
  
 このエラーは、Visual Studio .NET 2003 で行われたコンパイラ準拠作業の結果として生成されることもあります。  `bool` は正式な型になりました。  以前のバージョンでは、`bool` は typedef であり、その名前で識別子を作成できました。  
  
 次の例では警告 C2632 が生成されます。  
  
```  
// C2632_2.cpp  
// compile with: /LD  
void f(int bool);   // C2632  
```  
  
 このエラーを解決し、Visual Studio .NET 2003 と Visual Studio .NET の両方のバージョンの Visual C\+\+ でコードを有効にするには、識別子名を変更します。