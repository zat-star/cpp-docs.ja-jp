---
title: "コンパイラの警告 (レベル 4) C4431 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4431
dev_langs: C++
helpviewer_keywords: C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6594d50cf3688565bc2570ba536ddb908c482f23
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4431"></a>コンパイラの警告 (レベル 4) C4431
型指定子がありません - int と仮定しました。 メモ: C は、現在 int を既定値としてサポートしていません  
  
 このエラーは、Visual C 2005 で行ったコンパイラ準拠作業の結果として生成されることができます。 Visual c 不要になった型指定されていない識別子として int を既定で作成します。 識別子の型を明示的に指定する必要があります。  
  
 既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。  
  
## <a name="example"></a>例  
 次の例では、C4431 を生成します。  
  
```  
// C4431.c  
// compile with: /c /W4  
#pragma warning(default:4431)  
i;   // C4431  
int i;   // OK  
```