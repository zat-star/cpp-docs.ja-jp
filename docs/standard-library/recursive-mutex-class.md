---
title: "recursive_mutex クラス | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_mutex
- mutex/std::recursive_mutex::recursive_mutex
- mutex/std::recursive_mutex::lock
- mutex/std::recursive_mutex::try_lock
- mutex/std::recursive_mutex::unlock
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 0e5fccf4d1c1019d8922ae0676d7f5fe8e8dfd2a
ms.contentlocale: ja-jp
ms.lasthandoff: 04/29/2017

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
|[recursive_mutex](#recursive_mutex)|`recursive_mutex` オブジェクトを構築します。|  
|[~recursive_mutex デストラクター](#dtorrecursive_mutex_destructor)|`recursive_mutex` オブジェクトによって使用されるすべてのリソースを解放します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[lock](#lock)|呼び出しスレッドがミューテックスの所有権を取得するまでそのスレッドをブロックします。|  
|[try_lock](#try_lock)|ブロックせずにミューテックスの所有権を取得しようとします。|  
|[unlock](#unlock)|ミューテックスの所有権を解放します。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** \<ミュー テックス >  
  
 **名前空間:** std  
  
##  <a name="lock"></a>  lock  
 呼び出しスレッドが `mutex` の所有権を取得するまでそのスレッドをブロックします。  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが既に `mutex` を所有している場合、メソッドが直ちに返され、以前のロックは有効のままになります。  
  
##  <a name="recursive_mutex"></a>  recursive_mutex  
 ロックされていない `recursive_mutex` オブジェクトを構築します。  
  
```cpp  
recursive_mutex();
```  
  
##  <a name="dtorrecursive_mutex_destructor"></a>  ~recursive_mutex  
 オブジェクトによって使用されるすべてのリソースを解放します。  
  
```cpp  
~recursive_mutex();
```  
  
### <a name="remarks"></a>コメント  
 デストラクターの実行時にオブジェクトがロックされる場合の動作は未定義です。  
  
##  <a name="try_lock"></a>  try_lock  
 ブロックせずに `mutex` の所有権を取得しようとします。  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>戻り値  
 メソッドが `mutex` の所有権を正常に取得した場合、または呼び出し元のスレッドがすでに `mutex` を所有している場合は `true`、それ以外の場合は `false` です。  
  
### <a name="remarks"></a>コメント  
 呼び出しスレッドが既に `mutex` を所有している場合、関数が直ちに `true` を返し、以前のロックは有効のままになります。  
  
##  <a name="unlock"></a>  unlock  
 ミューテックスの所有権を解放します。  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>コメント  
 このメソッドが `mutex` の所有権を開放するのは、[lock](#lock) および [try_lock](#try_lock) が `recursive_mutex` オブジェクト上で正常に呼び出されたのと同じ回数だけ呼び出された後のみです。  
  
 呼び出しスレッドが `mutex` を所有していない場合の動作は未定義です。  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




