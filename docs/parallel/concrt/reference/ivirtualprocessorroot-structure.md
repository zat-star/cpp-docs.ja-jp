---
title: "IVirtualProcessorRoot 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IVirtualProcessorRoot
dev_langs:
- C++
helpviewer_keywords:
- IVirtualProcessorRoot structure
ms.assetid: 5ef371b8-9e4f-4fef-bb0d-49099693dd2b
caps.latest.revision: 18
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
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: ca095a249ee0eb9e1393e232ab7957a7060a2002
ms.lasthandoff: 02/24/2017

---
# <a name="ivirtualprocessorroot-structure"></a>IVirtualProcessorRoot 構造体
スレッド プロキシが実行できるハードウェア スレッドの抽象化です。  
  
## <a name="syntax"></a>構文  
  
```
struct IVirtualProcessorRoot : public IExecutionResource;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[Ivirtualprocessorroot::activate メソッド](#activate)|実行コンテキストのインターフェイスに関連付けられたスレッド プロキシと、`pContext`この仮想プロセッサ ルートで実行を開始します。|  
|[Ivirtualprocessorroot::deactivate メソッド](#deactivate)|実行コンテキストのディスパッチを停止するには、この仮想プロセッサ ルートで現在実行中のスレッド プロキシさせます。 スレッド プロキシはへの呼び出しでの実行を再開、`Activate`メソッドです。|  
|[Ivirtualprocessorroot::ensurealltasksvisible メソッド](#ensurealltasksvisible)|システム上のすべてのプロセッサに対して可視になる個々 のディスクのメモリ階層に格納されているデータ。 メソッドが戻る前に、メモリ フェンス全体がすべてのプロセッサで実行されたことになります。|  
|[Ivirtualprocessorroot::getid メソッド](#getid)|仮想プロセッサ ルートの一意の識別子を返します。|  
  
## <a name="remarks"></a>コメント  
 すべての仮想プロセッサ ルートでは、関連付けられた実行リソースを持ちます。 `IVirtualProcessorRoot`インターフェイスから継承、 [IExecutionResource](iexecutionresource-structure.md)インターフェイスです。 複数の仮想プロセッサ ルートは、同じ基になるハードウェア スレッドに対応付けることができます。  
  
 リソース マネージャーでは、仮想プロセッサ ルートのリソースに対する要求への応答内のスケジューラによって与えられます。 スケジューラは、仮想プロセッサ ルートを使用して、実行コンテキストによりアクティブ化して作業を実行することができます。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [IExecutionResource](iexecutionresource-structure.md)  
  
 `IVirtualProcessorRoot`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
##  <a name="a-nameactivatea--ivirtualprocessorrootactivate-method"></a><a name="activate"></a>Ivirtualprocessorroot::activate メソッド  
 実行コンテキストのインターフェイスに関連付けられたスレッド プロキシと、`pContext`この仮想プロセッサ ルートで実行を開始します。  
  
```
virtual void Activate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 この仮想プロセッサ ルートでディスパッチされる実行コンテキストへのインターフェイス。  
  
### <a name="remarks"></a>コメント  
 1 つの実行コンテキストのインターフェイスに関連付けられていない場合、リソース マネージャーは、スレッド プロキシを提供します。`pContext`  
  
 `Activate`リソース マネージャーによって返される新しい仮想プロセッサ ルートで処理の実行を開始するか、スレッド プロキシが非アクティブ化または非アクティブ化しようとする仮想プロセッサ ルートで再開メソッドを使用できます。 参照してください[ivirtualprocessorroot::deactivate](#deactivate)詳細については、非アクティブ化します。 非アクティブ化された仮想プロセッサ ルートのパラメーターを再開するときに`pContext`仮想プロセッサ ルートを非アクティブ化するために使用するパラメーターと同じである必要があります。  
  
 以降の呼び出しのペアは、最初に仮想プロセッサ ルートが有効にされた後`Deactivate`と`Activate`互いに競合する可能性があります。 これは、許容可能なリソース マネージャーへの呼び出しを受信する意味`Activate`を受信する前に、`Deactivate`の本来の呼び出しです。  
  
 仮想プロセッサ ルートを有効にする場合は、この仮想プロセッサ ルートが現在ビジー状態であるをリソース マネージャーが通知します。 スケジューラでは、このルート上で実行する作業を見つけられない場合は、起動する必要の`Deactivate`メソッドの仮想プロセッサ ルートがアイドル状態である旨をリソース マネージャーに通知します。 リソース マネージャーでは、このデータを使用して、分散システムを読み込みます。  
  
 `invalid_argument`場合にスローされますが、引数`pContext`プロパティ値を持つ`NULL`です。  
  
 `invalid_operation`場合にスローされますが、引数`pContext`はこの仮想プロセッサ ルートで最後にディスパッチされた実行コンテキストを表しません。  
  
 仮想プロセッサ ルートをアクティブ化は、基になるハードウェア スレッドのサブスクリプション レベルを&1; ずつ増加します。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。  
  
##  <a name="a-namedeactivatea--ivirtualprocessorrootdeactivate-method"></a><a name="deactivate"></a>Ivirtualprocessorroot::deactivate メソッド  
 実行コンテキストのディスパッチを停止するには、この仮想プロセッサ ルートで現在実行中のスレッド プロキシさせます。 スレッド プロキシはへの呼び出しでの実行を再開、`Activate`メソッドです。  
  
```
virtual bool Deactivate(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 このルートでディスパッチされているコンテキスト。  
  
### <a name="return-value"></a>戻り値  
 ブール値。 値`true`からスレッド プロキシが返されたことを示す、`Deactivate`メソッドへの呼び出しに応答に、`Activate`メソッドです。 値`false`スレッド プロキシがリソース マネージャーで通知イベントに対する応答でメソッドから返されたことを示します。 ユーザー モード スケジュール可能 (UMS) スレッド スケジューラでは、項目がスケジューラの入力候補の一覧に表示し、スケジューラがその処理に必要なことこれを示します。  
  
### <a name="remarks"></a>コメント  
 スケジューラのすべての作業が見つからない場合に仮想プロセッサ ルートの実行を一時的に停止するのにには、このメソッドを使用します。 呼び出し、`Deactivate`メソッド内から送信される必要が、`Dispatch`仮想プロセッサ ルートが最後にアクティブ化された実行コンテキストのメソッドです。 呼び出すスレッド プロキシ言い換えると、`Deactivate`メソッドは、仮想プロセッサ ルートで現在実行中の&1; つである必要があります。 メソッドを呼び出すことで実行されていない仮想プロセッサ ルートでは、未定義の動作になる可能性があります。  
  
 非アクティブ化された仮想プロセッサ ルートをへの呼び出しでウェイク アップは、`Activate`メソッドに渡された同じ引数で、`Deactivate`メソッドです。 呼び出しを確保するため、スケジューラは、`Activate`と`Deactivate`メソッドはペアになってが特定の順序で受信する必要はありません。 リソース マネージャーは、呼び出しを受け取る処理できる、`Activate`メソッドへの呼び出しを受信する前に、`Deactivate`メソッドの改善されました。  
  
 仮想プロセッサ ルートが起動している場合からの戻り値、`Deactivate`メソッドは値`false`、スケジューラを使用して UMS の完了リストを照会する必要があります、`IUMSCompletionList::GetUnblockNotifications`メソッドをその情報に動作し、後で呼び出す、`Deactivate`メソッドを再度します。 これは、手順を繰り返しますとまではこのような`Deactivate`メソッドが値を返します`true`します。  
  
 `invalid_argument`場合にスローされますが、引数`pContext`プロパティ値を持つ`NULL`です。  
  
 `invalid_operation`仮想プロセッサ ルートがアクティブ化されていない場合にスローされるか、引数`pContext`はこの仮想プロセッサ ルートで最後にディスパッチされた実行コンテキストを表しません。  
  
 仮想プロセッサ ルートを非アクティブ化の動作では、1 つで、基になるハードウェア スレッドのサブスクリプション レベルが低くなります。 サブスクリプション レベルの詳細については、次を参照してください。 [iexecutionresource::currentsubscriptionlevel](iexecutionresource-structure.md#currentsubscriptionlevel)します。  
  
##  <a name="a-nameensurealltasksvisiblea--ivirtualprocessorrootensurealltasksvisible-method"></a><a name="ensurealltasksvisible"></a>Ivirtualprocessorroot::ensurealltasksvisible メソッド  
 システム上のすべてのプロセッサに対して可視になる個々 のディスクのメモリ階層に格納されているデータ。 メソッドが戻る前に、メモリ フェンス全体がすべてのプロセッサで実行されたことになります。  
  
```
virtual void EnsureAllTasksVisible(_Inout_ IExecutionContext* pContext) = 0;
```  
  
### <a name="parameters"></a>パラメーター  
 `pContext`  
 この仮想プロセッサ ルートでディスパッチされているコンテキスト。  
  
### <a name="remarks"></a>コメント  
 役立つこのメソッドをスケジューラに新しい作業が追加された仮想プロセッサ ルートの非アクティブ化を同期するときにします。 パフォーマンス向上のため、スケジューラに&1; つのプロセッサで実行中のスレッドによって追加された作業項目が他のすべてのプロセッサにすぐに表示されないことを意味するメモリ バリアを実行することがなく作業項目を追加することもできます。 組み合わせてこのメソッドを使用して、`Deactivate`スケジューラのコレクションで作業項目が存在している間、スケジューラにそのすべての仮想プロセッサが非アクティブいないことを確認できるメソッドのルートです。  
  
 呼び出し、`EnsureAllTasksVisibleThe`メソッド内から送信される必要が、`Dispatch`仮想プロセッサ ルートが最後にアクティブ化された実行コンテキストのメソッドです。 呼び出すスレッド プロキシ言い換えると、`EnsureAllTasksVisible`メソッドは、仮想プロセッサ ルートで現在実行中の&1; つである必要があります。 メソッドを呼び出すことで実行されていない仮想プロセッサ ルートでは、未定義の動作になる可能性があります。  
  
 `invalid_argument`場合にスローされますが、引数`pContext`プロパティ値を持つ`NULL`です。  
  
 `invalid_operation`仮想プロセッサ ルートがアクティブ化されていない場合にスローされるか、引数`pContext`はこの仮想プロセッサ ルートで最後にディスパッチされた実行コンテキストを表しません。  
  
##  <a name="a-namegetida--ivirtualprocessorrootgetid-method"></a><a name="getid"></a>Ivirtualprocessorroot::getid メソッド  
 仮想プロセッサ ルートの一意の識別子を返します。  
  
```
virtual unsigned int GetId() const = 0;
```  
  
### <a name="return-value"></a>戻り値  
 整数の識別子。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)

