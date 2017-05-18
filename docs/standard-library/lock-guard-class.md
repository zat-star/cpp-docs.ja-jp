---
title: "lock_guard クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::lock_guard
- mutex/std::lock_guard::lock_guard
dev_langs:
- C++
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 047c7ab9db009bceafe47bb0ae53b876adad81b5
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="lockguard-class"></a>lock_guard クラス
オブジェクトを作成し、そのデストラクタ―が `mutex` のロックを解除するためにインスタンス化できるテンプレートを表します。  
  
## <a name="syntax"></a>構文  
  
```
template <class Mutex>
class lock_guard;
```  
  
## <a name="remarks"></a>コメント  
 テンプレート引数 `Mutex` には *mutex 型*を指定する必要があります。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`lock_guard::mutex_type`|テンプレート引数 `Mutex` のシノニム。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[lock_guard](#lock_guard)|`lock_guard` オブジェクトを構築します。|  
|[lock_guard::~lock_guard デストラクター](#dtorlock_guard_destructor)|コンストラクターに渡された `mutex` をロック解除します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<ミュー テックス >  
  
 **名前空間:** std  
  
##  <a name="lock_guard"></a>  lock_guard::lock_guard コンストラクター  
 `lock_guard` オブジェクトを構築します。  
  
```cpp  
explicit lock_guard(mutex_type& Mtx);

lock_guard(mutex_type& Mtx, adopt_lock_t);
```  
  
### <a name="parameters"></a>パラメーター  
 `Mtx`  
 *mutex 型*オブジェクト。  
  
### <a name="remarks"></a>コメント  
 1 番目のコンストラクターは `lock_guard` 型のオブジェクトを構築し、`Mtx` をロックします。 `Mtx` が再帰的なミューテックスではない場合、このコンストラクターが呼び出されたときにロック解除される必要があります。  
  
 2 番目のコンストラクターは `Mtx` をロックしません。 `Mtx` は、このコンストラクターが呼び出されたときにロックされる必要があります。 このコンストラクターでは例外はスローされません。  
  
##  <a name="dtorlock_guard_destructor"></a>  lock_guard::~lock_guard デストラクター  
 コンストラクターに渡された `mutex` をロック解除します。  
  
```
~lock_guard() noexcept;
```  
  
### <a name="remarks"></a>コメント  
 デストラクターの実行時に `mutex` が存在しない場合の動作は未定義です。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




