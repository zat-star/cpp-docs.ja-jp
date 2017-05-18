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
- CREATESTRUCT structure
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
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
ms.openlocfilehash: ec72d4725cb7e5959369b24a6ff7f0e3e9da1ca7
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

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
 ウィンドウを作成するためのデータへのポインター。  
  
 `hInstance`  
 新しいウィンドウを所有しているモジュールのモジュール インスタンス ハンドルを識別します。  
  
 `hMenu`  
 新しいウィンドウで使用するメニューを識別します。 子ウィンドウの場合は、整数の ID が含まれています  
  
 `hwndParent`  
 新しいウィンドウを所有しているウィンドウを識別します。 このメンバーは**NULL**新しいウィンドウがトップレベル ウィンドウの場合。  
  
 `cy`  
 新しいウィンドウの高さを指定します。  
  
 `cx`  
 新しいウィンドウの幅を指定します。  
  
 `y`  
 新しいウィンドウの左上隅の y 座標を指定します。 新しいウィンドウが子ウィンドウの場合は親ウィンドウの相対座標は、します。それ以外の場合、座標は画面の原点に対するです。  
  
 `x`  
 新しいウィンドウの左上隅の x 座標を指定します。 新しいウィンドウが子ウィンドウの場合は親ウィンドウの相対座標は、します。それ以外の場合、座標は画面の原点に対するです。  
  
 `style`  
 新しいウィンドウの指定[スタイル](../../mfc/reference/styles-used-by-mfc.md)します。  
  
 `lpszName`  
 新しいウィンドウの名前を指定する null で終わる文字列へのポインター。  
  
 `lpszClass`  
 新しいウィンドウのウィンドウ クラス名を指定する null で終わる文字列へのポインター (、 [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)構造体は、詳細については、参照してください、 [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)])。  
  
 `dwExStyle`  
 指定、[拡張スタイル](../../mfc/reference/extended-window-styles.md)新しいウィンドウのです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** winuser.h  
  
## <a name="see-also"></a>関連項目  
 [構造体、スタイル、コールバック、およびメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate)



