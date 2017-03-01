`task_group`クラスが、待機または取り消しできる並列処理のコレクションを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class task_group;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[task_group コンス トラクター](#ctor)|オーバーロードされます。 新しい `task_group` オブジェクトを構築します。|  
|[~ task_group デストラクター](#dtor)|`task_group` オブジェクトを破棄します。 いずれかを呼び出さないことを期待されて、`wait`または`run_and_wait`実行する前に、デストラクター、デストラクターがスタック アンワインドは例外のための結果として実行される場合を除き、オブジェクトのメソッドです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[cancel メソッド](#cancel)|このタスク グループをルートとする作業のサブツリーを取り消すためのベスト エフォートで実行します。 タスク グループに対してスケジュールされているすべてのタスクがキャンセル推移的に可能な場合です。|  
|[is_canceling メソッド](#is_canceling)|呼び出し元にするかどうか、タスク グループが現在取り消し中に通知されます。 これは必ずしもことを示していない、`cancel`にメソッドが呼び出された、`task_group`オブジェクト (を返すには、このメソッドが確実に適用されるなどが`true`)。 大文字と小文字がある可能性があります`task_group`オブジェクトはインライン実行されているし、さらに、タスク グループを処理ツリーにおけるが取り消されました。 これらの場所などの場合にキャンセルはこのフロー前もって判定できる`task_group`オブジェクト、`true`も返されます。|  
|[run メソッド](#run)|オーバーロードされます。 タスクがスケジュール、`task_group`オブジェクトです。 場合、`task_handle`へのパラメーターとして渡されるオブジェクト`run`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクトです。 パラメーターでは、可能性のあるランタイム内でヒープ割り当てとは、関数オブジェクトへの参照を受け取るメソッドのバージョンへの参照を受け取るバージョンを使用するよりも少ないウェルを実行する、`task_handle`オブジェクトです。 パラメーターを受け取るバージョン`_Placement`にタスクをそのパラメーターで指定された位置での実行に偏って させます。|  
|[run_and_wait メソッド](#run_and_wait)|オーバーロードされます。 呼び出し元のコンテキストでのインラインを実行するタスクをスケジュール、`task_group`完全キャンセルのサポートのオブジェクト。 処理されるまで、関数を待機、`task_group`オブジェクトが完了または取り消されました。 場合、`task_handle`へのパラメーターとして渡されるオブジェクト`run_and_wait`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクトです。|  
|[wait メソッド](#wait)|処理されるまで待機する、`task_group`オブジェクトが完了または取り消されました。|  
  
## <a name="remarks"></a>コメント  
 異なり、大きく制限された`structured_task_group`、クラス、`task_group`クラスより一般的な構成要素。 説明する制限のいずれかの必要はありません[structured_task_group](structured-task-group-class.md)します。 `task_group`オブジェクトをスレッド間で使用される安全かつ自由形式の方法で使用される場合があります。 欠点、`task_group`コンス トラクターは、実行があるだけでなく、`structured_task_group`の少量の作業を実行するタスクを作成します。  
  
 詳細については、次を参照してください。[タスクの並列化](../task-parallelism-concurrency-runtime.md)します。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `task_group`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-namecancela-cancel"></a><a name="cancel"></a>キャンセル 

 このタスク グループをルートとする作業のサブツリーを取り消すためのベスト エフォートで実行します。 タスク グループに対してスケジュールされているすべてのタスクがキャンセル推移的に可能な場合です。  
  
```  
void cancel();  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[キャンセル](../cancellation-in-the-ppl.md)します。  
  
##  <a name="a-nameiscancelinga-iscanceling"></a><a name="is_canceling"></a>is_canceling 

 呼び出し元にするかどうか、タスク グループが現在取り消し中に通知されます。 これは必ずしもことを示していない、`cancel`にメソッドが呼び出された、`task_group`オブジェクト (を返すには、このメソッドが確実に適用されるなどが`true`)。 大文字と小文字がある可能性があります`task_group`オブジェクトはインライン実行されているし、さらに、タスク グループを処理ツリーにおけるが取り消されました。 これらの場所などの場合にキャンセルはこのフロー前もって判定できる`task_group`オブジェクト、`true`も返されます。  
  
```  
bool is_canceling();  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかを示す値、`task_group`オブジェクトは取り消し中 (または直後にあることが保証)。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[キャンセル](../cancellation-in-the-ppl.md)します。  
  
##  <a name="a-nameruna-run"></a><a name="run"></a>実行します。 

 タスクがスケジュール、`task_group`オブジェクトです。 場合、`task_handle`へのパラメーターとして渡されるオブジェクト`run`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクトです。 パラメーターでは、可能性のあるランタイム内でヒープ割り当てとは、関数オブジェクトへの参照を受け取るメソッドのバージョンへの参照を受け取るバージョンを使用するよりも少ないウェルを実行する、`task_handle`オブジェクトです。 パラメーターを受け取るバージョン`_Placement`にタスクをそのパラメーターで指定された位置での実行に偏って させます。  
  
```  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func  
);  
  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func,  
   location& _Placement  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle,  
   location& _Placement  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 タスク ハンドルの本体は実行に呼び出される関数オブジェクトの型。  
  
 `_Func`  
 タスクの本体を呼び出すために呼び出される関数。 これは、ラムダ式またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクト`void operator()()`します。  
  
 `_Placement`  
 タスクがによって表される位置への参照、`_Func`パラメーターを実行する必要があります。  
  
 `_Task_handle`  
 スケジュールされている作業へのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任でことに注意してください。 ランタイムは本来はまで存在するか、引き続き、`wait`または`run_and_wait`このメソッドが呼び出された`task_group`オブジェクトです。  
  
### <a name="remarks"></a>コメント  
 ランタイムは、呼び出し元の関数が返された後に可能になり以降の時間に実行する指定された処理関数をスケジュールします。 このメソッドを使用して、 [task_handle](task-handle-class.md)指定された処理関数のコピーを保持するオブジェクト。 そのため、このメソッドに渡すことが関数オブジェクトで発生した状態の変更は、その関数のオブジェクトのコピーには表示されません。 さらに、処理関数が戻るまで、ポインター、または処理関数への参照によって渡された任意のオブジェクトの有効期間が有効なままことを確認します。  
  
 場合、 `task_group` destructs スタックの例外からのアンワインド操作の結果として、する必要はありません、呼び出しが行われたいずれかにことを保証するために、`wait`または`run_and_wait`メソッドです。 この場合、デストラクターが適切に取り消されで表されるタスクの待機、`_Task_handle`パラメーターを完了します。  
  
 メソッドをスロー、 [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md)タスク処理する場合に例外によって指定された、`_Task_handle`を使用してタスク グループ オブジェクトにパラメーターが既にスケジュール、`run`メソッドが行われていない中間の呼び出しと、`wait`または`run_and_wait`メソッドをそのタスクのグループです。  
  
##  <a name="a-namerunandwaita-runandwait"></a><a name="run_and_wait"></a>run_and_wait 

 呼び出し元のコンテキストでのインラインを実行するタスクをスケジュール、`task_group`完全キャンセルのサポートのオブジェクト。 処理されるまで、関数を待機、`task_group`オブジェクトが完了または取り消されました。 場合、`task_handle`へのパラメーターとして渡されるオブジェクト`run_and_wait`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクトです。  
  
```  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   const _Function& _Func  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 呼び出され、タスクの本体は実行が関数オブジェクトの型。  
  
 `_Task_handle`  
 インライン呼び出し元のコンテキストで実行するタスクへのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任でことに注意してください。 ランタイムは本来はまで、引き続き、`run_and_wait`メソッドが実行を終了します。  
  
 `_Func`  
 作業の本体を呼び出すために呼び出される関数。 これは、ラムダ式またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクト`void operator()()`します。  
  
### <a name="return-value"></a>戻り値  
 待機が満たされているかどうかを示す値、またはタスク グループは、明示的なキャンセル操作、またはそのタスクのいずれかからスローされる例外により取り消されました。 詳細については、次を参照してください。 [task_group_status](concurrency-namespace-enums.md#task_group_status)します。  

  
### <a name="remarks"></a>コメント  
 次のようにスケジュールされたタスクの&1; つ以上に注意してください`task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する可能性があります。  
  
 次のようにスケジュールされたタスクの&1; 人以上`task_group`オブジェクト、例外をスローする、ランタイムは、選択した場合のような例外が&1; つを選択しへの呼び出しから伝達、`run_and_wait`メソッドです。  
  
 戻ったとき、`run_and_wait`メソッドを`task_group`オブジェクトのランタイムは、ここで、再利用できるクリーンな状態にオブジェクトをリセットします。 これにより、大文字と小文字が含まれます。 ここで、`task_group`オブジェクトは取り消されました。  
  
 実行の例外的ではないパスにこのいずれかのメソッドを呼び出す必要がある場合、または`wait`メソッドのデストラクターの前に、`task_group`を実行します。  
  
##  <a name="a-namectora-taskgroup"></a><a name="ctor"></a>task_group 

 新しい `task_group` オブジェクトを構築します。  
  
```  
task_group();  
  
task_group(  
   cancellation_token _CancellationToken  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_CancellationToken`  
 このタスク グループに関連付けるキャンセル トークン。 トークンが取り消されたときに、タスク グループが取り消されます。  
  
### <a name="remarks"></a>コメント  
 キャンセル トークンを受け取るコンス トラクターを作成、`task_group`をトークンに関連付けられているソースが取り消されたときに取り消されます。 明示的なキャンセル トークンを提供すると、別のトークンまたはトークンを設定せずに親グループからの暗黙的な取り消しに参加するには、このタスク グループが分離されます。  
  
##  <a name="a-namedtora-taskgroup"></a><a name="dtor"></a>~ task_group 

 `task_group` オブジェクトを破棄します。 いずれかを呼び出さないことを期待されて、`wait`または`run_and_wait`実行する前に、デストラクター、デストラクターがスタック アンワインドは例外のための結果として実行される場合を除き、オブジェクトのメソッドです。  
  
```  
~task_group();  
```  
  
### <a name="remarks"></a>コメント  
 通常の実行 (たとえば、いないスタック アンワインドは例外のため) とも、結果として、デストラクターが実行する場合、`wait`も`run_and_wait`メソッドが呼び出されて、デストラクターがスローする可能性が、 [missing_wait](missing-wait-class.md)例外です。  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>待機 

 処理されるまで待機する、`task_group`オブジェクトが完了または取り消されました。  
  
```  
task_group_status wait();  
```  
  
### <a name="return-value"></a>戻り値  
 待機が満たされているかどうかを示す値、またはタスク グループは、明示的なキャンセル操作、またはそのタスクのいずれかからスローされる例外により取り消されました。 詳細については、次を参照してください。 [task_group_status](concurrency-namespace-enums.md#task_group_status)します。  

  
### <a name="remarks"></a>コメント  
 次のようにスケジュールされたタスクの&1; つ以上に注意してください`task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する可能性があります。  
  
 次のようにスケジュールされたタスクの&1; 人以上`task_group`オブジェクト、例外をスローする、ランタイムは、選択した場合のような例外が&1; つを選択しへの呼び出しから伝達、`wait`メソッドです。  
  
 呼び出す`wait`上、`task_group`オブジェクトは、ここで、再利用できるクリーンな状態にリセットします。 これにより、大文字と小文字が含まれます。 ここで、`task_group`オブジェクトは取り消されました。  
  
 実行の例外的ではないパスにこのいずれかのメソッドを呼び出す必要がある場合、または`run_and_wait`メソッドのデストラクターの前に、`task_group`を実行します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [structured_task_group クラス](structured-task-group-class.md)   
 [task_handle クラス](task-handle-class.md)