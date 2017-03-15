---
title: "致命的なエラー C1055 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1055"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1055"
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# 致命的なエラー C1055
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンパイラの制限 : キーが足りません。  
  
 ソース ファイルに含まれるシンボルが多すぎます。  コンパイラはシンボル テーブルのハッシュ キーを使い果たしました。  
  
### 次のような解決策を使用して問題を解決するには  
  
1.  ソース ファイルを小さな複数のファイルに分割します。  
  
2.  不要なヘッダー ファイルを除去します。  
  
3.  変数を新規作成する代わりに、テンポラリ変数やグローバル変数を再利用します。