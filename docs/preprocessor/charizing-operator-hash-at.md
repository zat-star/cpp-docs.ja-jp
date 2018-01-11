---
title: "演算子文字定数化 (#@) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '#@'
dev_langs: C++
helpviewer_keywords:
- preprocessor, operators
- charizing operator
- '#@ preprocessor operator'
ms.assetid: dee03314-d27c-4063-965c-64756efbef22
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 933e97732462b61919d9e5a1e73f2a72d26ea01b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="charizing-operator-"></a>文字定数化演算子 (#@)
**Microsoft 固有の仕様**  
  
 文字定数化演算子は、マクロの引数でのみ使用できます。 場合 **#@** 仮パラメーターの前に、実際の引数の単一引用符で囲むし、マクロが展開されている場合は、文字として扱わマクロの定義でします。 例:  
  
```  
#define makechar(x)  #@x  
```  
  
 は、次のステートメント  
  
```  
a = makechar(b);  
```  
  
 を次のように展開します  
  
```  
a = 'b';  
```  
  
 単一引用符文字は charizing 演算子では使用できません。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [プリプロセッサ演算子](../preprocessor/preprocessor-operators.md)