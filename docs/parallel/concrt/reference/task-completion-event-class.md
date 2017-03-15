---
title: "task_completion_event クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppltasks/concurrency::task_completion_event
dev_langs:
- C++
helpviewer_keywords:
- task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 2cd3e7381402cc65f3220010a71c969cda1c7e2d
ms.lasthandoff: 02/24/2017

---
# <a name="taskcompletionevent-class"></a>task_completion_event クラス
`task_completion_event` クラスを使用すると、条件が満たされるまで、または外部イベントに応答してタスクを開始するまで、タスクの実行を遅延できます。  
  
## <a name="syntax"></a>構文  
  
```
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `_ResultType`  
 この `task_completion_event` クラスの結果の型。  
  
 `T`  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[task_completion_event コンス トラクター](#ctor)|`task_completion_event` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[set メソッド](#set)|オーバーロードされます。 タスクの完了イベントを設定します。|  
|[set_exception メソッド](#set_exception)|オーバーロードされます。 このイベントに関連付けられているすべてのタスクに例外を反映します。|  
  
## <a name="remarks"></a>コメント  
 タスクを作成するシナリオで、将来のいずれかの時点でタスクが終了し、そのタスクの継続が実行されるようにスケジュールする必要がある場合、タスクの完了イベントから作成されるタスクを使用します。 `task_completion_event` には、作成するタスクと同じ型を含める必要があります。また、その型の値を使用し、タスクの完了イベントで set メソッドを呼び出すと、関連するタスクが完了し、その値が結果としてタスクの継続に渡されます。  
  
 タスクの完了イベントがシグナルを受け取らない場合、そのイベントから作成されたタスクは、イベントが破棄されるときに取り消されます。  
  
 `task_completion_event` は、スマート ポインターのように動作し、値渡しされる必要があります。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `task_completion_event`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>設定 

 タスクの完了イベントを設定します。  
  
```
bool set(_ResultType _Result) const ;

bool set() const ;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Result`  
 このイベントを設定する結果。  
  
### <a name="return-value"></a>戻り値  
 イベントの設定が成功した場合、メソッドは `true` を返します。 イベントが既に設定されている場合は、`false` を返します。  
  
### <a name="remarks"></a>コメント  
 `set` の複数呼び出しまたは同時呼び出しがある場合、最初の呼び出しだけが成功し、その結果 (結果が返される場合) はタスクの完了イベントに格納されます。 その他の set は無視され、メソッドは false を返します。 タスクの完了イベントを設定すると、そのイベントから作成されたすべてのタスクは直ちに完了します。また継続が存在する場合は、その継続がスケジュールされます。 タスクの完了オブジェクトを持つ、`_ResultType`以外の`void`を継続に値を渡します。  
  
##  <a name="a-namesetexceptiona-setexception"></a><a name="set_exception"></a>set_exception 

 このイベントに関連付けられているすべてのタスクに例外を反映します。  
  
```
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```  
  
### <a name="parameters"></a>パラメーター  
 `_E`  
 `_Except`  
 `_ExceptionPtr`  
  
### <a name="return-value"></a>戻り値  
  
##  <a name="a-namectora-taskcompletionevent"></a><a name="ctor"></a>task_completion_event 

 `task_completion_event` オブジェクトを構築します。  
  
```
task_completion_event();
```  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

