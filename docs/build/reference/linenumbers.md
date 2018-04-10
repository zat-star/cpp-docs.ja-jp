---
title: -LINENUMBERS |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- /linenumbers
dev_langs:
- C++
helpviewer_keywords:
- LINENUMBERS dumpbin option
- line numbers
- -LINENUMBERS dumpbin option
- /LINENUMBERS dumpbin option
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 745d73cd18cf3430f4588889a665775fe3184cb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linenumbers"></a>/LINENUMBERS
```  
/LINENUMBERS  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、COFF 行番号を表示します。 C7 互換プログラム データベース (/Zi) でコンパイルされた場合に、行番号がオブジェクト ファイルに存在 (/Z7)、または行番号のみ (/Zd)。 実行可能ファイルまたは DLL が含まれています行 coff にはデバッグ情報の生成にリンクされている場合 (/debug)。  
  
 のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションはにより生成されるファイルで使用できるよう、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。  
  
## <a name="see-also"></a>参照  
 [DUMPBIN オプション](../../build/reference/dumpbin-options.md)