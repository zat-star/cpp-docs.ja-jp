---
title: "コンパイラ エラー C2097 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2097
dev_langs: C++
helpviewer_keywords: C2097
ms.assetid: 7e5b2fd4-f61c-4b8a-b265-93e987a04bd3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d6955a610e3109c3b16edf96913be4503ee4c647
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2097"></a>コンパイラ エラー C2097
初期化が正しくありません。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  非定数の値を使用して変数を初期化します。  
  
2.  長いアドレスを持つ short アドレスの初期化。  
  
3.  ローカル構造体、共用体、または非定数の式をコンパイルするときに配列の初期化**/Za**です。  
  
4.  コンマ演算子を含む式で初期化します。  
  
5.  初期化式は定数でもシンボルを定義します。