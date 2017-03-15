---
title: "AsyncBase クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "async/Microsoft::WRL::AsyncBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AsyncBase クラス"
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# AsyncBase クラス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Windows ランタイムの非同期ステート マシンを実装します。  
  
## 構文  
  
```  
  
template <  
   typename TComplete,  
   typename TProgress = Details::Nil,  
   AsyncResultType resultType = SingleResult  
>  
class AsyncBase : public AsyncBase< TComplete, Details::Nil, resultType >;  
  
template <  
   typename TComplete,  
   AsyncResultType resultType  
>  
class AsyncBase< TComplete, Details::Nil, resultType > : public Microsoft::WRL::Implements< IAsyncInfo >;  
```  
  
#### パラメーター  
 `TComplete`  
 非同期操作が完了したときに呼び出されるイベント ハンドラー。  
  
 `TProgress`  
 実行中の非同期操作が現在の進行状況を報告すると呼び出されるイベント ハンドラー。  
  
 `resultType`  
 [AsyncResultType](../windows/asyncresulttype-enumeration.md) の列挙値の 1 つがあります。  既定で、SingleResult。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[AsyncBase::AsyncBase コンストラクター](../windows/asyncbase-asyncbase-constructor.md)|AsyncBase クラスのインスタンスを初期化します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[AsyncBase::Cancel メソッド](../Topic/AsyncBase::Cancel%20Method.md)|非同期操作をキャンセルします。|  
|[AsyncBase::Close メソッド](../windows/asyncbase-close-method.md)|非同期操作を閉じます。|  
|[AsyncBase::FireCompletion メソッド](../windows/asyncbase-firecompletion-method.md)|完了したイベント ハンドラーを呼び出すか、内部進行状況のデリゲートをリセットします。|  
|[AsyncBase::FireProgress メソッド](../windows/asyncbase-fireprogress-method.md)|現在の進行状況のイベント ハンドラーが呼び出されます。|  
|[AsyncBase::get\_ErrorCode メソッド](../windows/asyncbase-get-errorcode-method.md)|現在の非同期操作のエラー コードを取得します。|  
|[AsyncBase::get\_Id メソッド](../windows/asyncbase-get-id-method.md)|非同期操作のハンドルを取得します。|  
|[AsyncBase::get\_Status メソッド](../Topic/AsyncBase::get_Status%20Method.md)|非同期操作の状態を示す値を取得します。|  
|[AsyncBase::GetOnComplete メソッド](../windows/asyncbase-getoncomplete-method.md)|指定した変数に現在のイベント ハンドラーのアドレスをコピーします。|  
|[AsyncBase::GetOnProgress メソッド](../windows/asyncbase-getonprogress-method.md)|指定した変数に現在の進行状況のイベント ハンドラーのアドレスをコピーします。|  
|[AsyncBase::put\_Id メソッド](../windows/asyncbase-put-id-method.md)|非同期操作のハンドルを設定します。|  
|[AsyncBase::PutOnComplete メソッド](../windows/asyncbase-putoncomplete-method.md)|指定された値に完了するイベント ハンドラーのアドレスを設定します。|  
|[AsyncBase::PutOnProgress メソッド](../windows/asyncbase-putonprogress-method.md)|指定された値に進行状況のイベント ハンドラーのアドレスを設定します。|  
|[AsyncBase::Start メソッド](../windows/asyncbase-start-method.md)|非同期操作を開始できます。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[AsyncBase::CheckValidStateForDelegateCall メソッド](../windows/asyncbase-checkvalidstatefordelegatecall-method.md)|デリゲートのプロパティが現在の非同期状態で変更できるかどうかをテストします。|  
|[AsyncBase::CheckValidStateForResultsCall メソッド](../windows/asyncbase-checkvalidstateforresultscall-method.md)|非同期操作の結果が現在の非同期状態で収集できるかどうかをテストします。|  
|[AsyncBase::ContinueAsyncOperation メソッド](../Topic/AsyncBase::ContinueAsyncOperation%20Method.md)|非同期操作が処理を続行する必要があるかどうか、または停止する必要があります。|  
|[AsyncBase::CurrentStatus メソッド](../Topic/AsyncBase::CurrentStatus%20Method.md)|現在の非同期操作の状態を取得します。|  
|[AsyncBase::ErrorCode メソッド](../windows/asyncbase-errorcode-method.md)|現在の非同期操作のエラー コードを取得します。|  
|[AsyncBase::OnCancel メソッド](../windows/asyncbase-oncancel-method.md)|派生クラスでオーバーライドされた場合、キャンセル非同期操作。|  
|[AsyncBase::OnClose メソッド](../windows/asyncbase-onclose-method.md)|派生クラスでオーバーライドされた場合、非同期操作を閉じます。|  
|[AsyncBase::OnStart メソッド](../windows/asyncbase-onstart-method.md)|派生クラスでオーバーライドされた場合、開始非同期操作。|  
|[AsyncBase::TryTransitionToCompleted メソッド](../windows/asyncbase-trytransitiontocompleted-method.md)|現在の非同期操作が完了したかどうかを示します。|  
|[AsyncBase::TryTransitionToError メソッド](../windows/asyncbase-trytransitiontoerror-method.md)|指定したエラー コードが内部エラーの状態を変更できるかどうかを示します。|  
  
## 継承階層  
 `AsyncBase`  
  
 `AsyncBase`  
  
## 必要条件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)