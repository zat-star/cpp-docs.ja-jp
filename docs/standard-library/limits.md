---
title: '&lt;limits&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- limits/std::<limits>
- <limits>
dev_langs: C++
helpviewer_keywords: limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0e1745dcab769f5a5c81e089b4fba212ab4d6da0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="ltlimitsgt"></a>&lt;limits&gt;
テンプレート クラス `numeric_limits`、および浮動小数点表現と丸め処理に関する 2 種類の列挙体を定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <limits>  
  
```  
  
## <a name="remarks"></a>コメント  
 `numeric_limits` クラスの明示的な特殊化では、文字、整数、浮動小数点型などの基本的な型の多数のプロパティと、C++ 言語の規則で固定されていない、定義された実装である `bool` について記述します。 \<limits> に記述されたプロパティには、精度、表現の最小と最大サイズ、丸め処理、およびシグナリングに関するエラーが含まれます。  
  
### <a name="enumerations"></a>列挙  
  
|||  
|-|-|  
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|この列挙体では、小さすぎて、正規化された値としては表現できない非正規化された浮動小数点値を表現するために、実装で選択できるさまざまなメソッドを記述します。|  
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|この列挙体では、浮動小数点値を整数値に丸めるために、実装で選択できるさまざまなメソッドを記述します。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[numeric_limits クラス](../standard-library/numeric-limits-class.md)|このテンプレート クラスでは、組み込みの数値型の算術プロパティについて記述します。|  
  
## <a name="see-also"></a>参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



