---
title: "数値演算エラー M6111 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: M6111
dev_langs: C++
helpviewer_keywords: M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 204df0df4855fd2628a96ac326dd39c0d65151e5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6111"></a>数値演算エラー M6111
スタック アンダー フロー  
  
 浮動小数点演算では、8087/287/387 コプロセッサまたはエミュレーター スタック アンダー フローが発生しました。  
  
 このエラーの原因への呼び出しでは、多くの場合、`long double`値を返さない関数。 たとえば、次このエラーを生成コンパイルして実行時に。  
  
```  
long double ld() {};  
main ()  
{  
  ld();  
}  
```  
  
 プログラムは、終了コード 139 で終了します。