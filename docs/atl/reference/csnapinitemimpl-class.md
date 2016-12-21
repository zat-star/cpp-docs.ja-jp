---
title: "CSnapInItemImpl クラス | Microsoft Docs"
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
  - "CSnapInItemImpl"
  - "ATL.CSnapInItemImpl"
  - "ATL::CSnapInItemImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInItemImpl クラス"
  - "スナップイン"
  - "スナップイン, ATL のサポート"
  - "スナップイン, データ項目"
ms.assetid: 52caefbd-9eae-49b0-add2-d55524271aa7
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSnapInItemImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、スナップイン ノード オブジェクトを実装するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
      template <  
class T,  
BOOL bIsExtension= FALSE  
>  
class ATL_NO_VTABLE CSnapInItemImpl :  
public CSnapInItem  
```  
  
#### パラメーター  
 `T`  
 `CSnapInItemImpl`から派生したクラス。  
  
 *bIsExtension*  
 オブジェクトが、スナップイン拡張子である場合**\[真\]** ; それ **FALSE**。  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSnapInItemImpl::CSnapInItemImpl](../Topic/CSnapInItemImpl::CSnapInItemImpl.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSnapInItemImpl::AddMenuItems](../Topic/CSnapInItemImpl::AddMenuItems.md)|コンテキスト メニューにメニュー項目を追加します。|  
|[CSnapInItemImpl::Command](../Topic/CSnapInItemImpl::Command.md)|カスタム メニュー項目が選択されたときにコンソールによって呼び出されます。|  
|[CSnapInItemImpl::CreatePropertyPages](../Topic/CSnapInItemImpl::CreatePropertyPages.md)|スナップインのプロパティ シートにページを追加します。|  
|[CSnapInItemImpl::FillData](../Topic/CSnapInItemImpl::FillData.md)|指定したストリームへのスナップイン オブジェクトのコピーの情報。|  
|[CSnapInItemImpl::GetResultPaneInfo](../Topic/CSnapInItemImpl::GetResultPaneInfo.md)|スナップインの **RESULTDATAITEM** の構造体を取得します。|  
|[CSnapInItemImpl::GetResultViewType](../Topic/CSnapInItemImpl::GetResultViewType.md)|結果ウィンドウで使用されるビューの型が決まります。|  
|[CSnapInItemImpl::GetScopePaneInfo](../Topic/CSnapInItemImpl::GetScopePaneInfo.md)|スナップインの **SCOPEDATAITEM** の構造体を取得します。|  
|[CSnapInItemImpl::Notify](../Topic/CSnapInItemImpl::Notify.md)|ユーザーが実行する処理のスナップインを通知するために、コンソールによって呼び出されます。|  
|[CSnapInItemImpl::QueryPagesFor](../Topic/CSnapInItemImpl::QueryPagesFor.md)|スナップイン ノードがプロパティ ページをサポートするかどうかを確認するために呼び出されます。|  
|[CSnapInItemImpl::SetMenuInsertionFlags](../Topic/CSnapInItemImpl::SetMenuInsertionFlags.md)|スナップイン オブジェクトのメニューのフラグを変更します。|  
|[CSnapInItemImpl::SetToolbarButtonInfo](../Topic/CSnapInItemImpl::SetToolbarButtonInfo.md)|指定されたツール バー ボタンの情報を設定します。|  
|[CSnapInItemImpl::UpdateMenuState](../Topic/CSnapInItemImpl::UpdateMenuState.md)|コンテキスト メニュー項目の状態を更新します。|  
|[CSnapInItemImpl::UpdateToolbarButton](../Topic/CSnapInItemImpl::UpdateToolbarButton.md)|指定されたツール バー ボタンの状態を更新します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CSnapInItemImpl::m\_bstrDisplayName](../Topic/CSnapInItemImpl::m_bstrDisplayName.md)|スナップイン オブジェクトの名前。|  
|[CSnapInItemImpl::m\_resultDataItem](../Topic/CSnapInItemImpl::m_resultDataItem.md)|`CSnapInItemImpl` のオブジェクトで使用される Windows の構造 **RESULTDATAITEM**。|  
|[CSnapInItemImpl::m\_scopeDataItem](../Topic/CSnapInItemImpl::m_scopeDataItem.md)|`CSnapInItemImpl` のオブジェクトで使用される Windows の構造 **SCOPEDATAITEM**。|  
  
## 解説  
 `CSnapInItemImpl` は、メニュー項目とツール バーの追加などのスナップイン ノード オブジェクトの基本実装を提供し、スナップイン ノードのコマンドを適切なハンドラーに転送作用します。  これらの機能には、複数のインターフェイスを使用して実装され、型をマップします。  既定の実装は、派生クラスのインスタンスを確認し、適切なメッセージを転送して正しいインスタンスへのノード オブジェクトに送信される通知を処理します。  
  
## 継承階層  
 `CSnapInItem`  
  
 `CSnapInItemImpl`  
  
## 必要条件  
 **Header:** atlsnap.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)