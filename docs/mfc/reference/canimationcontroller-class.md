---
title: "CAnimationController クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CAnimationController"
  - "afxanimationcontroller/CAnimationController"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAnimationController クラス"
ms.assetid: ed294c98-695e-40a6-b940-33ef1d40aa6b
caps.latest.revision: 18
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAnimationController クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

アニメーションを作成および管理するための中心的なインターフェイスを提供する、アニメーション コントローラーを実装します。  
  
## 構文  
  
```  
class CAnimationController : public CObject;  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CAnimationController::CAnimationController](../Topic/CAnimationController::CAnimationController.md)|アニメーション コントローラーを構築します。|  
|[CAnimationController::~CAnimationController](../Topic/CAnimationController::~CAnimationController.md)|デストラクターです。  アニメーション コントローラー オブジェクトが破棄されるときに呼び出されます。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationController::AddAnimationObject](../Topic/CAnimationController::AddAnimationObject.md)|アニメーション コントローラーに属するグループにアニメーション オブジェクトを追加します。|  
|[CAnimationController::AddKeyframeToGroup](../Topic/CAnimationController::AddKeyframeToGroup.md)|キーフレームをグループに追加します。|  
|[CAnimationController::AnimateGroup](../Topic/CAnimationController::AnimateGroup.md)|グループがアニメーションを実行するように準備します。アニメーションをスケジュールすることもできます。|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|オーバーロードされます。  アニメーションがスケジュールされたときにグループをクリーンアップするために、フレームワークによって呼び出されます。|  
|[CAnimationController::CreateKeyframe](../Topic/CAnimationController::CreateKeyframe.md)|オーバーロードされます。  遷移に依存するキーフレームを作成し、指定したグループに追加します。|  
|[CAnimationController::EnableAnimationManagerEvent](../Topic/CAnimationController::EnableAnimationManagerEvent.md)|アニメーション マネージャーのステータスが変化したときに呼び出すハンドラーを設定または解放します。|  
|[CAnimationController::EnableAnimationTimerEventHandler](../Topic/CAnimationController::EnableAnimationTimerEventHandler.md)|タイミング イベントのハンドラーとタイミング更新のハンドラーを設定または解放します。|  
|[CAnimationController::EnablePriorityComparisonHandler](../Topic/CAnimationController::EnablePriorityComparisonHandler.md)|スケジュール済みのストーリーボードの取り消し、完了、トリム、または圧縮を実行できるかどうかを確認するために呼び出される優先度比較ハンドラーを設定または解放します。|  
|[CAnimationController::EnableStoryboardEventHandler](../Topic/CAnimationController::EnableStoryboardEventHandler.md)|ストーリーボードのステータス イベントと更新イベントのハンドラーを設定または解放します。|  
|[CAnimationController::FindAnimationGroup](../Topic/CAnimationController::FindAnimationGroup.md)|オーバーロードされます。  アニメーション グループをストーリーボードで検索します。|  
|[CAnimationController::FindAnimationObject](../Topic/CAnimationController::FindAnimationObject.md)|指定したアニメーション変数が格納されたアニメーション オブジェクトを検索します。|  
|[CAnimationController::GetKeyframeStoryboardStart](../Topic/CAnimationController::GetKeyframeStoryboardStart.md)|ストーリーボードの先頭を識別するキーフレームを返します。|  
|[CAnimationController::GetUIAnimationManager](../Topic/CAnimationController::GetUIAnimationManager.md)|カプセル化された IUIAnimationManager オブジェクトにアクセスできるようにします。|  
|[CAnimationController::GetUIAnimationTimer](../Topic/CAnimationController::GetUIAnimationTimer.md)|カプセル化された IUIAnimationTimer オブジェクトにアクセスできるようにします。|  
|[CAnimationController::GetUITransitionFactory](../Topic/CAnimationController::GetUITransitionFactory.md)|IUIAnimationTransitionFactory インターフェイスへのポインター。遷移ライブラリの作成に失敗した場合は NULL。|  
|[CAnimationController::GetUITransitionLibrary](../Topic/CAnimationController::GetUITransitionLibrary.md)|カプセル化された IUIAnimationTransitionLibrary オブジェクトにアクセスできるようにします。|  
|[CAnimationController::IsAnimationInProgress](../Topic/CAnimationController::IsAnimationInProgress.md)|少なくとも 1 つのグループでアニメーションが再生されているかどうかを示します。|  
|[CAnimationController::IsValid](../Topic/CAnimationController::IsValid.md)|アニメーション コントローラーが有効かどうかを示します。|  
|[CAnimationController::OnAnimationIntegerValueChanged](../Topic/CAnimationController::OnAnimationIntegerValueChanged.md)|アニメーション変数の整数値が変化したときに、フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationManagerStatusChanged](../Topic/CAnimationController::OnAnimationManagerStatusChanged.md)|アニメーション マネージャーからの StatusChanged イベントに対する応答として、フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationTimerPostUpdate](../Topic/CAnimationController::OnAnimationTimerPostUpdate.md)|アニメーションの更新が完了した後に、フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationTimerPreUpdate](../Topic/CAnimationController::OnAnimationTimerPreUpdate.md)|アニメーションの更新が開始される前に、フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationTimerRenderingTooSlow](../Topic/CAnimationController::OnAnimationTimerRenderingTooSlow.md)|アニメーションのレンダリング フレーム レートが推奨されるフレーム レートの最小値を下回ったときに、フレームワークによって呼び出されます。|  
|[CAnimationController::OnAnimationValueChanged](../Topic/CAnimationController::OnAnimationValueChanged.md)|アニメーション変数の値が変化したときに、フレームワークによって呼び出されます。|  
|[CAnimationController::OnBeforeAnimationStart](../Topic/CAnimationController::OnBeforeAnimationStart.md)|アニメーションがスケジュールされる直前に、フレームワークによって呼び出されます。|  
|[CAnimationController::OnHasPriorityCancel](../Topic/CAnimationController::OnHasPriorityCancel.md)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|  
|[CAnimationController::OnHasPriorityCompress](../Topic/CAnimationController::OnHasPriorityCompress.md)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|  
|[CAnimationController::OnHasPriorityConclude](../Topic/CAnimationController::OnHasPriorityConclude.md)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|  
|[CAnimationController::OnHasPriorityTrim](../Topic/CAnimationController::OnHasPriorityTrim.md)|スケジュールの競合を解決するために、フレームワークによって呼び出されます。|  
|[CAnimationController::OnStoryboardStatusChanged](../Topic/CAnimationController::OnStoryboardStatusChanged.md)|ストーリーボードのステータスが変化したときに、フレームワークによって呼び出されます。|  
|[CAnimationController::OnStoryboardUpdated](../Topic/CAnimationController::OnStoryboardUpdated.md)|ストーリーボードが更新されたときに、フレームワークによって呼び出されます。|  
|[CAnimationController::RemoveAllAnimationGroups](../Topic/CAnimationController::RemoveAllAnimationGroups.md)|アニメーション コントローラーからすべてのアニメーション グループを削除します。|  
|[CAnimationController::RemoveAnimationGroup](../Topic/CAnimationController::RemoveAnimationGroup.md)|指定した ID のアニメーション グループをアニメーション コントローラーから削除します。|  
|[CAnimationController::RemoveAnimationObject](../Topic/CAnimationController::RemoveAnimationObject.md)|アニメーション コントローラーからアニメーション オブジェクトを削除します。|  
|[CAnimationController::RemoveTransitions](../Topic/CAnimationController::RemoveTransitions.md)|指定したグループに属するアニメーション オブジェクトから遷移を削除します。|  
|[CAnimationController::ScheduleGroup](../Topic/CAnimationController::ScheduleGroup.md)|アニメーションをスケジュールします。|  
|[CAnimationController::SetRelatedWnd](../Topic/CAnimationController::SetRelatedWnd.md)|アニメーション コントローラーとウィンドウの関係を確立します。|  
|[CAnimationController::UpdateAnimationManager](../Topic/CAnimationController::UpdateAnimationManager.md)|アニメーション マネージャーに対し、すべてのアニメーション変数の値を更新するように指示します。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CAnimationController::CleanUpGroup](../Topic/CAnimationController::CleanUpGroup.md)|オーバーロードされます。  グループをクリーンアップするヘルパー。|  
|[CAnimationController::OnAfterSchedule](../Topic/CAnimationController::OnAfterSchedule.md)|指定したグループのアニメーションがスケジュールされた直後に、フレームワークによって呼び出されます。|  
  
### プロテクト データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CAnimationController::g\_KeyframeStoryboardStart](../Topic/CAnimationController::g_KeyframeStoryboardStart.md)|ストーリーボードの先頭を表すキーフレーム。|  
|[CAnimationController::m\_bIsValid](../Topic/CAnimationController::m_bIsValid.md)|アニメーション コントローラーが有効かどうかを示します。  現在の OS で Windows Animation API がサポートされていない場合、このメンバーは FALSE に設定されます。|  
|[CAnimationController::m\_lstAnimationGroups](../Topic/CAnimationController::m_lstAnimationGroups.md)|このアニメーション コントローラーに属するアニメーション グループのリスト。|  
|[CAnimationController::m\_pAnimationManager](../Topic/CAnimationController::m_pAnimationManager.md)|アニメーション マネージャー COM オブジェクトへのポインターを格納します。|  
|[CAnimationController::m\_pAnimationTimer](../Topic/CAnimationController::m_pAnimationTimer.md)|アニメーション タイマー COM オブジェクトへのポインターを格納します。|  
|[CAnimationController::m\_pRelatedWnd](../Topic/CAnimationController::m_pRelatedWnd.md)|アニメーション マネージャーのステータスが変化したときまたは更新後のイベントが発生したときに自動的に再描画できる、関連する CWnd オブジェクトへのポインター。  NULL の場合もあります。|  
|[CAnimationController::m\_pTransitionFactory](../Topic/CAnimationController::m_pTransitionFactory.md)|遷移ファクトリ COM オブジェクトへのポインターを格納します。|  
|[CAnimationController::m\_pTransitionLibrary](../Topic/CAnimationController::m_pTransitionLibrary.md)|遷移ライブラリ COM オブジェクトへのポインターを格納します。|  
  
## 解説  
 CAnimationController クラスは、アニメーションを管理する主要なクラスです。  アプリケーションでアニメーション コントローラーのインスタンスを 1 つ以上作成し、必要に応じて CAnimationController::SetRelatedWnd を使用して CWnd オブジェクトに接続できます。  この接続は、アニメーション マネージャーのステータスが変化したとき、またはアニメーション タイマーが更新されたときに、関連するウィンドウに自動的に WM\_PAINT メッセージを送信するために必要です。  この関係を有効にしない場合は、アニメーションを表示するウィンドウを手動で再描画する必要があります。  そのためには、CAnimationController の派生クラスを作成して、OnAnimationManagerStatusChanged または OnAnimationTimerPostUpdate、あるいはその両方をオーバーライドし、必要に応じて 1 つ以上のウィンドウを無効にします。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CAnimationController](../../mfc/reference/canimationcontroller-class.md)  
  
## 必要条件  
 **ヘッダー:** afxanimationcontroller.h  
  
## 参照  
 [クラス](../Topic/MFC%20Classes.md)