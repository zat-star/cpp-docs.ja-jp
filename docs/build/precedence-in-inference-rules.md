---
title: "推論規則の優先順位 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f7374da0541fc66464947af5a7b2ea7ea7b5c1d3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-inference-rules"></a>推論規則の優先順位
推論規則は重複定義されて、NMAKE は最も高い優先順位の定義を使用します。 次に、最上位から最下位までの優先順位の順序を示します。  
  
1.  メイクファイルで定義された推論規則後続の定義では、優先順位があります。  
  
2.  Tools.ini; で定義された推論規則後続の定義では、優先順位があります。  
  
3.  定義済みの推論規則。  
  
## <a name="see-also"></a>参照  
 [推論規則](../build/inference-rules.md)