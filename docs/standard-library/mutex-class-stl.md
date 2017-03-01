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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: ff3e7e71c678ffc9bdead79ec56ad94f8e297a16
ms.lasthandoff: 02/24/2017

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
|[mutex::mutex コンストラクター](#mutex__mutex_constructor)|`mutex` オブジェクトを構築します。|  
|[mutex::~mutex デストラクター](#mutex___dtormutex_destructor)|`mutex` オブジェクトで使用されたすべてのリソースを解放します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[mutex::lock メソッド](#mutex__lock_method)|呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。|  
|[mutex::native_handle メソッド](#mutex__native_handle_method)|ミューテックス ハンドルを表す実装固有の型を返します。|  
|[mutex::try_lock メソッド](#mutex__try_lock_method)|ブロックせずに `mutex` の所有権を取得しようとします。|  
|[mutex::unlock メソッド](#mutex__unlock_method)|`mutex` の所有権を解放します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** mutex  
  
 **名前空間:** std  
  
##  <a name="a-namemutexlockmethoda--mutexlock-method"></a><a name="mutex__lock_method"></a>  mutex::lock メソッド  
 呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。  
  
##  <a name="a-namemutexmutexconstructora--mutexmutex-constructor"></a><a name="mutex__mutex_constructor"></a>  mutex::mutex コンストラクター  
 ロックされていない `mutex` オブジェクトを構築します。  
  
```cpp  
constexpr mutex() noexcept;
```  
  
##  <a name="a-namemutexdtormutexdestructora--mutexmutex-destructor"></a><a name="mutex___dtormutex_destructor"></a>  mutex::~mutex デストラクター  
 `mutex` オブジェクトによって使用されているすべてのリソースを解放します。  
  
```cpp  
~mutex();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターの実行時にオブジェクトがロックされる場合の動作は未定義です。  
  
##  <a name="a-namemutexnativehandlemethoda--mutexnativehandle-method"></a><a name="mutex__native_handle_method"></a>  mutex::native_handle メソッド  
 ミューテックス ハンドルを表す実装固有の型を返します。 ミューテックス ハンドルは、実装固有の方法で使用できます。  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>戻り値  
 `native_handle_type` は、`void *` としてキャストされる `Concurrency::critical_section *` と定義されます。  
  
##  <a name="a-namemutextrylockmethoda--mutextrylock-method"></a><a name="mutex__try_lock_method"></a>  mutex::try_lock メソッド  
 ブロックせずに `mutex` の所有権を取得しようとします。  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが `true` の所有権の取得に成功した場合は `mutex` を返します。それ以外の場合は `false` を返します。  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが既に `mutex` を所有している場合の動作は未定義です。  
  
##  <a name="a-namemutexunlockmethoda--mutexunlock-method"></a><a name="mutex__unlock_method"></a>  mutex::unlock メソッド  
 `mutex` の所有権を解放します。  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが `mutex` を所有していない場合の動作は未定義です。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




