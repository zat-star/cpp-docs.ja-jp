---
title: "ML の致命的なエラー A1007 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1007
dev_langs: C++
helpviewer_keywords: A1007
ms.assetid: bcf9c826-beb3-4e93-91fe-1ffd34995fbf
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 619f1eae458b52eb7851118d6702dccec769a1ca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ml-fatal-error-a1007"></a>ML の致命的なエラー A1007
**入れ子のレベルが深すぎます**  
  
 アセンブラーでは、その入れ子の上限に達しました。 制限は、特に記載のない以外のレベルを 20 です。  
  
 次のいずれかの入れ子が深すぎます。  
  
-   などの高度なディレクティブ[です。IF](../../assembler/masm/dot-if.md)、[です。繰り返し](../../assembler/masm/dot-repeat.md)、または[です。中に](../../assembler/masm/dot-while.md)です。  
  
-   構造体の定義。  
  
-   条件付きアセンブリ ディレクティブです。  
  
-   プロシージャの定義。  
  
-   A [PUSHCONTEXT](../../assembler/masm/pushcontext.md)ディレクティブ (上限は 10)。  
  
-   セグメントの定義。  
  
-   インクルード ファイル。  
  
-   このマクロは。  
  
## <a name="see-also"></a>参照  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)