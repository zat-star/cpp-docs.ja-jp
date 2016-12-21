---
title: "CVSListBox クラス | Microsoft Docs"
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
  - "CVSListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CVSListBox クラス"
  - "CVSListBox::PreTranslateMessage メソッド"
ms.assetid: c79be7b4-46ed-4af8-a41e-68962782d8ef
caps.latest.revision: 30
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CVSListBox クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CVSListBox` クラスは、編集可能なリスト コントロールをサポートします。  
  
## 構文  
  
```  
class CVSListBox : public CVSListBoxBase  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CVSListBox::CVSListBox](../Topic/CVSListBox::CVSListBox.md)|`CVSListBox` オブジェクトを構築します。|  
|`CVSListBox::~CVSListBox`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CVSListBox::AddItem](../Topic/CVSListBox::AddItem.md)|リスト コントロールに文字列を追加します   \(`CVSListBoxBase::AddItem` をオーバーライドします。\)|  
|[CVSListBox::EditItem](../Topic/CVSListBox::EditItem.md)|リスト コントロール項目のテキストの編集操作を開始します   \(`CVSListBoxBase::EditItem` をオーバーライドします。\)|  
|[CVSListBox::GetCount](../Topic/CVSListBox::GetCount.md)|編集できるリスト コントロールに含まれる文字列の数を取得します   \(`CVSListBoxBase::GetCount` をオーバーライドします。\)|  
|[CVSListBox::GetItemData](../Topic/CVSListBox::GetItemData.md)|編集できるリスト コントロール項目に関連付けられている、アプリケーション固有の 32 ビット値を取得します   \(`CVSListBoxBase::GetItemData` をオーバーライドします。\)|  
|[CVSListBox::GetItemText](../Topic/CVSListBox::GetItemText.md)|編集できるリスト コントロール項目のテキストを取得します   \(`CVSListBoxBase::GetItemText` をオーバーライドします。\)|  
|[CVSListBox::GetSelItem](../Topic/CVSListBox::GetSelItem.md)|編集できるリスト コントロールで現在選択されている項目の 0 から始まるインデックスを取得します   \(`CVSListBoxBase::GetSelItem` をオーバーライドします。\)|  
|`CVSListBox::PreTranslateMessage`|Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) や [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチする前にウィンドウ メッセージを変換します。  詳細とメソッド構文については、「[CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md)」を参照してください。  \(`CVSListBoxBase::PreTranslateMessage` をオーバーライドします\)。|  
|[CVSListBox::RemoveItem](../Topic/CVSListBox::RemoveItem.md)|編集できるリスト コントロールから項目を削除します   \(`CVSListBoxBase::RemoveItem` をオーバーライドします。\)|  
|[CVSListBox::SelectItem](../Topic/CVSListBox::SelectItem.md)|編集できるリスト コントロールの文字列を選択します   \(`CVSListBoxBase::SelectItem` をオーバーライドします。\)|  
|[CVSListBox::SetItemData](../Topic/CVSListBox::SetItemData.md)|アプリケーション固有の 32 ビット値を、編集できるリスト コントロール項目に関連付けます。  \(`CVSListBoxBase::SetItemData` をオーバーライドします。\)|  
  
### プロテクト メソッド  
  
|名前|説明|  
|--------|--------|  
|[CVSListBox::GetListHwnd](../Topic/CVSListBox::GetListHwnd.md)|現在の埋め込みリスト ビュー コントロールのハンドルを返します。|  
  
## 解説  
 `CVSListBox` クラスは、編集ボタンのセットを提供します。このセットを使用して、ユーザーはリスト コントロールの項目を作成、変更、削除、または配置変更できます。  
  
 編集可能なリスト コントロールの画像を次に示します。  2 番目のリスト エントリ \("Item2"\) が編集用に選択されています。  
  
 ![CVSListBox コントロール](../../mfc/reference/media/cvslistbox.png "cvslistbox")  
  
 リソース エディターを使用して編集可能なリスト コントロールを追加すると、エディターの **\[ツールボックス\]** ウィンドウに定義済みの編集可能なリスト コントロールが表示されなくなります。  これを回避するには、**グループ ボックス** コントロールのようなスタティック コントロールを追加してください。  フレームワークは、スタティック コントロールをプレースホルダーとして使用し、編集可能なリスト コントロールのサイズおよび位置を指定します。  
  
 ダイアログ ボックス テンプレートで編集可能なリスト コントロールを使用するには、ダイアログ ボックス クラスで `CVSListBox` 変数を宣言します。  変数とコントロールとのデータ交換をサポートするには、ダイアログ ボックスの `DoDataExchange` メソッドで `DDX_Control` マクロ エントリを定義します。  既定では、編集可能なリスト コントロールは編集ボタンなしで作成されます。  編集ボタンを有効にするには、継承された [CVSListBoxBase::SetStandardButtons](http://msdn.microsoft.com/ja-jp/129e530f-97e9-42eb-b128-371c2a5686ba) メソッドを使用します。  
  
 詳細については、Samples ディレクトリ、`New Controls` サンプル、Page3.cpp ファイル、および Page3.h ファイルを参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CStatic](../Topic/CStatic%20Class.md)  
  
 `CVSListBoxBase`  
  
 [CVSListBox](../../mfc/reference/cvslistbox-class.md)  
  
## 必要条件  
 **ヘッダー :** afxvslistbox.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)