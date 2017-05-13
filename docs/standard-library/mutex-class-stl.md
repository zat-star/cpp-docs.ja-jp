---
title: "mutex クラス (C++ 標準ライブラリ)| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::mutex
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
dev_langs:
- C++
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: e08c7c13d1e182bc3299f11769eddb699b03ab3f
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

---
# <a name="mutex-class-c-standard-library"></a>mutex クラス (C++ 標準ライブラリ)
*mutex 型*を表します。 この型のオブジェクトを使用して、プログラム内で相互排他を適用できます。  
  
## <a name="syntax"></a>構文  
  
```
class mutex;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[mutex](#mutex)|`mutex` オブジェクトを構築します。|  
|[mutex::~mutex デストラクター](#dtormutex_destructor)|`mutex` オブジェクトで使用されたすべてのリソースを解放します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[lock](#lock)|呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。|  
|[native_handle](#native_handle)|ミューテックス ハンドルを表す実装固有の型を返します。|  
|[try_lock](#try_lock)|ブロックせずに `mutex` の所有権を取得しようとします。|  
|[unlock](#unlock)|`mutex` の所有権を解放します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<ミュー テックス >  
  
 **名前空間:** std  
  
##  <a name="lock"></a>mutex::lock
 呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。  
  
##  <a name="mutex"></a>  mutex::mutex コンストラクター  
 ロックされていない `mutex` オブジェクトを構築します。  
  
```cpp  
constexpr mutex() noexcept;
```  
  
##  <a name="dtormutex_destructor"></a>  mutex::~mutex デストラクター  
 `mutex` オブジェクトによって使用されているすべてのリソースを解放します。  
  
```cpp  
~mutex();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターの実行時にオブジェクトがロックされる場合の動作は未定義です。  
  
##  <a name="native_handle"></a>mutex::native_handle
 ミューテックス ハンドルを表す実装固有の型を返します。 ミューテックス ハンドルは、実装固有の方法で使用できます。  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>戻り値  
 `native_handle_type` は、`void *` としてキャストされる `Concurrency::critical_section *` と定義されます。  
  
##  <a name="try_lock"></a>mutex::try_lock
 ブロックせずに `mutex` の所有権を取得しようとします。  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが `true` の所有権の取得に成功した場合は `mutex` を返します。それ以外の場合は `false` を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。  
  
##  <a name="unlock"></a>mutex::unlock
 `mutex` の所有権を解放します。  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが `mutex` を所有していない場合の動作は未定義です。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




