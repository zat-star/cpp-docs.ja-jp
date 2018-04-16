---
title: "CREATESTRUCT 構造体 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CREATESTRUCT
dev_langs:
- C++
helpviewer_keywords:
- CREATESTRUCT structure [MFC]
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 97ca66036930963028681b6179ac7176b0350166
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="createstruct-structure"></a>CREATESTRUCT 構造体
`CREATESTRUCT`構造体は、アプリケーションのウィンドウ プロシージャに渡される初期化パラメーターを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
typedef struct tagCREATESTRUCT {  
    LPVOID lpCreateParams;  
    HANDLE hInstance;  
    HMENU hMenu;  
    HWND hwndParent;  
    int cy;  
    int cx;  
    int y;  
    int x;  
    LONG style;  
    LPCSTR lpszName;  
    LPCSTR lpszClass;  
    DWORD dwExStyle;  
} CREATESTRUCT;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lpCreateParams`  
 ウィンドウを作成するために使用するデータへのポインター。  
  
 `hInstance`  
 新しいウィンドウを所有しているモジュールのモジュール インスタンス ハンドルを識別します。  
  
 `hMenu`  
 新しいウィンドウで使用するのには、メニューを識別します。 場合、子ウィンドウは、整数の ID が含まれています  
  
 `hwndParent`  
 新しいウィンドウを所有しているウィンドウを識別します。 このメンバーは**NULL**新しいウィンドウがトップレベル ウィンドウの場合。  
  
 `cy`  
 新しいウィンドウの高さを指定します。  
  
 `cx`  
 新しいウィンドウの幅を指定します。  
  
 `y`  
 新しいウィンドウの左上隅の y 座標を指定します。 新しいウィンドウが子ウィンドウ以外の場合、親ウィンドウに対する相対座標は、します。それ以外の場合座標は、画面の原点に対するします。  
  
 `x`  
 新しいウィンドウの左上隅の x 座標を指定します。 新しいウィンドウが子ウィンドウ以外の場合、親ウィンドウに対する相対座標は、します。それ以外の場合座標は、画面の原点に対するします。  
  
 `style`  
 新しいウィンドウの指定[スタイル](../../mfc/reference/styles-used-by-mfc.md)です。  
  
 `lpszName`  
 新しいウィンドウの名前を指定する null で終わる文字列へのポインター。  
  
 `lpszClass`  
 新しいウィンドウのウィンドウ クラス名を指定する null で終わる文字列へのポインター (、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造体です。 詳細については、Windows SDK を参照してください)。  
  
 `dwExStyle`  
 指定します、[拡張スタイル](../../mfc/reference/styles-used-by-mfc.md#extended-window-styles)新しいウィンドウのです。  
  
## <a name="requirements"></a>必要条件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>参照  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)


