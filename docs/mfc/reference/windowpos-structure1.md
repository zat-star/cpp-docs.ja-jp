---
title: "WINDOWPOS Structure1 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- WINDOWPOS
dev_langs:
- C++
helpviewer_keywords:
- WINDOWPOS structure [MFC]
ms.assetid: a4ea7cd9-c4c2-4480-9c55-cbbff72195e1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7db3991a6767e33c73857daf40a977ac5f6f0b85
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="windowpos-structure1"></a>WINDOWPOS Structure1
`WINDOWPOS`構造体には、ウィンドウの位置とサイズに関する情報が含まれています。  
  
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
 *hwnd*  
 ウィンドウを識別します。  
  
 *オーダーで*  
 このウィンドウを配置する背後にあるウィンドウを識別します。  
  
 *x*  
 ウィンドウの左端の位置を指定します。  
  
 *y*  
 ウィンドウの右の端の位置を指定します。  
  
 `cx`  
 ウィンドウの幅をピクセル単位で指定します。  
  
 `cy`  
 ウィンドウの高さをピクセル単位で指定します。  
  
 `flags`  
 ウィンドウの位置決めオプションを指定します。 このメンバーは、次の値のいずれかになります。  
  
- **SWP_DRAWFRAME**ウィンドウの周囲 (ウィンドウのクラスの説明で定義されている) にフレームを描画します。 ウィンドウを受け取る、`WM_NCCALCSIZE`メッセージ。  
  
- **SWP_FRAMECHANGED**送信、`WM_NCCALCSIZE`ウィンドウのサイズが変更されない場合でも、ウィンドウに表示するメッセージします。 このフラグが指定されていない場合`WM_NCCALCSIZE`ウィンドウのサイズが変更されるときにのみ送信されます。  
  
- **SWP_HIDEWINDOW**ウィンドウを非表示にします。  
  
- `SWP_NOACTIVATE`ウィンドウをアクティブにしません。  
  
- **SWP_NOCOPYBITS**クライアント領域の内容全体を破棄します。 このフラグが指定されていない場合、クライアント領域の有効な内容が保存され、ウィンドウのサイズまたは位置を変更した後、クライアント領域にコピーします。  
  
- `SWP_NOMOVE`現在の位置を保持 (は無視、 **x**と**y**メンバー)。  
  
- **SWP_NOOWNERZORDER** Z オーダーのオーナー ウィンドウの位置は変更されません。  
  
- `SWP_NOSIZE`現在のサイズを保持 (は無視、 **cx**と**cy**メンバー)。  
  
- **SWP_NOREDRAW**変更が再描画されません。  
  
- **SWP_NOREPOSITION**と同じ**SWP_NOOWNERZORDER**です。  
  
- **SWP_NOSENDCHANGING**受信できなくなります、ウィンドウ、`WM_WINDOWPOSCHANGING`メッセージ。  
  
- `SWP_NOZORDER`現在の順序が保持されます (は無視、**オーダーで**メンバー)。  
  
- **SWP_SHOWWINDOW**ウィンドウが表示されます。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnWindowPosChanging](../../mfc/reference/cwnd-class.md#onwindowposchanging)

