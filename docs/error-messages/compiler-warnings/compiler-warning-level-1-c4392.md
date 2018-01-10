---
title: "コンパイラの警告 (レベル 1) C4392 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4392
dev_langs: C++
helpviewer_keywords: C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7c33a88ae9dda253192fc6ed4616da52ef7c58c1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4392"></a>コンパイラの警告 (レベル 1) C4392
'signature': 組み込み関数の引数の数が正しくないが 'number' 引数が必要です  
  
 コンパイラ組み込み関数の関数宣言には、間違った数の引数が必要があります。 結果のイメージは正しく動作しない可能性があります。  
  
 この警告を解決するか、宣言を修正してまたは宣言を削除し、単に #include 適切なヘッダー ファイルです。  
  
 次の例では、C4392 が生成されます。  
  
```  
// C4392.cpp  
// compile with: /W1  
// processor: x86  
// uncomment the following line and delete the line that  
// generated the warning to resolve  
// #include "xmmintrin.h"  
  
#ifdef  __cplusplus  
extern "C" {  
#endif  
  
extern void _mm_stream_pd(double *dp);   // C4392  
  
#ifdef  __cplusplus  
}  
#endif  
  
int main()  
{  
}  
```