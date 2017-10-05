---
title: "&lt;mutex&gt; 関数および変数 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::adopt_lock
- mutex/std::call_once
- mutex/std::defer_lock
- mutex/std::lock
- mutex/std::try_to_lock
ms.assetid: 78ab3c8b-c7db-4226-ac93-e2e78ff8b964
caps.latest.revision: 11
manager: ghogen
helpviewer_keywords:
- std::adopt_lock [C++]
- std::call_once [C++]
- std::defer_lock [C++]
- std::lock [C++]
- std::try_to_lock [C++]
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: a81d134a4fb49f9123dbed5b4146976d5c676379
ms.contentlocale: ja-jp
ms.lasthandoff: 10/03/2017

---
# <a name="ltmutexgt-functions-and-variables"></a>&lt;mutex&gt; 関数および変数
||||  
|-|-|-|  
|[adopt_lock](#adopt_lock)|[call_once](#call_once)|[defer_lock](#defer_lock)|  
|[lock](#lock)|[try_to_lock](#try_to_lock)|  
  
##  <a name="adopt_lock"></a>  adopt_lock 関数  
 [lock_guard](../standard-library/lock-guard-class.md) と [unique_lock](../standard-library/unique-lock-class.md) のコンストラクターに渡されるオブジェクトを表し、同じコンストラクターに渡されるミューテックス オブジェクトがロックされていることを示します。  
  
```cpp  
const adopt_lock_t adopt_lock;
```  
  
##  <a name="call_once"></a>  call_once  
 指定された呼び出し可能オブジェクトが、実行中に 1 回だけ呼び出されるメカニズムを提供します。  
  
```
template <class Callable, class... Args>
void call_once(once_flag& Flag,
    Callable F&&, Args&&... A);
```  
  
### <a name="parameters"></a>パラメーター  
 `Flag`  
 呼び出し可能オブジェクトが 1 回だけ呼び出されるようにする [once_flag](../standard-library/once-flag-structure.md) オブジェクト。  
  
 `F`  
 呼び出し可能オブジェクト。  
  
 `A`  
 引数リスト。  
  
### <a name="remarks"></a>コメント  
 `Flag` が有効でない場合、関数はエラー コードが `invalid_argument` である [system_error](../standard-library/system-error-class.md) をスローします。 それ以外の場合、テンプレート関数は `Flag` 引数を使用して、テンプレート関数が呼び出される回数に関係なく `F(A...)` が 1 回だけ呼び出されるようにします。 `F(A...)` が例外をスローして終了した場合、呼び出しは失敗です。  
  
##  <a name="defer_lock"></a>  defer_lock 変数  
 [unique_lock](../standard-library/unique-lock-class.md) のコンストラクターに渡すことができるオブジェクトを表します。 これは、コンストラクターに渡される mitex オブジェクトをコンストラクターがロックしてはならないことを示します。  
  
```cpp  
const defer_lock_t defer_lock;
```  
  
##  <a name="lock"></a>  lock  
 デッドロックなしですべての引数をロックしようとします。  
  
```cpp  
template <class L1, class L2, class... L3>
void lock(L1&, L2&, L3&...);
```  
  
### <a name="remarks"></a>コメント  
 このテンプレート関数に対する引数は、例外をスローする可能性がある `try_lock` への呼び出しを除いて、*mutex 型*である必要があります。  
  
 この関数は、`lock`、`try_lock`、および `unlock` への呼び出しによるデッドロックなしで、すべての引数をロックします。 `lock` または `try_lock` の呼び出しで例外がスローされると、この関数は再び例外をスローする前に正常にロックされた mutex オブジェクトのいずれかに `unlock` を呼び出します。  
  
##  <a name="try_to_lock"></a>  try_to_lock 変数  
 [unique_lock](../standard-library/unique-lock-class.md) のコンストラクターに渡すことのできるオブジェクトを表し、ブロックされずに渡される `mutex` をコンストラクターがロック解除しようとしたほうがよいことを示します。  
  
```cpp  
const try_to_lock_t try_to_lock;
```  
  
## <a name="see-also"></a>関連項目  
 [\<mutex>](../standard-library/mutex.md)




