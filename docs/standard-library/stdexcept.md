---
title: '&lt;stdexcept&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<stdexcept>
- std::<stdexcept>
- <stdexcept>
dev_langs:
- C++
helpviewer_keywords:
- stdexcept header
ms.assetid: 495c10b1-1e60-4514-9f8f-7fda11a2f522
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: a01f0cf531196d59815eb87f03ee9d8a15574088
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="ltstdexceptgt"></a>&lt;stdexcept&gt;
例外の通知に使用する複数の標準クラスを定義します。 このクラスは、[exception](../standard-library/exception-class.md) クラスから派生したものからなる派生階層を形成します。このクラスには、論理エラーと実行時エラーという&2; 種類の一般的な例外の型が含まれます。 論理エラーはプログラマの誤りが原因で発生します。 これらは、基底クラス logic_error から派生します。  
  
-   `domain_error`  
  
-   `invalid_argument`  
  
-   `length_error`  
  
-   `out_of_range`  
  
 実行時エラーは、ライブラリ関数か実行時のシステムの誤りが原因で発生します。 これらは、基底クラス runtime_error から派生し、次のものが含まれます。  
  
-   `overflow_error`  
  
-   `range_error`  
  
-   `underflow_error`  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[domain_error クラス](../standard-library/domain-error-class.md)|このクラスは、ドメイン エラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|  
|[invalid_argument クラス](../standard-library/invalid-argument-class.md)|このクラスは、無効な引数を通知するためにスローされる例外すべてに対する基底クラスとして機能します。|  
|[length_error クラス](../standard-library/length-error-class.md)|このクラスは、生成を試みたオブジェクトが長すぎて指定できないことを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|  
|[logic_error クラス](../standard-library/logic-error-class.md)|このクラスは、論理的前提条件に対する違反など、プログラムの実行前に検出可能なエラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|  
|[out_of_range クラス](../standard-library/out-of-range-class.md)|このクラスは、有効範囲外の引数を通知するためにスローされる例外すべてに対する基底クラスとして機能します。|  
|[overflow_error クラス](../standard-library/overflow-error-class.md)|このクラスは、算術オーバーフローを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|  
|[range_error クラス](../standard-library/range-error-class.md)|このクラスは、範囲のエラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|  
|[runtime_error クラス](../standard-library/runtime-error-class.md)|このクラスは、プログラムの実行時にのみ検出可能なエラーを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|  
|[underflow_error クラス](../standard-library/underflow-error-class.md)|このクラスは、算術アンダーフローを通知するためにスローされる例外すべてに対する基底クラスとして機能します。|  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)


