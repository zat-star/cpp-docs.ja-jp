---
title: "DRAWITEMSTRUCT 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DRAWITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DRAWITEMSTRUCT 構造体"
ms.assetid: ba9ef1d4-aebb-45e9-b956-4b81a02e50f7
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DRAWITEMSTRUCT 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`DRAWITEMSTRUCT` 構造体は、オーナー ウィンドウでオーナー描画コントロールまたはメニュー項目の描画方法を決定する情報を提供します。  
  
## 構文  
  
```  
  
typedef struct tagDRAWITEMSTRUCT {  
   UINT   
CtlType  
;  
   UINT   
CtlID  
;  
   UINT   
itemID  
;  
   UINT   
itemAction  
;  
   UINT   
itemState  
;  
   HWND   
hwndItem  
;  
   HDC   
hDC  
;  
   RECT   
rcItem  
;  
   DWORD   
itemData  
;  
} DRAWITEMSTRUCT;  
  
```  
  
#### パラメーター  
 `CtlType`  
 コントロール型。 コントロール型の値は次のとおりです。  
  
-   **ODT\_BUTTON** オーナー描画ボタン  
  
-   **ODT\_COMBOBOX** オーナー描画コンボ ボックス  
  
-   **ODT\_COMBOBOX** オーナー描画リスト ボックス  
  
-   **ODT\_MENU** オーナー描画メニュー  
  
-   **ODT\_LISTVIEW** リスト ビュー コントロール  
  
-   **ODT\_STATIC** オーナー描画スタティック コントロール  
  
-   **ODT\_TAB** タブ コントロール  
  
 `CtlID`  
 コンボ ボックス、リスト ボックスまたはボタンのコントロール ID。 このメンバーは、メニューには使用されません。  
  
 `itemID`  
 メニューのメニュー項目 ID、あるいはリスト ボックスまたはコンボ ボックス内の項目のインデックス。 このメンバーは、空のリスト ボックスまたはコンボ ボックスの場合は負の値であり、アプリケーションは、コントロールに項目がない場合でも、**rcItem** メンバーで指定されている座標のフォーカスを表す四角形のみを描画します。 したがって、ユーザーはリスト ボックスまたはコンボ ボックスに入力フォーカスがあるかどうかを判断できます。**itemAction** メンバー内のビットの設定によって、リスト ボックスまたはコンボ ボックスに入力フォーカスがあるものとして四角形を描画するかどうかが決まります。  
  
 `itemAction`  
 描画に必要なアクションを定義します。 これは次のビットの 1 つ以上になります。  
  
-   **ODA\_DRAWENTIRE** コントロール全体を描画する必要がある場合に設定されます。  
  
-   **ODA\_FOCUS** コントロールが入力フォーカスを取得したとき、または失ったときに設定されます。**ItemState** メンバーは、コントロールにフォーカスがあるかどうかを判断する場合にチェックします。  
  
-   **ODA\_SELECT** 選択状態が変更された場合にのみ設定されます。**itemState** メンバーは、選択状態が新しくなったかどうかを判断する場合にチェックします。  
  
 *itemState*  
 現在の描画アクションが実行された後の項目の表示状態を指定します。 つまり、メニュー項目が淡色表示されている場合、状態フラグ **ODS\_GRAYED** が設定されます。 状態フラグは次のとおりです。  
  
-   **ODS\_CHECKED** メニュー項目をチェックする場合に設定されます。 このビットは、メニューでのみ使用されます。  
  
-   **ODS\_DISABLED** 項目の描画が無効になっている場合に設定されます。  
  
-   **ODS\_FOCUS** 項目に入力フォーカスがある場合に設定されます。  
  
-   **ODS\_GRAYED** 項目が淡色表示される場合に設定されます。 このビットは、メニューでのみ使用されます。  
  
-   **ODS\_SELECTED** 項目の状態が選択されている場合に設定されます。  
  
-   **ODS\_COMBOBOXEDIT** オーナー描画のコンボ ボックスの選択項目 \(エディット コントロール\) で描画が実行されます。  
  
-   **ODS\_DEFAULT** 項目は既定の項目です。  
  
 `hwndItem`  
 コンボ ボックス、リスト ボックス、およびボタンをコントロールするウィンドウ ハンドルを指定します。 メニュー項目を含むメニューのハンドルを指定します \(`HMENU`\)。  
  
 `hDC`  
 デバイス コンテキストを識別します。 このデバイス コンテキストは、コントロール上で描画操作を実行するときに使用する必要があります。  
  
 *rcItem*  
 コントロールの境界を定義する `hDC` メンバーによってデバイス コンテキストを指定すると、そこに四角形が描画されます。 Windows では、コンボ ボックス、リスト、ボックス、およびボタン用にデバイス コンテキストにオーナーが描画したものすべてが自動的にクリップされますが、メニュー項目はクリップされません。 メニュー項目を描画する場合、オーナーは **rcItem** メンバーで定義した四角形の境界外には描画できません。  
  
 `itemData`  
 コンボ ボックスまたはリスト ボックスでは、次のいずれかによってリスト ボックスに渡された値がメンバーに含まれています。  
  
-   [CComboBox::AddString](../Topic/CComboBox::AddString.md)  
  
-   [CComboBox::InsertString](../Topic/CComboBox::InsertString.md)  
  
-   [CListBox::AddString](../Topic/CListBox::AddString.md)  
  
-   [CListBox::InsertString](../Topic/CListBox::InsertString.md)  
  
 メニューでは、次のいずれかによってメニューに渡された値がメンバーに含まれています。  
  
-   [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)  
  
-   [CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)  
  
-   [CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)  
  
## 解説  
 オーナー描画コントロールのオーナー ウィンドウまたはメニュー項目は、この構造体へのポインターを `WM_DRAWITEM` メッセージの `lParam` パラメーターとして受け取ります。  
  
## 必要条件  
 **ヘッダー:** winuser.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDrawItem](../Topic/CWnd::OnDrawItem.md)