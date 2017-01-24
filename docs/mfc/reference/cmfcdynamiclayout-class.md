---
title: "CMFCDynamicLayout クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
caps.latest.revision: 16
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCDynamicLayout クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザーによるウィンドウ サイズの変更時に、ウィンドウのコントロールをどのように移動して、サイズを変更するかを指定します。  
  
## 構文  
  
```  
class CMFCDynamicLayout : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|`CMFCDynamicLayout::CMFCDynamicLayout`|`CMFCDynamicLayout` オブジェクトを構築します。|  
|`CMFCDynamicLayout::~CMFCDynamicLayout`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCDynamicLayout::AddItem](../Topic/CMFCDynamicLayout::AddItem.md)|子ウィンドウ \(通常はコントロール\) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。|  
|[CMFCDynamicLayout::Adjust](../Topic/CMFCDynamicLayout::Adjust.md)|子ウィンドウ \(通常はコントロール\) を、動的レイアウト マネージャーによって制御されているウィンドウのリストに追加します。|  
|[CMFCDynamicLayout::Create](../Topic/CMFCDynamicLayout::Create.md)|ホスト ウィンドウを格納し、検証します。|  
|[CMFCDynamicLayout::GetHostWnd](../Topic/CMFCDynamicLayout::GetHostWnd.md)|ホスト ウィンドウへのポインターを返します。|  
|[CMFCDynamicLayout::GetMinSize](../Topic/CMFCDynamicLayout::GetMinSize.md)|レイアウト調整の下限のウィンドウ サイズを返します。|  
|[CMFCDynamicLayout::GetWindowRect](../Topic/CMFCDynamicLayout::GetWindowRect.md)|ウィンドウの現在のクライアント領域の長方形を取得します。|  
|[CMFCDynamicLayout::HasItem](../Topic/CMFCDynamicLayout::HasItem.md)|子コントロールが動的レイアウトに追加されたかどうかを確認します。|  
|[CMFCDynamicLayout::IsEmpty](../Topic/CMFCDynamicLayout::IsEmpty.md)|動的なレイアウトに子ウィンドウが追加されていないことを確認します。|  
|[CMFCDynamicLayout::LoadResource](../Topic/CMFCDynamicLayout::LoadResource.md)|AFX\_DIALOG\_LAYOUT リソースから動的レイアウトを読み取り、ホスト ウィンドウにそのレイアウトを適用します。|  
|static [CMFCDynamicLayout::MoveHorizontal](../Topic/CMFCDynamicLayout::MoveHorizontal.md)|子コントロールをホストしているウィンドウのサイズがユーザーによって変更されたときに子コントロールを水平方向に移動する量を定義する [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 値を取得します。|  
|static [CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md)|子コントロールをホストしているウィンドウのサイズがユーザーによって変更されたときに子コントロールを水平方向に移動する量を定義する [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 値を取得します。|  
|static [CMFCDynamicLayout::MoveNone](../Topic/CMFCDynamicLayout::MoveNone.md)|垂直方向または水平方向のどちらにも子コントロールを移動しないことを表す [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 値を取得します。|  
|static [CMFCDynamicLayout::MoveVertical](../Topic/CMFCDynamicLayout::MoveVertical.md)|子コントロールをホストしているウィンドウのサイズがユーザーによって変更されたときに子コントロールを垂直方向に移動する量を定義する [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md) 値を取得します。|  
|[CMFCDynamicLayout::SetMinSize](../Topic/CMFCDynamicLayout::SetMinSize.md)|ウィンドウ サイズをレイアウト調整の下限に設定します。|  
|static [CMFCDynamicLayout::SizeHorizontal](../Topic/CMFCDynamicLayout::SizeHorizontal.md)|子コントロールをホストしているウィンドウのサイズがユーザーによって変更されたときに子コントロールの水平方向のサイズを変更する量を定義する [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 値を取得します。|  
|static [CMFCDynamicLayout::SizeHorizontalAndVertical](../Topic/CMFCDynamicLayout::SizeHorizontalAndVertical.md)|子コントロールをホストしているウィンドウのサイズがユーザーによって変更されたときに子コントロールの水平方向のサイズを変更する量を定義する [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 値を取得します。|  
|static [CMFCDynamicLayout::SizeNone](../Topic/CMFCDynamicLayout::SizeNone.md)|子コントロールのサイズに変更がないことを表す [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 値を取得します。|  
|static [CMFCDynamicLayout::SizeVertical](../Topic/CMFCDynamicLayout::SizeVertical.md)|子コントロールをホストしているウィンドウのサイズがユーザーによって変更されたときに子コントロールの垂直方向のサイズを変更する量を定義する [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md) 値を取得します。|  
  
## 入れ子にされた型  
  
|名前|説明|  
|--------|--------|  
|[CMFCDynamicLayout::MoveSettings 構造体](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md)|動的レイアウトでのコントロールの移動データをカプセル化します。|  
|[CMFCDynamicLayout::SizeSettings 構造体](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md)|動的レイアウトでのコントロールのサイズ変更データをカプセル化します。|  
  
## 解説  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## 必要条件  
 **ヘッダー:** afxlayout.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)