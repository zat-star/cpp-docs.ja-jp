---
title: "コンパイラ エラー C3888 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3888"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3888"
ms.assetid: 40820812-79c5-4dcd-a19d-b4164d25fc8a
caps.latest.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 3
---
# コンパイラ エラー C3888
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'name': このリテラル データ メンバーと関連付けられた const 式は C\+\+\/CLI でサポートされていません  
  
 [literal](../../windows/literal-cpp-component-extensions.md) キーワードを使用して宣言された *name* データ メンバーが、コンパイラがサポートしていない値で初期化されています。 コンパイラは、定数の整数型、列挙型、または文字列型のみをサポートしています。**C3888** エラーの考えられる原因は、データ メンバーがバイト配列で初期化されていることです。  
  
### このエラーを解決するには  
  
1.  宣言されたリテラル データ メンバーがサポートされている型であることを確認します。  
  
## 参照  
 [literal](../../windows/literal-cpp-component-extensions.md)