---
title: '&lt;iomanip&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iomanip/std::<iomanip>
- std::<iomanip>
- <iomanip>
- std.<iomanip>
dev_langs:
- C++
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 71c6a6f3d9c8c256628f609c6a3e65f6b72df952
ms.lasthandoff: 02/24/2017

---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;
`iostreams` 標準ヘッダー `<iomanip>` をインクルードして、それぞれが単一の引数を受け取る複数のマニピュレーターを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <iomanip>  
  
```  
  
## <a name="remarks"></a>コメント  
 これらの各マニピュレーターは、`basic_istream`\<**Elem**, **Tr**>`::`[operator>>](../standard-library/istream-operators.md#operator_gt__gt_) と `basic_ostream`\<**Elem**, **Tr**>`::`[operator<<](../standard-library/ostream-operators.md#operator_lt__lt_) の両方をオーバーロードする、**T1** から **T10** の未指定の型を返します。  
  
### <a name="manipulators"></a>マニピュレーター  
  
|||  
|-|-|  
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|必要に応じて国際化の形式で、金額を取得します。|  
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|指定された形式を使用して、時間構造体内の時間を取得します。|  
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|必要に応じて国際化の形式で、金額を提供します。|  
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|時間構造体内の時間と、使用する書式設定文字列を提供します。|  
|[quoted](../standard-library/iomanip-functions.md#quoted)|挿入演算子と抽出演算子を使用する文字列の便利なラウンド トリップを有効にします。|  
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|指定したフラグをクリアします。|  
|[setbase](../standard-library/iomanip-functions.md#setbase)|整数の基数を設定します。|  
|[setfill](../standard-library/iomanip-functions.md#setfill)|右揃えの表示でスペースを埋めるために使用する文字を設定します。|  
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|指定したフラグを設定します。|  
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|浮動小数点値の有効桁数を設定します。|  
|[setw](../standard-library/iomanip-functions.md#setw)|表示フィールドの幅を指定します。|  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)




