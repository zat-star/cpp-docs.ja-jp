---
title: "WINDOWPOS Structure1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
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
ms.openlocfilehash: 522b15d630c3a5a3593010250db0491601493c69
ms.lasthandoff: 02/24/2017

---
# <a name="windowpos-structure1"></a>WINDOWPOS Structure1
`WINDOWPOS`構造体にはサイズとウィンドウの位置に関する情報が含まれています。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagWINDOWPOS { /* wp */  
    HWND hwnd;  
    HWND hwndInsertAfter;  
    int x;  
    int y;  
    int cx;  
    int cy;  
    UINT flags;  
} WINDOWPOS;  
```  
  
#### <a name="parameters"></a>パラメーター  
 *hwnd の分離*  
 ウィンドウを識別します。  
  
 *オーダーで*  
 このウィンドウを配置するの背後にあるウィンドウを識別します。  
  
 *x*  
 ウィンドウの左端の位置を指定します。  
  
 *y*  
 ウィンドウの上端の位置を指定します。  
  
 `cx`  
 ウィンドウの幅をピクセル単位で指定します。  
  
 `cy`  
 ウィンドウの高さをピクセル単位で指定します。  
  
 `flags`  
 ウィンドウの位置決めオプションを指定します。 このメンバーは、次の値のいずれかになります。  
  
- **SWP_DRAWFRAME**ウィンドウの周囲 (ウィンドウのクラスの説明で定義) の枠を描画します。 ウィンドウを受け取る、`WM_NCCALCSIZE`メッセージです。  
  
- **SWP_FRAMECHANGED**送信、`WM_NCCALCSIZE`ウィンドウのサイズが変更されていない場合でも、ウィンドウに表示するメッセージします。 このフラグが指定されていない場合`WM_NCCALCSIZE`ウィンドウのサイズが変更されている場合にのみに送信します。  
  
- **SWP_HIDEWINDOW**ウィンドウを非表示にします。  
  
- `SWP_NOACTIVATE`ウィンドウをアクティブにしません。  
  
- **SWP_NOCOPYBITS**クライアント領域の内容全体を破棄します。 このフラグが指定されていない場合、クライアント領域の有効な内容が保存され、ウィンドウのサイズや位置を変更した後、クライアント領域にコピーします。  
  
- `SWP_NOMOVE`現在の位置が保持されます (無視、 **x**と**y**メンバー)。  
  
- **SWP_NOOWNERZORDER** Z オーダーでオーナー ウィンドウの位置は変更されません。  
  
- `SWP_NOSIZE`現在のサイズが保持されます (無視、 **cx**と**cy**メンバー)。  
  
- **SWP_NOREDRAW**の変更が再描画されません。  
  
- **SWP_NOREPOSITION**と同じ**SWP_NOOWNERZORDER**します。  
  
- **SWP_NOSENDCHANGING**受信ウィンドウのことを回避、`WM_WINDOWPOSCHANGING`メッセージです。  
  
- `SWP_NOZORDER`現在の順序が保持されます (無視、**オーダーで**メンバー)。  
  
- **SWP_SHOWWINDOW**ウィンドウを表示します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)


