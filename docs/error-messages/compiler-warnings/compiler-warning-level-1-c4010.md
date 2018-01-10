---
title: "コンパイラの警告 (レベル 1) C4010 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4010
dev_langs: C++
helpviewer_keywords: C4010
ms.assetid: d607a9ff-8f8f-45c0-b07b-3b2f439e5485
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a56adb54c4a4b7123bde706a2b6b8bdcb184775
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4010"></a>コンパイラの警告 (レベル 1) C4010
単一行コメントには、行連結文字が含まれています。  
  
 導入された、単一行のコメント//、円記号が含まれています (\\) 行連結文字として機能します。 コンパイラでは、継続タスクを次の行を考慮し、コメントとして扱われます。  
  
 一部の構文向けエディターは、コメントとして連結文字の次の行を示していません。 構文の色分けでこの警告が発生した行を無視します。  
  
 次の例では、C4010 が生成されます。  
  
```  
// C4010.cpp  
// compile with: /WX  
int main() {  
   // the next line is also a comment because of the backslash \  
   int a = 3; // C4010  
   a++;  
}  
```