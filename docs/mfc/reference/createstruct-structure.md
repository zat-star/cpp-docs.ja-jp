---
title: "CREATESTRUCT 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CREATESTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CREATESTRUCT 構造体"
ms.assetid: 028c7b5e-4fdc-48da-a550-d3e4f9e6cc85
caps.latest.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 15
---
# CREATESTRUCT 構造体
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CREATESTRUCT` 構造体は、アプリケーションのウィンドウ プロシージャに渡す初期化パラメーターを定義します。  
  
## 構文  
  
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
  
#### パラメーター  
 `lpCreateParams`  
 ウィンドウを作成するために使用されるデータへのポインター。  
  
 `hInstance`  
 新しいウィンドウを所有するモジュールのモジュールのインスタンス ハンドルを識別します。  
  
 `hMenu`  
 新しいウィンドウが使用されるメニューを識別します。  子ウィンドウが、整数の ID が含まれる場合  
  
 `hwndParent`  
 新しいウィンドウを所有するウィンドウを識別します。  このメンバーが新しいウィンドウがトップレベル ウィンドウの **NULL** です。  
  
 `cy`  
 新しいウィンドウの高さを指定します。  
  
 `cx`  
 新しいウィンドウの幅を指定します。  
  
 `y`  
 新しいウィンドウの左上隅の y 座標を指定します。  座標は親ウィンドウに対して新しいウィンドウが子ウィンドウで;です それは、画面座標の原点を基準にします。  
  
 `x`  
 新しいウィンドウの左上隅の x 座標を指定します。  座標は親ウィンドウに対して新しいウィンドウが子ウィンドウで;です それは、画面座標の原点を基準にします。  
  
 `style`  
 新しい Windows [スタイル](../../mfc/reference/styles-used-by-mfc.md)を指定します。  
  
 `lpszName`  
 新しいウィンドウの名前を指定する NULL で終わる文字列へのポインター。  
  
 `lpszClass`  
 新しいウィンドウのウィンドウ クラスの名前 \([WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 構造体を指定する NULL で終わる文字列へのポインター; 詳細については、「[!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]」を参照してください。  
  
 `dwExStyle`  
 新しいウィンドウに [拡張スタイル](../Topic/Extended%20Window%20Styles.md) を指定します。  
  
## 必要条件  
 **ヘッダー:** winuser.h  
  
## 参照  
 [構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnCreate](../Topic/CWnd::OnCreate.md)