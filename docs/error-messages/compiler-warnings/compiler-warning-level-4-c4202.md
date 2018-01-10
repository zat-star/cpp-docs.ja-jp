---
title: "コンパイラの警告 (レベル 4) C4202 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4202
dev_langs: C++
helpviewer_keywords: C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: eee7919cd4b14eb8d307b5fbec986523db29dbf6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4202"></a>コンパイラの警告 (レベル 4) C4202
使用される標準の拡張機能: '…': プロトタイプのパラメーター名 ボックスの一覧が不正です。  
  
 旧スタイルの関数定義には、可変個の引数が含まれています。 これらの定義は、ANSI 互換のエラーを生成 ([/Za](../../build/reference/za-ze-disable-language-extensions.md))。  
  
## <a name="example"></a>例  
  
```  
// C4202.c  
// compile with: /W4  
void func( a, b, ...)   // C4202  
int a, b;  
{}  
  
int main()  
{  
}  
```