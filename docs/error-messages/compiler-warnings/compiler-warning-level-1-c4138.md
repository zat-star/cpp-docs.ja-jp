---
title: "コンパイラの警告 (レベル 1) C4138 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4138"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4138"
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# コンパイラの警告 (レベル 1) C4138
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

始まりのデリミターがない閉じのコメントデリミター \(\*\/\) が見つかりました。  
  
 終了のコメント区切り記号の前に、開始のコメント区切り記号がありません。 コンパイラでは、アスタリスク \(**\***\) とスラッシュ \(\/\) との間にスペースが必要です。  
  
## 使用例  
  
```  
// C4138a.cpp // compile with: /W1 int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning int main() { }  
```  
  
 この警告は、コメントを入れ子にしようとすると、発生する可能性があります。  
  
 この警告は、コメントを含むコードのセクションをコメント アウトして、**\#if\/\#endif** ブロックでコードを囲み、制御式を 0 に設定すると、解決する場合があります。  
  
```  
// C4138b.cpp // compile with: /W1 #if 0 int my_variable;   /* Declaration currently not needed */ #endif int main() { }  
```