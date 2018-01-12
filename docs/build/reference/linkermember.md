---
title: "-LINKERMEMBER |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /linkermember
dev_langs: C++
helpviewer_keywords:
- /LINKERMEMBER dumpbin option
- LINKERMEMBER dumpbin option
- -LINKERMEMBER dumpbin option
ms.assetid: c96868c1-d70e-4651-ae36-c55b58b16406
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 86248b226f40da62282d7a8fb4f5847e6e617915
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linkermember"></a>/LINKERMEMBER
```  
/LINKERMEMBER[:{1|2}]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、ライブラリで定義されているパブリック シンボルを表示します。 そのオフセットと共に、オブジェクトの順序で記号を表示する 1 つの引数を指定します。 オフセットと、オブジェクトのインデックス番号を表示する 2 つの引数を指定してシンボルごとにオブジェクトのインデックスと共にのアルファベット順に一覧表示されます。 両方の出力を取得するには、数値の引数を指定せず/LINKERMEMBER を指定します。  
  
 のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションはにより生成されるファイルで使用できるよう、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。  
  
## <a name="see-also"></a>参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)