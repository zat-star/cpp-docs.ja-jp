---
title: "structured_task_group クラス |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
dev_langs:
- C++
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a1817080506150a8a25918988e18b76dd7a04def
ms.contentlocale: ja-jp
ms.lasthandoff: 03/17/2017

---
# <a name="structuredtaskgroup-class"></a>structured_task_group クラス
`structured_task_group` クラスは、並列処理の高度に構造化されたコレクションを表します。 `structured_task_group` オブジェクトを使用して個々の並列タスクを `task_handle` のキューに配置し、それらのタスクが完了するまで待機するか、実行が完了する前にタスク グループを取り消すことができます。取り消すと、実行が開始されていないタスクはすべて中止されます。  
  
## <a name="syntax"></a>構文  
  
```
class structured_task_group;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[structured_task_group の違い](#ctor)|オーバーロードされます。 新しい `structured_task_group` オブジェクトを構築します。|  
|[~ structured_task_group デストラクター](#dtor)|`structured_task_group` オブジェクトを破棄します。 いずれかを呼び出さないことを期待されて、`wait`または`run_and_wait`デストラクターの実行前にオブジェクトのメソッド、デストラクターが実行される場合を除きの結果としてスタック アンワインドは例外のためです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[キャンセル](#cancel)|このタスク グループをルートとする作業のサブツリーを取り消すためのベスト エフォートで実行します。 タスク グループに対してスケジュールされているすべてのタスクがキャンセル推移的に可能な場合です。|  
|[is_canceling](#is_canceling)|呼び出し元にするかどうか、タスク グループが現在取り消し中に通知されます。 これは必ずしもことを示していない、`cancel`にメソッドが呼び出された、`structured_task_group`オブジェクト (を返すには、このメソッドが確実に適用されるなどが`true`)。 大文字と小文字がある可能性があります`structured_task_group`オブジェクトはインライン実行されているし、さらに、タスク グループを処理ツリーにおけるが取り消されました。 これらの場所などの場合にキャンセルはこのフロー前もって判定できる`structured_task_group`オブジェクト、`true`も返されます。|  
|[run](#run)|オーバーロードされます。 タスクがスケジュール、`structured_task_group`オブジェクトです。 呼び出し元の有効期間を管理する、`task_handle`で渡されるオブジェクト、`_Task_handle`パラメーター。 パラメーターを受け取るバージョンで`_Placement`タスクをそのパラメーターで指定された位置での実行に偏って させます。|  
|[run_and_wait](#run_and_wait)|オーバーロードされます。 呼び出し元のコンテキストでのインラインを実行するタスクをスケジュール、`structured_task_group`完全キャンセルのサポートのオブジェクト。 場合、`task_handle`へのパラメーターとして渡されるオブジェクト`run_and_wait`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクトです。 処理されるまで、関数を待機、`structured_task_group`オブジェクトが完了または取り消されました。|  
|[待機](#wait)|処理されるまで待機する、`structured_task_group`が完了するかキャンセルします。|  
  
## <a name="remarks"></a>コメント  
 さまざまな配置の使用状況に関する重大な制限がある、`structured_task_group`パフォーマンスを取得するためにオブジェクト。  
  
-   単一の`structured_task_group`オブジェクトは、複数のスレッドでは使用できません。 すべての操作、`structured_task_group`オブジェクトは、オブジェクトを作成したスレッドによって実行する必要があります。 このルールは、2 つの例外は、メンバー関数`cancel`と`is_canceling`です。 オブジェクトでは、ラムダ式のキャプチャの一覧でされない可能性があり、タスクがキャンセル操作のいずれかを使用していなければ、タスク内で使用します。  
  
-   スケジュールされているすべてのタスク、`structured_task_group`の使用によりオブジェクトがスケジュールされている`task_handle`オブジェクトの有効期間を明示的に管理する必要があります。  
  
-   複数のグループは、絶対に入れ子になった順序でのみ使用可能性があります。 2 つ`structured_task_group`オブジェクトが宣言された、2 つ目 (内部のいずれか) を宣言する必要がありますを除く任意のメソッドの前に消滅させるため`cancel`または`is_canceling`が&1; つ目で呼び出されます (外側のいずれか)。 この状態は複数を宣言するだけの場合の両方に true を保持`structured_task_group`のキューに登録されたタスクの場合と同様に、同じまたは機能的には入れ子になったスコープ内のオブジェクト、`structured_task_group`を使用して、`run`または`run_and_wait`メソッドです。  
  
-   [全般] とは異なり`task_group`クラスのすべての状態、`structured_task_group`クラスは最終的なです。 グループにタスクをキューに登録し、その完了を待機した後、同じグループをもう一度使用可能性があります。  
  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `structured_task_group`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="cancel"></a>キャンセル 

 このタスク グループをルートとする作業のサブツリーを取り消すためのベスト エフォートで実行します。 タスク グループに対してスケジュールされているすべてのタスクがキャンセル推移的に可能な場合です。  
  
```
void cancel();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)します。  
  
##  <a name="is_canceling"></a>is_canceling 

 呼び出し元にするかどうか、タスク グループが現在取り消し中に通知されます。 これは必ずしもことを示していない、`cancel`にメソッドが呼び出された、`structured_task_group`オブジェクト (を返すには、このメソッドが確実に適用されるなどが`true`)。 大文字と小文字がある可能性があります`structured_task_group`オブジェクトはインライン実行されているし、さらに、タスク グループを処理ツリーにおけるが取り消されました。 これらの場所などの場合にキャンセルはこのフロー前もって判定できる`structured_task_group`オブジェクト、`true`も返されます。  
  
```
bool is_canceling();
```  
  
### <a name="return-value"></a>戻り値  
 かどうかを示す値、`structured_task_group`オブジェクトは取り消し中 (または直後にあることが保証)。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)します。  
  
##  <a name="run"></a>実行します。 

 タスクがスケジュール、`structured_task_group`オブジェクトです。 呼び出し元の有効期間を管理する、`task_handle`で渡されるオブジェクト、`_Task_handle`パラメーター。 パラメーターを受け取るバージョンで`_Placement`タスクをそのパラメーターで指定された位置での実行に偏って させます。  
  
```
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 タスク ハンドルの本体は実行に呼び出される関数オブジェクトの型。  
  
 `_Task_handle`  
 スケジュールされている作業へのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任でことに注意してください。 ランタイムは本来はまで存在するか、引き続き、`wait`または`run_and_wait`このメソッドが呼び出された`structured_task_group`オブジェクトです。  
  
 `_Placement`  
 タスクがによって表される位置への参照、`_Task_handle`パラメーターを実行する必要があります。  
  
### <a name="remarks"></a>コメント  
 ランタイムでは、このメソッドに渡す処理関数のコピーを作成します。 このメソッドに渡された関数オブジェクトで発生した状態の変更は、その関数のオブジェクトのコピーには表示されません。  
  
 場合、 `structured_task_group` destructs スタックの例外からのアンワインド操作の結果として、する必要はありません、呼び出しが行われたいずれかにことを保証するために、`wait`または`run_and_wait`メソッドです。 この場合、デストラクターが適切に取り消されで表されるタスクの待機、`_Task_handle`パラメーターを完了します。  
  
 スロー、 [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md)タスク処理する場合に例外によって指定された、`_Task_handle`を使用してタスク グループ オブジェクトにパラメーターが既にスケジュール、`run`メソッドが行われていない中間の呼び出しと、`wait`または`run_and_wait`メソッドをそのタスクのグループです。  
  
##  <a name="run_and_wait"></a>run_and_wait 

 呼び出し元のコンテキストでのインラインを実行するタスクをスケジュール、`structured_task_group`完全キャンセルのサポートのオブジェクト。 場合、`task_handle`へのパラメーターとして渡されるオブジェクト`run_and_wait`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクトです。 処理されるまで、関数を待機、`structured_task_group`オブジェクトが完了または取り消されました。  
  
```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 タスクを実行するときに呼び出される関数オブジェクトの型。  
  
 `_Task_handle`  
 インライン呼び出し元のコンテキストで実行するタスクへのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任でことに注意してください。 ランタイムは本来はまで、引き続き、`run_and_wait`メソッドが実行を終了します。  
  
 `_Func`  
 作業の本体を呼び出すために呼び出される関数。 これは、ラムダまたはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクト`void operator()()`します。  
  
### <a name="return-value"></a>戻り値  
 待機が満たされているかどうかを示す値、またはタスク グループは、明示的なキャンセル操作、またはそのタスクのいずれかからスローされる例外により取り消されました。 詳細については、次を参照してください[task_group_status。](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>コメント  
 次のようにスケジュールされたタスクの&1; つ以上に注意してください`structured_task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する可能性があります。  
  
 次のようにスケジュールされたタスクの&1; 人以上`structured_task_group`オブジェクト、例外をスローする、ランタイムは、選択した場合のような例外が&1; つを選択しへの呼び出しから伝達、`run_and_wait`メソッドです。  
  
 この関数が返された後に、`structured_task_group`オブジェクトは最終的な状態と見なされます、使わないでください。 その後の使用率に注意してください、`run_and_wait`メソッドが戻る未定義の動作が発生します。  
  
 実行の例外的ではないパスにこのいずれかのメソッドを呼び出す必要がある場合、または`wait`メソッドのデストラクターの前に、`structured_task_group`を実行します。  
  
##  <a name="ctor"></a>structured_task_group の違い 

 新しい `structured_task_group` オブジェクトを構築します。  
  
```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```  
  
### <a name="parameters"></a>パラメーター  
 `_CancellationToken`  
 この構造化タスク グループに関連付けるキャンセル トークン。 トークンが取り消されたときに、構造化タスク グループが取り消されます。  
  
### <a name="remarks"></a>コメント  
 キャンセル トークンを受け取るコンス トラクターを作成、`structured_task_group`をトークンに関連付けられているソースが取り消されたときに取り消されます。 明示的なキャンセル トークンを提供すると、別のトークンまたはトークンを設定せずに親グループからの暗黙的な取り消しに参加するには、この構造化タスク グループが分離されます。  
  
##  <a name="dtor"></a>~ structured_task_group の違い 

 `structured_task_group` オブジェクトを破棄します。 いずれかを呼び出さないことを期待されて、`wait`または`run_and_wait`デストラクターの実行前にオブジェクトのメソッド、デストラクターが実行される場合を除きの結果としてスタック アンワインドは例外のためです。  
  
```
~structured_task_group();
```  
  
### <a name="remarks"></a>コメント  
 通常の実行 (たとえば、いないスタック アンワインドは例外のため) とも、結果として、デストラクターが実行する場合、`wait`も`run_and_wait`メソッドが呼び出されて、デストラクターがスローする可能性が、 [missing_wait](missing-wait-class.md)例外です。  
  
##  <a name="wait"></a>待機 

 処理されるまで待機する、`structured_task_group`が完了するかキャンセルします。  
  
```
task_group_status wait();
```  
  
### <a name="return-value"></a>戻り値  
 待機が満たされているかどうかを示す値、またはタスク グループは、明示的なキャンセル操作、またはそのタスクのいずれかからスローされる例外により取り消されました。 詳細については、次を参照してください[task_group_status。](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>コメント  
 次のようにスケジュールされたタスクの&1; つ以上に注意してください`structured_task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する可能性があります。  
  
 次のようにスケジュールされたタスクの&1; 人以上`structured_task_group`オブジェクト、例外をスローする、ランタイムは、選択した場合のような例外が&1; つを選択しへの呼び出しから伝達、`wait`メソッドです。  
  
 この関数が返された後に、`structured_task_group`オブジェクトは最終的な状態と見なされます、使わないでください。 その後の使用率に注意してください、`wait`メソッドが戻る未定義の動作が発生します。  
  
 実行の例外的ではないパスにこのいずれかのメソッドを呼び出す必要がある場合、または`run_and_wait`メソッドのデストラクターの前に、`structured_task_group`を実行します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [task_group クラス](task-group-class.md)   
 [task_handle クラス](task-handle-class.md)

