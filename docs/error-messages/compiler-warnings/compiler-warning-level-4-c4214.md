---
title: "コンパイラの警告 (レベル 4) C4214 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4214
dev_langs: C++
helpviewer_keywords: C4214
ms.assetid: 9b8db279-1f12-4a6b-a923-2db22acd1947
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46df65f9e920eae788088d9e4ec219b6bf93e96f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4214"></a>コンパイラの警告 (レベル 4) C4214
使用される標準の拡張機能: int 型以外のフィールド型のビット  
  
 既定 Microsoft 拡張機能 (/Ze)、任意の整数型のビット フィールドの構造体のメンバーができます。  
  
## <a name="example"></a>例  
  
```  
// C4214.c  
// compile with: /W4  
struct bitfields  
{  
   unsigned short j:4;  // C4214  
};  
  
int main()  
{  
}  
```  
  
 このようなビット フィールドは ANSI 互換では無効 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。