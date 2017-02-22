---
title: "CMFCRibbonEdit クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonEdit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonEdit クラス"
ms.assetid: 9b85f1f2-446b-454e-9af9-104fdad8a897
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CMFCRibbonEdit クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リボン バーに配置されるエディット コントロールを実装します。  
  
## 構文  
  
```  
class CMFCRibbonEdit : public CMFCRibbonButton  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|`CMFCRibbonEdit` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonEdit::CanBeStretched](../Topic/CMFCRibbonEdit::CanBeStretched.md)|`CMFCRibbonEdit` コントロールの高さをリボンの行の高さに合わせて縦方向に拡大するかどうかを指定します。|  
|[CMFCRibbonEdit::CMFCRibbonEdit](../Topic/CMFCRibbonEdit::CMFCRibbonEdit.md)|`CMFCRibbonEdit` オブジェクトを構築します。|  
|[CMFCRibbonEdit::CopyFrom](../Topic/CMFCRibbonEdit::CopyFrom.md)|指定された `CMFCRibbonEdit` オブジェクトの状態を現在の `CMFCRibbonEdit` オブジェクトにコピーします。|  
|[CMFCRibbonEdit::CreateEdit](../Topic/CMFCRibbonEdit::CreateEdit.md)|`CMFCRibbonEdit` オブジェクトのテキスト ボックスを新しく作成します。|  
|[CMFCRibbonEdit::DestroyCtrl](../Topic/CMFCRibbonEdit::DestroyCtrl.md)|`CMFCRibbonEdit` オブジェクトを破棄します。|  
|[CMFCRibbonEdit::DropDownList](../Topic/CMFCRibbonEdit::DropDownList.md)|リスト ボックスをドロップダウンします。|  
|[CMFCRibbonEdit::EnableSpinButtons](../Topic/CMFCRibbonEdit::EnableSpinButtons.md)|テキスト ボックスのスピン ボタンを有効にし、その範囲を設定します。|  
|[CMFCRibbonEdit::GetCompactSize](../Topic/CMFCRibbonEdit::GetCompactSize.md)|`CFMCRibbonEdit` オブジェクトのコンパクト サイズを取得します。|  
|[CMFCRibbonEdit::GetEditText](../Topic/CMFCRibbonEdit::GetEditText.md)|テキスト ボックスのテキストを取得します。|  
|[CMFCRibbonEdit::GetIntermediateSize](../Topic/CMFCRibbonEdit::GetIntermediateSize.md)|`CMFCRibbonEdit` オブジェクトの中間サイズを取得します。|  
|[CMFCRibbonEdit::GetTextAlign](../Topic/CMFCRibbonEdit::GetTextAlign.md)|テキスト ボックスのテキストの配置を取得します。|  
|[CMFCRibbonEdit::GetWidth](../Topic/CMFCRibbonEdit::GetWidth.md)|`CMFCRibbonEdit` コントロールの幅 \(ピクセル単位\) を取得します。|  
|[CMFCRibbonEdit::HasCompactMode](../Topic/CMFCRibbonEdit::HasCompactMode.md)|`CMFCRibbonEdit` コントロールの表示サイズを縮小できるかどうかを示します。|  
|[CMFCRibbonEdit::HasFocus](../Topic/CMFCRibbonEdit::HasFocus.md)|`CMFCRIbbonEdit` コントロールにフォーカスがあるかどうかを示します。|  
|[CMFCRibbonEdit::HasLargeMode](../Topic/CMFCRibbonEdit::HasLargeMode.md)|`CMFCRibbonEdit` コントロールの表示サイズを拡大できるかどうかを示します。|  
|[CMFCRibbonEdit::HasSpinButtons](../Topic/CMFCRibbonEdit::HasSpinButtons.md)|テキスト ボックスにスピン ボタンがあるかどうかを示します。|  
|[CMFCRibbonEdit::IsHighlighted](../Topic/CMFCRibbonEdit::IsHighlighted.md)|`CMFCRibbonEdit` コントロールが強調表示されているかどうかを示します。|  
|[CMFCRibbonEdit::OnAfterChangeRect](../Topic/CMFCRibbonEdit::OnAfterChangeRect.md)|`CMFCRibbonEdit` コントロールを表示する四角形の寸法が変化したときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::OnDraw](../Topic/CMFCRibbonEdit::OnDraw.md)|`CMFCRibbonEdit` コントロールを描画するために、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::OnDrawLabelAndImage](../Topic/CMFCRibbonEdit::OnDrawLabelAndImage.md)|`CMFCRibbonEdit` コントロールのラベルとイメージを描画するために、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::OnDrawOnList](../Topic/CMFCRibbonEdit::OnDrawOnList.md)|コマンド リスト ボックス内の `CMFCRibbonEdit` コントロールを描画するために、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::OnEnable](../Topic/CMFCRibbonEdit::OnEnable.md)|`CMFCRibbonEdit` コントロールを有効または無効にするために、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::OnHighlight](../Topic/CMFCRibbonEdit::OnHighlight.md)|`CMFCRibbonEdit` コントロールの境界をポインターが出入りするときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::OnKey](../Topic/CMFCRibbonEdit::OnKey.md)|ユーザーが KeyTip を押し、`CMFCRibbonEdit` にフォーカスがあるときに、フレームワークによって呼び出されます|  
|[CMFCRibbonEdit::OnLButtonDown](../Topic/CMFCRibbonEdit::OnLButtonDown.md)|フレームワークによって呼び出されます。`CMFCRibbonEdit` コントロール上にマウス ポインターがある間にユーザーがマウスの左ボタンを押したときに、そのコントロールを更新します。|  
|[CMFCRibbonEdit::OnLButtonUp](../Topic/CMFCRibbonEdit::OnLButtonUp.md)|ユーザーがマウスの左ボタンを離したときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::OnRTLChanged](../Topic/CMFCRibbonEdit::OnRTLChanged.md)|フレームワークによって呼び出され、レイアウトの方向が変更されたときに `CMFCRibbonEdit` コントロールを更新します。|  
|[CMFCRibbonEdit::OnShow](../Topic/CMFCRibbonEdit::OnShow.md)|`CMFCRibbonEdit` コントロールの表示と非表示を切り替えるために、フレームワークによって呼び出されます。|  
|[CMFCRibbonEdit::Redraw](../Topic/CMFCRibbonEdit::Redraw.md)|`CMFCRibbonEdit` コントロールの表示を更新します。|  
|[CMFCRibbonEdit::SetACCData](../Topic/CMFCRibbonEdit::SetACCData.md)|`CMFCRibbonEdit` オブジェクトのアクセシビリティ データを設定します。|  
|[CMFCRibbonEdit::SetEditText](../Topic/CMFCRibbonEdit::SetEditText.md)|テキスト ボックスのテキストを設定します。|  
|[CMFCRibbonEdit::SetTextAlign](../Topic/CMFCRibbonEdit::SetTextAlign.md)|テキスト ボックスのテキストの配置を設定します。|  
|[CMFCRibbonEdit::SetWidth](../Topic/CMFCRibbonEdit::SetWidth.md)|`CMFCRibbonEdit` コントロールのテキスト ボックスの幅を設定します。|  
  
## 解説  
  
## 使用例  
 `CMFCRibbonEdit` オブジェクトの構築、編集コントロールの横へのスピンボタンの表示、および編集コントロールのテキストの設定方法を次の例に示します。  このコード スニペットは [MS の Office 2007 のデモのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!CODE [NVC_MFC_MSOffice2007Demo#7](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_MSOffice2007Demo#7)]  
  
## 必要条件  
 **ヘッダー :** afxRibbonEdit.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCRibbonButton クラス](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonBar クラス](../../mfc/reference/cmfcribbonbar-class.md)