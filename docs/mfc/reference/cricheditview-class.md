---
title: "CRichEditView クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRichEditView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRichEditView クラス"
  - "ドキュメント/ビュー アーキテクチャ, リッチ エディット コントロール"
  - "OLE コンテナー, リッチ エディット"
  - "リッチ エディット コントロール, OLE コンテナー"
ms.assetid: bd576b10-4cc0-4050-8f76-e1a0548411e4
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CRichEditView クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[CRichEditDoc](../../mfc/reference/cricheditdoc-class.md) [CRichEditCntrItem](../../mfc/reference/cricheditcntritem-class.md)とともに、MFC のドキュメント ビュー アーキテクチャのコンテキストでリッチ エディット コントロールの機能を提供します。  
  
## 構文  
  
```  
  
class CRichEditView : public CCtrlView  
  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CRichEditView::CRichEditView](../Topic/CRichEditView::CRichEditView.md)|`CRichEditView` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRichEditView::AdjustDialogPosition](../Topic/CRichEditView::AdjustDialogPosition.md)|現在の選択が隠されることにダイアログ ボックスを実行します。|  
|[CRichEditView::CanPaste](../Topic/CRichEditView::CanPaste.md)|クリップボードは豊富な編集ビューに貼り付けることができるデータが含まれているかどうかを示します。|  
|[CRichEditView::DoPaste](../Topic/CRichEditView::DoPaste.md)|このリッチ エディット ビューに OLE アイテムを貼り付けます。|  
|[CRichEditView::FindText](../Topic/CRichEditView::FindText.md)|待機カーソルを開始位置として、指定したテキストを検索します。|  
|[CRichEditView::FindTextSimple](../Topic/CRichEditView::FindTextSimple.md)|指定したテキストを検索します。|  
|[CRichEditView::GetCharFormatSelection](../Topic/CRichEditView::GetCharFormatSelection.md)|現在の選択の文字書式の属性を取得します。|  
|[CRichEditView::GetDocument](../Topic/CRichEditView::GetDocument.md)|関連の [CRichEditDoc](../../mfc/reference/cricheditdoc-class.md)へのポインターを取得します。|  
|[CRichEditView::GetInPlaceActiveItem](../Topic/CRichEditView::GetInPlaceActiveItem.md)|現在リッチ エディット ビューの埋め込み先編集が有効な OLE アイテムを取得します。|  
|[CRichEditView::GetMargins](../Topic/CRichEditView::GetMargins.md)|このリッチ エディット ビューのマージンを取得します。|  
|[CRichEditView::GetPageRect](../Topic/CRichEditView::GetPageRect.md)|このリッチ エディット ビューのページの四角形を取得します。|  
|[CRichEditView::GetPaperSize](../Topic/CRichEditView::GetPaperSize.md)|このリッチ エディット ビューについて、用紙サイズを取得します。|  
|[CRichEditView::GetParaFormatSelection](../Topic/CRichEditView::GetParaFormatSelection.md)|現在の選択の段落の書式属性を取得します。|  
|[CRichEditView::GetPrintRect](../Topic/CRichEditView::GetPrintRect.md)|このリッチ エディット ビューの印刷する四角形を取得します。|  
|[CRichEditView::GetPrintWidth](../Topic/CRichEditView::GetPrintWidth.md)|このリッチ エディット ビューについて出力の幅を取得します。|  
|[CRichEditView::GetRichEditCtrl](../Topic/CRichEditView::GetRichEditCtrl.md)|リッチ エディット コントロールを取得します。|  
|[CRichEditView::GetSelectedItem](../Topic/CRichEditView::GetSelectedItem.md)|リッチ エディット ビューから選択した項目を取得します。|  
|[CRichEditView::GetTextLength](../Topic/CRichEditView::GetTextLength.md)|リッチ エディット ビューのテキストの長さを取得します。|  
|[CRichEditView::GetTextLengthEx](../Topic/CRichEditView::GetTextLengthEx.md)|リッチ エディット ビューの文字数またはバイト数を取得します。  長さを判断するメソッドの配置された現役将官支払い。|  
|[CRichEditView::InsertFileAsObject](../Topic/CRichEditView::InsertFileAsObject.md)|OLE アイテムとしてファイルを挿入します。|  
|[CRichEditView::InsertItem](../Topic/CRichEditView::InsertItem.md)|OLE アイテムとして新しい項目を挿入します。|  
|[CRichEditView::IsRichEditFormat](../Topic/CRichEditView::IsRichEditFormat.md)|クリップボードを編集またはリッチ テキスト形式でデータが含まれているかどうかを示します。|  
|[CRichEditView::OnCharEffect](../Topic/CRichEditView::OnCharEffect.md)|現在の選択の文字書式を切り替えます。|  
|[CRichEditView::OnParaAlign](../Topic/CRichEditView::OnParaAlign.md)|段落の配置を変更します。|  
|[CRichEditView::OnUpdateCharEffect](../Topic/CRichEditView::OnUpdateCharEffect.md)|文字のパブリック メンバー関数のコマンド UI を更新します。|  
|[CRichEditView::OnUpdateParaAlign](../Topic/CRichEditView::OnUpdateParaAlign.md)|段落のパブリック メンバー関数のコマンド UI を更新します。|  
|[CRichEditView::PrintInsideRect](../Topic/CRichEditView::PrintInsideRect.md)|指定された四角形内に指定したテキストの書式を設定します。|  
|[CRichEditView::PrintPage](../Topic/CRichEditView::PrintPage.md)|特定のページ内に指定したテキストの書式を設定します。|  
|[CRichEditView::SetCharFormat](../Topic/CRichEditView::SetCharFormat.md)|現在の選択の文字書式の属性を設定します。|  
|[CRichEditView::SetMargins](../Topic/CRichEditView::SetMargins.md)|このリッチ エディット ビューのマージンを設定します。|  
|[CRichEditView::SetPaperSize](../Topic/CRichEditView::SetPaperSize.md)|このリッチ エディット ビューについて、用紙サイズを設定します。|  
|[CRichEditView::SetParaFormat](../Topic/CRichEditView::SetParaFormat.md)|現在の選択の段落の書式属性を設定します。|  
|[CRichEditView::TextNotFound](../Topic/CRichEditView::TextNotFound.md)|コントロールの内部検索の状態をリセットします。|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CRichEditView::GetClipboardData](../Topic/CRichEditView::GetClipboardData.md)|このリッチ エディット ビューの範囲のクリップボードのオブジェクトを取得します。|  
|[CRichEditView::GetContextMenu](../Topic/CRichEditView::GetContextMenu.md)|コンテキスト メニューをマウスの右ボタンで使用する取得します。|  
|[CRichEditView::IsSelected](../Topic/CRichEditView::IsSelected.md)|特定の OLE アイテムでは、選択されている示します。|  
|[CRichEditView::OnFindNext](../Topic/CRichEditView::OnFindNext.md)|部分文字列の次の出現箇所を検索します。|  
|[CRichEditView::OnInitialUpdate](../Topic/CRichEditView::OnInitialUpdate.md)|これがドキュメントにアタッチするとビューを更新します。|  
|[CRichEditView::OnPasteNativeObject](../Topic/CRichEditView::OnPasteNativeObject.md)|OLE アイテムからネイティブ データを取得します。|  
|[CRichEditView::OnPrinterChanged](../Topic/CRichEditView::OnPrinterChanged.md)|特定のデバイスに印刷の特性を設定します。|  
|[CRichEditView::OnReplaceAll](../Topic/CRichEditView::OnReplaceAll.md)|新しい文字列と指定した文字列のすべての一致を置き換えます。|  
|[CRichEditView::OnReplaceSel](../Topic/CRichEditView::OnReplaceSel.md)|現在の選択を置き換えます。|  
|[CRichEditView::OnTextNotFound](../Topic/CRichEditView::OnTextNotFound.md)|要求されたテキストが見つからないユーザーの通知を処理します。|  
|[CRichEditView::QueryAcceptData](../Topic/CRichEditView::QueryAcceptData.md)|`IDataObject`のデータについて、クエリ表示されます。|  
|[CRichEditView::WrapChanged](../Topic/CRichEditView::WrapChanged.md)|`m_nWordWrap`の値に基づいてこのリッチ エディット ビューができるようにターゲットの出力デバイスを調整します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CRichEditView::m\_nBulletIndent](../Topic/CRichEditView::m_nBulletIndent.md)|箇条書きのリストのインデントの量を示します。|  
|[CRichEditView::m\_nWordWrap](../Topic/CRichEditView::m_nWordWrap.md)|ワード ラップの制約を示します。|  
  
## 解説  
 「リッチ エディット コントロール」はユーザーがテキストを入力し、編集できるウィンドウです。  テキストは、文字と段落書式を割り当て、埋め込み OLE オブジェクトを含めることができます。  リッチ エディット コントロールは、テキストの書式を設定するプログラミング インターフェイスを提供します。  ただし、アプリケーションは書式設定操作をユーザーが使用できるようにするために必要なユーザー インターフェイス コンポーネントを実装する必要があります。  
  
 `CRichEditView` は、テキストに一意のテキストと書式設定を保持します。  `CRichEditDoc` は、ビューにある OLE クライアント項目のリストを保持します。  `CRichEditCntrItem` は OLE クライアント項目へのコンテナー側のアクセスを提供します。  
  
 このの Windows コモン コントロール \(したがって [CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md) と関連クラス\) \/98 Windows 95 および Windows NT 3.51 以降で実行されるプログラムにのみ使用できます。  
  
 MFC アプリケーションの豊富な編集ビューの使用例については、[WORDPAD](../../top/visual-cpp-samples.md) サンプル アプリケーションを参照します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CCtrlView](../../mfc/reference/cctrlview-class.md)  
  
 `CRichEditView`  
  
## 必要条件  
 **Header:** afxrich.h  
  
## 参照  
 [MFC WORDPAD サンプル](../../top/visual-cpp-samples.md)   
 [CCtrlView クラス](../../mfc/reference/cctrlview-class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CRichEditDoc クラス](../../mfc/reference/cricheditdoc-class.md)   
 [CRichEditCntrItem クラス](../../mfc/reference/cricheditcntritem-class.md)