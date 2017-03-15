---
title: "COMPAREITEMSTRUCT 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- COMPAREITEMSTRUCT
dev_langs:
- C++
helpviewer_keywords:
- COMPAREITEMSTRUCT structure
ms.assetid: 4b7131a5-5c7d-4e98-aac7-e85650262b52
caps.latest.revision: 11
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 6c38c3e362f2e97cb51f5474aaa0bc05098b1ec2
ms.lasthandoff: 02/24/2017

---
# <a name="compareitemstruct-structure"></a>COMPAREITEMSTRUCT 構造体
`COMPAREITEMSTRUCT`構造体は、識別子と、オーナー描画の並べ替えられたリスト ボックスまたはコンボ ボックスの&2; つの項目にアプリケーションによって提供されるデータを提供します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagCOMPAREITEMSTRUCT {  
    UINT CtlType;  
    UINT CtlID;  
    HWND hwndItem;  
    UINT itemID1;  
    DWORD itemData1;  
    UINT itemID2;  
    DWORD itemData2;  
} COMPAREITEMSTRUCT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `CtlType`  
 **ODT_LISTBOX** (オーナー描画のリスト ボックスを指定する) または**ODT_COMBOBOX** (オーナー描画コンボ ボックスを指定する)。  
  
 `CtlID`  
 リスト ボックスまたはコンボ ボックスのコントロールの ID。  
  
 `hwndItem`  
 コントロールのウィンドウ ハンドル。  
  
 *itemID1*  
 リスト ボックスまたはコンボ ボックスの比較対象となるは、最初の項目のインデックス。  
  
 *itemData1*  
 比較対象となる最初の項目のアプリケーションによって提供されるデータ。 この値は、アイテムをコンボ ボックスまたはリスト ボックスに追加の呼び出しで渡されました。  
  
 *itemID2*  
 リスト ボックスまたはコンボ ボックスの比較対象となる&2; 番目の項目のインデックス。  
  
 *itemData2*  
 比較対象となる&2; 番目の項目のアプリケーションによって提供されるデータ。 この値は、アイテムをコンボ ボックスまたはリスト ボックスに追加の呼び出しで渡されました。  
  
## <a name="remarks"></a>コメント  
 ときに、アプリケーションでは、オーナー描画のリスト ボックスに新しい項目を追加またはコンボ ボックス、 **CBS_SORT**または**LBS_SORT**スタイル、Windows の送信、所有者、`WM_COMPAREITEM`メッセージです。 `lParam` 、メッセージのパラメーターにはへの long ポインターが含まれています、`COMPAREITEMSTRUCT`構造体。 メッセージを受け取るとは、所有者は、2 つの項目を比較し、どの項目がもう一方の前になることを示す値を返します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCompareItem](../../mfc/reference/cwnd-class.md#oncompareitem)


