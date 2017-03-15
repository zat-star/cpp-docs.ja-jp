---
title: "MEASUREITEMSTRUCT 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MEASUREITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MEASUREITEMSTRUCT 構造体"
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# MEASUREITEMSTRUCT 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`MEASUREITEMSTRUCT` 構造体はオーナー描画のコントロールやメニュー項目の次元を Windows に通知します。  
  
## 構文  
  
```  
  
      typedef struct tagMEASUREITEMSTRUCT {  
   UINT CtlType;  
   UINT CtlID;  
   UINT itemID;  
   UINT itemWidth;  
   UINT itemHeight;  
   DWORD itemData  
} MEASUREITEMSTRUCT;  
```  
  
#### パラメーター  
 `CtlType`  
 コントロール型が含まれています。  コントロール型の値は次のとおりです。:  
  
-   **ODT\_COMBOBOX**のオーナー描画コンボ ボックス  
  
-   **ODT\_LISTBOX**のオーナー描画リスト ボックス  
  
-   **ODT\_MENU**のオーナー描画メニュー  
  
 `CtlID`  
 コンボ ボックス、リスト ボックス、およびボタンのコントロール ID が含まれています。  このメンバーは、メニューには使用されません。  
  
 `itemID`  
 メニューのメニュー項目 ID または変数高さのコンボ ボックスやリスト ボックスのリスト ボックスの項目 ID が含まれています。  このメンバーは、固定の高さのコンボ ボックスやリスト ボックス、ボタンには使用されません。  
  
 *itemWidth*  
 メニュー項目の幅を指定します。  オーナー描画のメニュー項目の所有者はメッセージから戻る前にこのメンバーを満たす必要があります。  
  
 *itemHeight*  
 リスト ボックスまたはメニューの各項目の高さを指定します。  これがメッセージから戻る前に、オーナー描画コンボ ボックス、リスト ボックス、またはメニュー項目の所有者はこのメンバーを指定する必要があります。  リスト ボックスの項目の高さの最大値は 255 です。  
  
 `itemData`  
 コンボ ボックスやリスト ボックスでは、このメンバーは次のいずれかをリスト ボックスに渡された値があります:  
  
-   [CComboBox::AddString](../Topic/CComboBox::AddString.md)  
  
-   [CComboBox::InsertString](../Topic/CComboBox::InsertString.md)  
  
-   [CListBox::AddString](../Topic/CListBox::AddString.md)  
  
-   [CListBox::InsertString](../Topic/CListBox::InsertString.md)  
  
 メニューの場合は、このメンバーは次のいずれかをメニューに渡された値があります:  
  
-   [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)  
  
-   [CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)  
  
-   [CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)  
  
 これは、Windows のコントロールとの対話を適切に処理することができます。  `MEASUREITEMSTRUCT` 構造体の適切なメンバーを表示するエラーは、コントロールの不適切な操作が発生します。  
  
## 必要条件  
 **ヘッダー:** winuser.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)