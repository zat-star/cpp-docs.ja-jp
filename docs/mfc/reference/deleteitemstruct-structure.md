---
title: "DELETEITEMSTRUCT 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DELETEITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- DELETEITEMSTRUCT structure
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: f5936cbb863cf8ace851609cb1dc8352e21f9456
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="deleteitemstruct-structure"></a>DELETEITEMSTRUCT 構造体
`DELETEITEMSTRUCT`構造が削除されたオーナー描画リスト ボックスまたはコンボ ボックス項目について説明します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `CtlType`  
 指定**ODT_LISTBOX** (オーナー描画のリスト ボックス) または**ODT_COMBOBOX** (オーナー描画のコンボ ボックス)。  
  
 `CtlID`  
 リスト ボックスまたはコンボ ボックスの識別子を指定します。  
  
 `itemID`  
 リスト ボックスまたはコンボ ボックスの削除された項目のインデックスを指定します。  
  
 `hwndItem`  
 コントロールを識別します。  
  
 `itemData`  
 アイテムのデータをアプリケーション定義を指定します。 この値がコントロールに渡される、 **lParam**項目をリスト ボックスまたはコンボ ボックスに追加するメッセージのパラメーターです。  
  
## <a name="remarks"></a>コメント  
 リスト ボックスまたはコンボ ボックスから、またはリスト ボックスまたはコンボ ボックスが破棄されるときに項目が削除されると、Windows が送信、`WM_DELETEITEM`メッセージが削除される各項目の所有者にします。 **LParam**メッセージのパラメーターには、この構造体へのポインターが含まれています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [構造体](../../mfc/reference/cwnd-class.md#ondeleteitem)



