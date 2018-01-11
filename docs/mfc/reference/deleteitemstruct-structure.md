---
title: "DELETEITEMSTRUCT 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DELETEITEMSTRUCT
dev_langs: C++
helpviewer_keywords: DELETEITEMSTRUCT structure [MFC]
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 93be7b23ae713caea5fa64e437fe792c550589f1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
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
 指定**ODT_LISTBOX** (オーナー描画リスト ボックス、) または**ODT_COMBOBOX** (オーナー描画コンボ ボックス、)。  
  
 `CtlID`  
 リスト ボックスまたはコンボ ボックスの識別子を指定します。  
  
 `itemID`  
 リスト ボックスまたはコンボ ボックスの削除された項目のインデックスを指定します。  
  
 `hwndItem`  
 コントロールを識別します。  
  
 `itemData`  
 アイテムのアプリケーション定義のデータを指定します。 コントロールにこの値は、 **lParam**リスト ボックスまたはコンボ ボックスに、項目を追加、メッセージのパラメーターです。  
  
## <a name="remarks"></a>コメント  
 リスト ボックスまたはコンボ ボックスから、またはリスト ボックスまたはコンボ ボックスが破棄されるときに項目が削除されると、Windows の送信、`WM_DELETEITEM`削除される各項目の所有者へのメッセージ。 **LParam**メッセージのパラメーターには、この構造体へのポインターが含まれています。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** atldbcli.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [構造体](../../mfc/reference/cwnd-class.md#ondeleteitem)


