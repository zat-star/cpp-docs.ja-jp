---
title: "テクニカル ノート 1: ウィンドウ クラスの登録 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.registration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxRegisterClass 関数"
  - "TN001"
  - "WNDCLASS"
ms.assetid: 1abf678e-f220-4606-85e0-03df32f64c54
caps.latest.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# テクニカル ノート 1: ウィンドウ クラスの登録
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、Microsoft Windows によって必要とされる特別な [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576)es を登録する MFC ルーチンについて説明します。  MFC で使用する `WNDCLASS` の特定の属性と"で説明します。  
  
## 問題  
 [CWnd](../Topic/CWnd%20Class.md) 属性は、2 か所で Windows `HWND` のハンドルと同様に、保存されます:です。window オブジェクトと `WNDCLASS`。  `WNDCLASS` の名前は `lpszClassName` パラメーターの [CWnd::Create](../Topic/CWnd::Create.md) と [CFrameWnd::Create](../Topic/CFrameWnd::Create.md) などの一般的なウィンドウの作成関数に渡されます。  
  
 この `WNDCLASS` は 4 の 1 に登録する必要があります:  
  
-   MFC に用意されている `WNDCLASS`を使用して暗黙的。  
  
-   Windows のコントロール \(または他のコントロール\) サブクラス化することによって暗黙的。  
  
-   明示的に MFC [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) または [AfxRegisterClass](../Topic/AfxRegisterClass.md)を呼び出して。  
  
-   明示的に Windows [RegisterClass](http://msdn.microsoft.com/library/windows/desktop/ms633586)ルーチンを呼び出して。  
  
## WNDCLASS フィールド  
 `WNDCLASS` 構造体はウィンドウ クラスを記述するさまざまなフィールドで構成されます。  次の表は、フィールドを示し、MFC アプリケーションでどのように使用するかを指定し、T:  
  
|フィールド|説明|  
|-----------|--------|  
|`lpfnWndProc`|ウィンドウ プロシージャは、`AfxWndProc`である必要があります。|  
|`cbClsExtra`|使用されない場合 \(ゼロが必要です\)。|  
|`cbWndExtra`|使用されない場合 \(ゼロが必要です\)。|  
|`hInstance`|[AfxGetInstanceHandle](../Topic/AfxGetInstanceHandle.md)で自動的に値|  
|`hIcon`|フレーム ウィンドウのアイコンが、参照します|  
|`hCursor`|マウス カーソルがウィンドウにある場合は、次の参照します|  
|`hbrBackground`|背景色は、参照します|  
|`lpszMenuName`|使用されていない \(null です\)|  
|`lpszClassName`|クラス名は、参照します|  
  
## 指定された WNDCLASSes  
 以前のバージョンの MFC \(MFC 4.0 の前\) に、複数の定義済みのなウィンドウ クラス。  これらのウィンドウ クラスは、既定では提供されていません。  アプリケーションは、適切なパラメーターを `AfxRegisterWndClass` を使用する必要があります。  
  
 アプリケーションが指定したリソース id をリソース \(たとえば、AFX\_IDI\_STD\_FRAME\) 場合、MFC はそのリソースを使用します。  それ以外の場合は、既定のリソースを使用します。  アイコンの場合は、標準のアプリケーション アイコンが使用され、カーソルの場合は、標準矢印カーソルが使用されます。  
  
 単一ドキュメントの型の 2 種類のサポート: MDI アプリケーション アイコン メイン アプリケーションの 1 種類のアイコンのイメージ、MDIChild 的なドキュメントまたはウィンドウの他のアイコン。  異なるアイコンを持つ複数のドキュメントの場合、追加 `WNDCLASS`es を登録したり、[CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md) 関数を使用する必要があります。  
  
 `CFrameWnd::LoadFrame` は、最初のパラメーターと次の標準の属性として指定できるアイコン ID を使用して `WNDCLASS` を登録する:  
  
-   クラス スタイル: CS\_DBLCLKS &#124; CS\_HREDRAW &#124; CS\_VREDRAW;  
  
-   アイコン AFX\_IDI\_STD\_FRAME  
  
-   矢印カーソル  
  
-   COLOR\_WINDOW の背景色  
  
 `CMDIFrameWnd` のクライアント領域の **\[MDICLIENT\]** ウィンドウに完全に処理されるため、背景色の値および [CMDIFrameWnd](../mfc/reference/cmdiframewnd-class.md) のカーソルは使用されません。  Microsoft は **\[MDICLIENT\]** ウィンドウのサブクラス化行為を、可能な場合は標準色とカーソルの種類を使用します。  
  
## サブクラス化してコントロールをスーパークラス化すれば  
 またはサブクラス化するかスーパークラス化は、Windows のコントロール \(たとえば、[CButton](../mfc/reference/cbutton-class.md)クラスは、自動的に `WNDCLASS` 属性をそのコントロールの Windows の実装を提供します。  
  
## AfxRegisterWndClass 関数  
 MFC には、ウィンドウ クラスを登録するヘルパー関数を提供します。  一連の属性 \(ウィンドウ クラス スタイル、カーソル、背景ブラシとアイコン\) の場合、全体的な名前が生成され、そのウィンドウ クラスが登録されています。  次に例を示します。  
  
```  
const char* AfxRegisterWndClass(UINT nClassStyle, HCURSOR hCursor, HBRUSH hbrBackground, HICON hIcon);  
```  
  
 この関数の戻り値が生成した登録されているウィンドウ クラス名の一時的な文字列。  この関数の詳細については、「[AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md)」を参照してください。  
  
 返される文字列は静的な文字列バッファーに一時的なポインターです。  これは `AfxRegisterWndClass`に回復するまで有効です。  この文字列を格納する場合は、この例のように [CString](../atl-mfc-shared/using-cstring.md) の変数に格納する:  
  
```  
CString strWndClass = AfxRegisterWndClass(CS_DBLCLK, ...);  
...  
CWnd* pWnd = new CWnd;  
pWnd->Create(strWndClass, ...);  
...  
```  
  
 `AfxRegisterWndClass` は ウィンドウ クラスが登録されていない場合 [CResourceException](../mfc/reference/cresourceexception-class.md) をスローします \(から不適切なパラメーターに、または Windows メモリ\)。  
  
## RegisterClass と AfxRegisterClass 関数  
 どの `AfxRegisterWndClass` があります。より複雑になる何もする場合は、Windows API `RegisterClass` や MFC の `AfxRegisterClass`関数を呼び出すことができます。  `CWnd`、[CFrameWnd](../mfc/reference/cframewnd-class.md) と [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md) `Create` 関数は、最初のパラメーターとしてウィンドウ クラスの `lpszClassName` の文字列名を受け取ります。  ユーザー コントロールを登録するために使用するメソッドに関係なく、登録されたウィンドウ クラスの名前を使用できます。  
  
 Win32 の DLL で `AfxRegisterClass` \(または `AfxRegisterWndClass`\) を使用することが重要です。  Win32 には、自動的に DLL に登録されているクラスを登録解除されておらず、DLL が終了すると、明示的にクラスの登録を解除する必要があります。  `RegisterClass` の代わりに `AfxRegisterClass` を使用してこれが自動的に処理されます。  `AfxRegisterClass` は DLL が終了すると、DLL に登録されている一意のクラスのリストを保持し、自動的に登録解除します。  DLL で `RegisterClass` を使用すると、DLL が終了すると、すべてのクラスを登録解除する必要があります \([DllMain](http://msdn.microsoft.com/library/windows/desktop/ms682583) 関数\)。  他のクライアント アプリケーションが DLL を使用しようとしたときにそのエラーは、`RegisterClass` で予期しないエラーが発生することがあります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)