---
title: "コンパイラの警告 (レベル 4) C4057 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4057
dev_langs: C++
helpviewer_keywords: C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1c9ef5041d26e2e5a8933a53d4f6f0153c7106cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4057"></a>コンパイラの警告 (レベル 4) C4057
'operator' : 'identifier1' と 'identifier2' で間接参照している基本型が微妙に異なっています  
  
 2 つのポインター式が参照する基本型が異なります。 式は変換されずに使用されます。  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>次のような原因をチェックして問題を解決するには  
  
1.  signed 型と unsigned 型が混在しています。  
  
2.  **short** 型と **long** 型が混在しています。