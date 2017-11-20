---
title: "コンパイラの警告 (レベル 1) C4138 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4138
dev_langs: C++
helpviewer_keywords: C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ae173f0862517d7c8d125cc5cf479b84d6463f46
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4138"></a>コンパイラの警告 (レベル 1) C4138
始まりのデリミターがない閉じのコメントデリミター (*/) が見つかりました。  
  
 終了のコメント区切り記号の前に、開始のコメント区切り記号がありません。 コンパイラでは、アスタリスク (**\***) とスラッシュ (/) との間にスペースが必要です。  
  
## <a name="example"></a>例  
  
```  
// C4138a.cpp  
// compile with: /W1  
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning  
int main()  
{  
}  
```  
  
 この警告は、コメントを入れ子にしようとすると、発生する可能性があります。  
  
 この警告は、コメントを含むコードのセクションをコメント アウトして、 **#if/#endif** ブロックでコードを囲み、制御式を 0 に設定すると、解決する場合があります。  
  
```  
// C4138b.cpp  
// compile with: /W1  
#if 0  
int my_variable;   /* Declaration currently not needed */  
#endif  
int main()  
{  
}  
```