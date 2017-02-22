---
title: "DELETEITEMSTRUCT 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DELETEITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DELETEITEMSTRUCT 構造体"
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# DELETEITEMSTRUCT 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`DELETEITEMSTRUCT` 構造体は削除されたオーナー描画のリスト ボックスまたは ComboBox 項目を示します。  
  
## 構文  
  
```  
  
      typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### パラメーター  
 `CtlType`  
 **ODT\_LISTBOX** \(オーナー描画のリスト ボックス\) または **ODT\_COMBOBOX** \(オーナー描画のコンボ ボックス\) を指定します。  
  
 `CtlID`  
 リスト ボックスやコンボ ボックスの識別子を指定します。  
  
 `itemID`  
 削除するリスト ボックスやコンボ ボックスの項目のインデックスを指定します。  
  
 `hwndItem`  
 コントロールを識別します。  
  
 `itemData`  
 呼び出される項目のデータをアプリケーション定義しました。  この値はリスト ボックスやコンボ ボックスに項目を追加するメッセージの **lParam** パラメーターのコントロールに渡されます。  
  
## 解説  
 項目がリスト ボックスやコンボ ボックスから削除したり、リスト ボックスやコンボ ボックスが破棄されるときに、Windows は、削除された項目の所有者に `WM_DELETEITEM` メッセージを送信します。  メッセージの **lParam** パラメーターは、この構造体へのポインターが格納されます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)