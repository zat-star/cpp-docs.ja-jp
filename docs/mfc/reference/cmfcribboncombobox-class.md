---
title: "CMFCRibbonComboBox クラス | Microsoft Docs"
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
  - "CMFCRibbonComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonComboBox クラス"
ms.assetid: 9b29a6a4-cf17-4152-9b13-0bf90784b30d
caps.latest.revision: 35
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCRibbonComboBox クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CMFCRibbonComboBox` クラスは、リボン バー、リボン パネル、またはリボン ポップアップ メニューに追加できるコンボ ボックスを実装します。  
  
## 構文  
  
```  
class CMFCRibbonComboBox : public CMFCRibbonEdit  
```  
  
## メンバー  
  
### コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonComboBox::CMFCRibbonComboBox](../Topic/CMFCRibbonComboBox::CMFCRibbonComboBox.md)|CMFCRibbonComboBox オブジェクトを構築します。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CMFCRibbonComboBox::AddItem](../Topic/CMFCRibbonComboBox::AddItem.md)|リスト ボックスに一意の項目を追加します。|  
|[CMFCRibbonComboBox::DeleteItem](../Topic/CMFCRibbonComboBox::DeleteItem.md)|リスト ボックスから指定された項目を削除します。|  
|[CMFCRibbonComboBox::EnableDropDownListResize](../Topic/CMFCRibbonComboBox::EnableDropDownListResize.md)|リスト ボックスをドロップダウンしたときに、サイズを変更できるかどうかを指定します。|  
|[CMFCRibbonComboBox::FindItem](../Topic/CMFCRibbonComboBox::FindItem.md)|指定された文字列と一致するリスト ボックス内の最初の項目のインデックスを返します。|  
|[CMFCRibbonComboBox::GetCount](../Topic/CMFCRibbonComboBox::GetCount.md)|リスト ボックスの項目数を返します。|  
|[CMFCRibbonComboBox::GetCurSel](../Topic/CMFCRibbonComboBox::GetCurSel.md)|リスト ボックスで現在選択されている項目のインデックスを取得します。|  
|[CMFCRibbonComboBox::GetDropDownHeight](../Topic/CMFCRibbonComboBox::GetDropDownHeight.md)|リスト ボックスがドロップダウンされたときのリスト ボックスの高さを取得します。|  
|[CMFCRibbonComboBox::GetIntermediateSize](../Topic/CMFCRibbonComboBox::GetIntermediateSize.md)|中間モードで表示されるときのコンボ ボックスのサイズを返します。|  
|[CMFCRibbonComboBox::GetItem](../Topic/CMFCRibbonComboBox::GetItem.md)|リスト ボックス内の、指定されたインデックス位置にある項目に関連付けられた文字列を返します。|  
|[CMFCRibbonComboBox::GetItemData](../Topic/CMFCRibbonComboBox::GetItemData.md)|リスト ボックスの指定したインデックス位置にある項目に関連するデータを返します。|  
|[CMFCRibbonComboBox::HasEditBox](../Topic/CMFCRibbonComboBox::HasEditBox.md)|コントロールにエディット ボックスが含まれるかどうかを示します。|  
|[CMFCRibbonComboBox::IsResizeDropDownList](../Topic/CMFCRibbonComboBox::IsResizeDropDownList.md)|リスト ボックスのサイズを変更できるかどうかを示します。|  
|[CMFCRibbonComboBox::OnSelectItem](../Topic/CMFCRibbonComboBox::OnSelectItem.md)|ユーザーがリスト ボックス内の項目を選択したときに、フレームワークによって呼び出されます。|  
|[CMFCRibbonComboBox::RemoveAllItems](../Topic/CMFCRibbonComboBox::RemoveAllItems.md)|リスト ボックスからすべての項目を削除し、エディット ボックスをクリアします。|  
|[CMFCRibbonComboBox::SelectItem](../Topic/CMFCRibbonComboBox::SelectItem.md)|リスト ボックスの項目を選択します。|  
|[CMFCRibbonComboBox::SetDropDownHeight](../Topic/CMFCRibbonComboBox::SetDropDownHeight.md)|リスト ボックスがドロップダウンされたときの高さを設定します。|  
  
## 解説  
 リボン コンボ ボックスは、静的ラベルまたはユーザーが編集できるラベルと組み合わせたリスト ボックスで構成されます。  リボン コンボ ボックスを作成するときにどちらかの種類を指定する必要があります。  
  
## 使用例  
 `CMFCRibbonComboBox` クラスのオブジェクトの構築、コンボ ボックスへの項目の追加、コンボ ボックスでの項目の選択、およびパネルへのコンボ ボックスの追加方法を次の例に示します。  
  
 [!code-cpp[NVC_MFC_RibbonApp#11](../../mfc/reference/codesnippet/CPP/cmfcribboncombobox-class_1.cpp)]  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonEdit](../../mfc/reference/cmfcribbonedit-class.md)  
  
 [CMFCRibbonComboBox](../../mfc/reference/cmfcribboncombobox-class.md)  
  
## 必要条件  
 **ヘッダー :** afxribboncombobox.h  
  
## 参照  
 [階層図](../../mfc/hierarchy-chart.md)   
 [クラス](../Topic/MFC%20Classes.md)   
 [CMFCRibbonEdit クラス](../../mfc/reference/cmfcribbonedit-class.md)