---
title: "CMFCFontComboBox クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCFontComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCFontComboBox クラス"
  - "CMFCFontComboBox::CompareItem メソッド"
  - "CMFCFontComboBox::DrawItem メソッド"
  - "CMFCFontComboBox::MeasureItem メソッド"
  - "CMFCFontComboBox::PreTranslateMessage メソッド"
ms.assetid: 9a53fb0c-7b45-486d-8187-2a4c723d9fbb
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CMFCFontComboBox クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCFontComboBox` クラスは、フォントの一覧を含むコンボ ボックス コントロールを作成します。  
  
## 構文  
  
```  
class CMFCFontComboBox : public CComboBox  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCFontComboBox::CMFCFontComboBox](../Topic/CMFCFontComboBox::CMFCFontComboBox.md)|`CMFCFontComboBox` オブジェクトを構築します。|  
|`CMFCFontComboBox::~CMFCFontComboBox`|デストラクターです。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|`CMFCFontComboBox::CompareItem`|現在のフォントのコンボ ボックス コントロールの、並べ替えられたリスト ボックスにある新しい項目の相対位置を判定するために、フレームワークによって呼び出されます   \([CComboBox::CompareItem](../Topic/CComboBox::CompareItem.md) をオーバーライドします\)。|  
|`CMFCFontComboBox::DrawItem`|現在のフォントのコンボ ボックス コントロール内の指定された項目を描画するために、フレームワークによって呼び出されます   \([CComboBox::DrawItem](../Topic/CComboBox::DrawItem.md) をオーバーライドします\)。|  
|[CMFCFontComboBox::GetSelFont](../Topic/CMFCFontComboBox::GetSelFont.md)|選択されているフォントに関する情報を取得します。|  
|`CMFCFontComboBox::MeasureItem`|現在のフォントのコンボ ボックス コントロール内のリスト ボックスのサイズを Windows に通知するために、フレームワークによって呼び出されます   \([CComboBox::MeasureItem](../Topic/CComboBox::MeasureItem.md) をオーバーライドします\)。|  
|`CMFCFontComboBox::PreTranslateMessage`|Windows 関数の [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) や [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) にディスパッチする前にウィンドウ メッセージを変換します。  \([CWnd::PreTranslateMessage](../Topic/CWnd::PreTranslateMessage.md) をオーバーライドします\)。|  
|[CMFCFontComboBox::SelectFont](../Topic/CMFCFontComboBox::SelectFont.md)|指定された基準に一致するフォントをフォント コンボ ボックスから選択します。|  
|[CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md)|フォント コンボ ボックスの項目の一覧を初期化します。|  
  
### データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CMFCFontComboBox::m\_bDrawUsingFont](../Topic/CMFCFontComboBox::m_bDrawUsingFont.md)|現在のフォントのコンボ ボックス コントロール内の項目ラベルを描画するために使用するフォントを持つフレームワークに対して示されます。|  
  
## 解説  
 ダイアログ ボックスで `CMFCFontComboBox` オブジェクトを使用するには、`CMFCFontComboBox` 変数をダイアログ ボックス クラスに追加します。  次にダイアログ ボックス クラスの `OnInitDialog` メソッドで [CMFCFontComboBox::Setup](../Topic/CMFCFontComboBox::Setup.md) メソッドを呼び出して、コンボ ボックス コントロール内の項目のリストを初期化します。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CComboBox](../../mfc/reference/ccombobox-class.md)  
  
 [CMFCFontComboBox](../../mfc/reference/cmfcfontcombobox-class.md)  
  
## 必要条件  
 **ヘッダー :** afxfontcombobox.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)   
 [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)