---
title: "コンパイラの警告 (レベル 1) C4216 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4216
dev_langs:
- C++
helpviewer_keywords:
- C4216
ms.assetid: 211079dc-59d0-42a7-801c-2ddab21d7232
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e036b27972965aee85c05b987932206d52c030fe
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4216"></a>コンパイラの警告 (レベル 1) C4216
使用される標準の拡張機能: long float  
  
 既定の Microsoft 拡張機能 (/Ze) が扱う**long float**として**二重**です。 ANSI 互換 ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) はありません。 使用して**二重**互換性を維持します。 次の例では、C4216 が生成されます。  
  
```  
// C4216.cpp  
// compile with: /W1  
float long a;   // C4216  
  
// use the line below to resolve the warning  
// double a;  
  
int main() {  
}  
```