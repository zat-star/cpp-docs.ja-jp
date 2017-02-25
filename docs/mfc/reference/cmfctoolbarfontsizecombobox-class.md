---
title: "CMFCToolBarFontSizeComboBox クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarFontSizeComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarFontSizeComboBox クラス"
ms.assetid: 72e0c44c-6a0e-4194-a71f-ab64e3afb9b5
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CMFCToolBarFontSizeComboBox クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ユーザーがフォント サイズを選択するための、コンボ ボックス コントロールを含むツール バーのボタンです。  
  
## 構文  
  
```  
class CMFCToolBarFontSizeComboBox : public CMFCToolBarComboBoxButton  
```  
  
## メンバー  
  
### プロテクト コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox](../Topic/CMFCToolBarFontSizeComboBox::CMFCToolBarFontSizeComboBox.md)|`CMFCToolBarFontSizeComboBox` オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCToolBarFontSizeComboBox::GetTwipSize](../Topic/CMFCToolBarFontSizeComboBox::GetTwipSize.md)|選択されているフォントのサイズ \(twip 単位\) を返します。|  
|[CMFCToolBarFontSizeComboBox::RebuildFontSizes](../Topic/CMFCToolBarFontSizeComboBox::RebuildFontSizes.md)|コンボ ボックスの一覧に、指定されたフォントに対してサポートされているすべてのフォント サイズを格納します。|  
|[CMFCToolBarFontSizeComboBox::SetTwipSize](../Topic/CMFCToolBarFontSizeComboBox::SetTwipSize.md)|twip 単位でフォント サイズを設定します。|  
  
## 解説  
 `CMFCToolBarFontSizeComboBox` オブジェクトを [CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md) オブジェクトと共に使用すると、ユーザーがフォントおよびフォント サイズを選択できるようになります。  
  
 ツール バーには、フォント コンボ ボックスのボタンと同じように、フォント サイズ コンボ ボックスのボタンを追加できます。  詳細については、「[CMFCToolBarFontComboBox クラス](../../mfc/reference/cmfctoolbarfontcombobox-class.md)」を参照してください。  
  
 `CMFCToolBarFontComboBox` オブジェクトでユーザーが新しいフォントを選択したときに、[CMFCToolBarFontSizeComboBox::RebuildFontSizes](../Topic/CMFCToolBarFontSizeComboBox::RebuildFontSizes.md) メソッドを使用することで、そのフォントのサポートされているサイズをフォント サイズ コンボ ボックスに格納できます。  
  
## 使用例  
 `CMFCToolBarFontSizeComboBox` クラスのさまざまなメソッドを使用して `CMFCToolBarFontSizeComboBox` オブジェクトを構成する方法を次の例に示します。  この例では、テキスト ボックスからのフォント サイズ \(twip 単位\) の取得、指定されたフォントで有効なすべてのサイズのフォント サイズ コンボ ボックスへの格納、およびフォント サイズ \(twip 単位\) の指定の方法を示します。  このコード スニペットは [Word のスペースのサンプル](../../top/visual-cpp-samples.md)の一部です。  
  
 [!code-cpp[NVC_MFC_WordPad#8](../../mfc/reference/codesnippet/CPP/cmfctoolbarfontsizecombobox-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCToolBarButton](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
 [CMFCToolBarComboBoxButton](../Topic/CMFCToolBarComboBoxButton%20Class.md)  
  
 [CMFCToolBarFontSizeComboBox](../../mfc/reference/cmfctoolbarfontsizecombobox-class.md)  
  
## 必要条件  
 **ヘッダー :** afxtoolbarfontcombobox.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCToolBar クラス](../../mfc/reference/cmfctoolbar-class.md)   
 [CMFCToolBarButton クラス](../../mfc/reference/cmfctoolbarbutton-class.md)   
 [CMFCToolBarComboBoxButton クラス](../Topic/CMFCToolBarComboBoxButton%20Class.md)   
 [CMFCFontInfo クラス](../../mfc/reference/cmfcfontinfo-class.md)   
 [CMFCToolBar::ReplaceButton](../Topic/CMFCToolBar::ReplaceButton.md)   
 [チュートリアル: ツール バーへのコントロールの追加](../../mfc/walkthrough-putting-controls-on-toolbars.md)