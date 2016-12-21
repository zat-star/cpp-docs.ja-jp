---
title: "CSnapInPropertyPageImpl クラス | Microsoft Docs"
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
  - "CSnapInPropertyPageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSnapInPropertyPageImpl クラス"
  - "プロパティ ページ, ATL"
  - "スナップイン"
  - "スナップイン, プロパティ ページ"
ms.assetid: 75bdce5a-985e-4166-bd44-493132e023c4
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSnapInPropertyPageImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

このクラスには、スナップイン プロパティ ページ オブジェクトを実装するためのメソッドが用意されています。  
  
> [!IMPORTANT]
>  このクラスおよびメンバーは、Windows のランタイムで実行するアプリケーションで使用することはできません。  
  
## 構文  
  
```  
  
CSnapInPropertyPageImpl : public CDialogImplBase  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CSnapInPropertyPageImpl::CSnapInPropertyPageImpl](../Topic/CSnapInPropertyPageImpl::CSnapInPropertyPageImpl.md)|コンストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CSnapInPropertyPageImpl::CancelToClose](../Topic/CSnapInPropertyPageImpl::CancelToClose.md)|**OK** と **\[キャンセル\]** のボタンの状態が変更されます。|  
|[CSnapInPropertyPageImpl::Create](../Topic/CSnapInPropertyPageImpl::Create.md)|`CSnapInPropertyPageImpl` の新しく作成されたオブジェクトを初期化します。|  
|[CSnapInPropertyPageImpl::OnApply](../Topic/CSnapInPropertyPageImpl::OnApply.md)|ウィザード型のプロパティ シートを使用して中にユーザーが **今すぐ適用する** のボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnHelp](../Topic/CSnapInPropertyPageImpl::OnHelp.md)|ウィザード型のプロパティ シートを使用して中にユーザーが **\[ヘルプ\]** のボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnKillActive](../Topic/CSnapInPropertyPageImpl::OnKillActive.md)|現在のページがアクティブでない場合にフレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnQueryCancel](../Topic/CSnapInPropertyPageImpl::OnQueryCancel.md)|ユーザーが **\[キャンセル\]** のボタンをクリックしたときに、キャンセルが発生する前に、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnReset](../Topic/CSnapInPropertyPageImpl::OnReset.md)|ウィザード型のプロパティ シートを使用して中にユーザーが **\[リセット\]** のボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnSetActive](../Topic/CSnapInPropertyPageImpl::OnSetActive.md)|現在のページがアクティブになるときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnWizardBack](../Topic/CSnapInPropertyPageImpl::OnWizardBack.md)|ウィザード型のプロパティ シートを使用して中にユーザーが**Back** のボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnWizardFinish](../Topic/CSnapInPropertyPageImpl::OnWizardFinish.md)|ウィザード型のプロパティ シートを使用して中にユーザーが **\[完了\]** のボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::OnWizardNext](../Topic/CSnapInPropertyPageImpl::OnWizardNext.md)|ウィザード型のプロパティ シートを使用して中にユーザーが `Next` のボタンをクリックしたときに、フレームワークによって呼び出されます。|  
|[CSnapInPropertyPageImpl::QuerySiblings](../Topic/CSnapInPropertyPageImpl::QuerySiblings.md)|プロパティ シートのすべてのページに現在のメッセージを転送します。|  
|[CSnapInPropertyPageImpl::SetModified](../Topic/CSnapInPropertyPageImpl::SetModified.md)|**今すぐ適用する** のボタンをアクティブ化または非アクティブ化します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CSnapInPropertyPageImpl::m\_psp](../Topic/CSnapInPropertyPageImpl::m_psp.md)|`CSnapInPropertyPageImpl` のオブジェクトで使用される Windows の構造 **PROPSHEETPAGE**。|  
  
## 解説  
 `CSnapInPropertyPageImpl` には、スナップイン プロパティ ページ オブジェクトに基本実装を提供します。  スナップイン プロパティ ページの基本的な機能には、複数のインターフェイスを使用して実装され、型をマップします。  
  
## 継承階層  
 `CDialogImplBase`  
  
 `CSnapInPropertyPageImpl`  
  
## 必要条件  
 **Header:** atlsnap.h  
  
## 参照  
 [クラスの概要](../../atl/atl-class-overview.md)