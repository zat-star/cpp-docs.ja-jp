---
title: "マクロ定義内の優先度 |Microsoft ドキュメント"
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
- NMAKE program, precedence in macro definitions
- macros, precedence
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7421ef51c37e3724bdb986321581e6736a62e18b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="precedence-in-macro-definitions"></a>マクロ定義の優先順位
マクロは、複数の定義を持つ、NMAKE は最も高い優先順位の定義を使用します。 次に、最上位から最下位からの優先順位の順序を示します。  
  
1.  コマンドラインで定義されているマクロ  
  
2.  マクロはメイクファイルで定義されているか、ファイルを含める  
  
3.  継承の環境変数マクロ  
  
4.  Tools.ini ファイルで定義されているマクロ  
  
5.  定義済みマクロなど[CC](../build/command-macros-and-options-macros.md)と[AS](../build/command-macros-and-options-macros.md)  
  
 /E を使用して、同じ名前のメイクファイルのマクロをオーバーライドする環境変数から継承されたマクロが発生します。 使用して**!UNDEF**をコマンド ラインをオーバーライドします。  
  
## <a name="see-also"></a>参照  
 [NMAKE マクロの定義](../build/defining-an-nmake-macro.md)