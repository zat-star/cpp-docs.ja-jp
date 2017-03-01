---
title: "&lt;スレッド&gt;|Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- <thread>
dev_langs:
- C++
ms.assetid: 0c858405-4efb-449d-bf76-70d3693c9234
caps.latest.revision: 18
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
translationtype: Machine Translation
ms.sourcegitcommit: cc82b83860786ffc3f0aee73ede18ecadef16a7a
ms.openlocfilehash: 9b32de86d2ec84017157cccf1a05b9e9b6802e47
ms.lasthandoff: 02/24/2017

---
# <a name="ltthreadgt"></a>&lt;スレッド&gt;
標準ヘッダーを含める\<スレッド > クラスを定義する`thread`やさまざまなサポートする関数。  
  
## <a name="syntax"></a>構文  
  
```cpp  
#include <thread>  
```  
  
## <a name="remarks"></a>コメント  
  
> [!NOTE]
>  使用してコンパイルされたコードで**/clr**、このヘッダーはブロックされます。  
  
 `__STDCPP_THREADS__`スレッドはこのヘッダーでサポートされていることを示すために&0; 以外の値としてマクロを定義します。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-classes"></a>パブリック クラス  
  
|名前|説明|  
|----------|-----------------|  
|[thread クラス](../standard-library/thread-class.md)|観察およびアプリケーションの実行のスレッドを管理するために使用できるオブジェクトを定義します。|  
  
### <a name="public-structures"></a>パブリック構造体  
  
|名前|説明|  
|----------|-----------------|  
|[hash 構造体 (C++ 標準ライブラリ)](../standard-library/hash-structure-stl.md)|によって一意に決定される値を返すメンバー関数の定義、`thread::id`です。 メンバー関数を定義、[ハッシュ](../standard-library/hash-class.md)関数型のマッピングの値に適した`thread::id`インデックス値の分布にします。|  
  
### <a name="public-functions"></a>パブリック関数  
  
|名前|説明|  
|----------|-----------------|  
|[get_id 関数](../standard-library/thread-functions.md#get_id_function)|現在の実行スレッドを一意に識別します。|  
|[sleep_for 関数](../standard-library/thread-functions.md#sleep_for_function)|呼び出し元のスレッドをブロックします。|  
|[sleep_until 関数](../standard-library/thread-functions.md#sleep_until_function)|少なくとも指定された時間まで、呼び出し元スレッドをブロックします。|  
|[swap 関数](../standard-library/thread-functions.md#swap_function)|2 つの状態を交換`thread`オブジェクトです。|  
|[yield 関数](../standard-library/thread-functions.md#yield_function)|現在のスレッドが通常引き続き実行される場合であっても、他のスレッドを実行するようオペレーティング システムに通知します。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[演算子 > = 演算子](../standard-library/thread-operators.md#operator_gt__eq)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以上かどうかを判断します。|  
|[演算子 > 演算子](../standard-library/thread-operators.md#operator_gt_)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より大きいかどうかを判断します。|  
|[演算子<=></=>](../standard-library/thread-operators.md#operator_lt__eq)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値以下かどうかを判断します。|  
|[演算子<>](../standard-library/thread-operators.md#operator_lt_)|一方の `thread::id` オブジェクトの値が、もう一方のオブジェクトの値より小さいかどうかを判断します。|  
|[operator! = 演算子](../standard-library/thread-operators.md#operator_neq)|2 つの `thread::id` オブジェクトが等しくないかどうかを比較します。|  
|[operator = 演算子](../standard-library/thread-operators.md#operator_eq_eq)|2 つの `thread::id` オブジェクトが等しいかどうかを比較します。|  
|[演算子<>](../standard-library/thread-operators.md#operator_lt__lt_)|`thread::id` オブジェクトのテキスト表現をストリームに挿入します。|  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)


