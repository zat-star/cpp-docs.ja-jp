---
title: "recursive_mutex クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_mutex
dev_langs:
- C++
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
caps.latest.revision: 9
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
ms.openlocfilehash: c82c8302be5d3e01de90adda2049a022100b8443
ms.lasthandoff: 02/24/2017

---
# <a name="recursivemutex-class"></a>recursive_mutex クラス
*mutex 型*を表します。 [mutex](../standard-library/mutex-class-stl.md) とは異なり、既にロックされているオブジェクトのロック メソッドを呼び出す動作は詳細に定義されています。  
  
## <a name="syntax"></a>構文  
  
```
class recursive_mutex;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[recursive_mutex コンストラクター](#recursive_mutex__recursive_mutex_constructor)|`recursive_mutex` オブジェクトを構築します。|  
|[~recursive_mutex デストラクター](#recursive_mutex___dtorrecursive_mutex_destructor)|`recursive_mutex` オブジェクトによって使用されるすべてのリソースを解放します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[lock](#recursive_mutex__lock_method)|呼び出しスレッドがミューテックスの所有権を取得するまでそのスレッドをブロックします。|  
|[try_lock](#recursive_mutex__try_lock_method)|ブロックせずにミューテックスの所有権を取得しようとします。|  
|[unlock](#recursive_mutex__unlock_method)|ミューテックスの所有権を解放します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** mutex  
  
 **名前空間:** std  
  
##  <a name="a-namerecursivemutexlockmethoda--lock"></a><a name="recursive_mutex__lock_method"></a>  lock  
 呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが既に `mutex` を所有している場合、メソッドが直ちに返され、以前のロックは有効のままになります。  
  
##  <a name="a-namerecursivemutexrecursivemutexconstructora--recursivemutex"></a><a name="recursive_mutex__recursive_mutex_constructor"></a>  recursive_mutex  
 ロックされていない `recursive_mutex` オブジェクトを構築します。  
  
```cpp  
recursive_mutex();
```  
  
##  <a name="a-namerecursivemutexdtorrecursivemutexdestructora--recursivemutex"></a><a name="recursive_mutex___dtorrecursive_mutex_destructor"></a>  ~recursive_mutex  
 オブジェクトによって使用されるすべてのリソースを解放します。  
  
```cpp  
~recursive_mutex();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターの実行時にオブジェクトがロックされる場合の動作は未定義です。  
  
##  <a name="a-namerecursivemutextrylockmethoda--trylock"></a><a name="recursive_mutex__try_lock_method"></a>  try_lock  
 ブロックせずに `mutex` の所有権を取得しようとします。  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが `mutex` の所有権を正常に取得した場合、または呼び出し元のスレッドがすでに `mutex` を所有している場合は `true`、それ以外の場合は `false` です。  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが既に `mutex` を所有している場合、関数が直ちに `true` を返し、以前のロックは有効のままになります。  
  
##  <a name="a-namerecursivemutexunlockmethoda--unlock"></a><a name="recursive_mutex__unlock_method"></a>  unlock  
 ミューテックスの所有権を解放します。  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドが `mutex` の所有権を開放するのは、[lock](#recursive_mutex__lock_method) および [try_lock](#recursive_mutex__try_lock_method) が `recursive_mutex` オブジェクト上で正常に呼び出されたのと同じ回数だけ呼び出された後のみです。  
  
 呼び出しスレッドが `mutex` を所有していない場合の動作は未定義です。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




