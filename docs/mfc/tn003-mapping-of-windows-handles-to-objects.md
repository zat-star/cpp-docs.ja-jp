---
title: "テクニカル ノート 3: Windows ハンドルとオブジェクト間のマップ | Microsoft Docs"
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
  - "vc.mapping"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ハンドル マップ"
  - "マップ, Windows ハンドル (オブジェクトに)"
  - "TN003"
  - "Windows ハンドル (オブジェクトに) [C++]"
ms.assetid: fbea9f38-992c-4091-8dbc-f29e288617d6
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 3: Windows ハンドルとオブジェクト間のマップ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ここでは、C\+\+ オブジェクトにマッピング ウィンドウ オブジェクト ハンドルをサポートする MFC ルーチンについて説明します。  
  
## 問題  
 window オブジェクトは、MFC クラスの折り返しのウィンドウ オブジェクトが C\+\+ オブジェクトを処理する [ハンドル](http://msdn.microsoft.com/library/windows/desktop/aa383751) のさまざまな通常オブジェクトによって表されます。  MFC のクラス ライブラリ関数をラップするハンドルは特定のハンドルを持つウィンドウ オブジェクトをラップしている C\+\+ オブジェクトを見つけることができます。  ただし、オブジェクトに対する C \+\+.のラッパー オブジェクトがないため、これらの時点でシステムは C\+\+ のラッパーとして機能する一時オブジェクトが作成されます。  
  
 次のように使用のハンドルのマップがあります。ウィンドウ オブジェクト:  
  
-   HWND \([CWnd](../Topic/CWnd%20Class.md) と `CWnd`\-派生クラス\)  
  
-   HDC \([CDC](../Topic/CDC%20Class.md) と `CDC`\-派生クラス\)  
  
-   HMENU \([CMenu](../mfc/reference/cmenu-class.md)\)  
  
-   HPEN \([CGdiObject](../mfc/reference/cgdiobject-class.md)\)  
  
-   HBRUSH \(`CGdiObject`\)  
  
-   HFONT \(`CGdiObject`\)  
  
-   HBITMAP \(`CGdiObject`\)  
  
-   HPALETTE \(`CGdiObject`\)  
  
-   HRGN \(`CGdiObject`\)  
  
-   HIMAGELIST \([CImageList](../Topic/CImageList%20Class.md)\)  
  
-   ソケット \([CSocket](../mfc/reference/csocket-class.md)\)  
  
 ハンドルをこれらのオブジェクトのいずれかにより、静的 `FromHandle`メソッドを呼び出して、ハンドルをラップする MFC オブジェクトを参照できます。  たとえば、HWND を指定 `hWnd`、次の行を返します `hWnd`をラップする `CWnd` へのポインターという:  
  
```  
CWnd::FromHandle(hWnd)  
```  
  
 `hWnd` に特定のラッパー オブジェクトが存在しない場合 `hWnd`をラップするには、一時 `CWnd` が作成されます。  これは、ハンドルの有効な C\+\+ オブジェクトを取得できるようにします。  
  
 ラッパー オブジェクトが見つかったら、ラッパー クラスのパブリック メンバー変数からハンドルを取得できます。  `CWnd`の場合、`m_hWnd` はそのオブジェクトの HWND が含まれます。  
  
## MFC オブジェクトへのハンドルの接続  
 ウィンドウ オブジェクトへの新しく作成されたハンドル ラッパー オブジェクトおよびハンドルは、この例のように `Attach` 関数を呼び出して 2 を関連付けることができますが、T:  
  
```  
CWnd myWnd;  
myWnd.Attach(hWnd);  
```  
  
 これは `myWnd` と `hWnd`を関連付けるパーマネント マップのエントリを作成します。  `CWnd::FromHandle(hWnd)` を呼び出すと、`myWnd`でポインターを返します。  `myWnd` が削除された場合、デストラクターは Windows の [DestroyWindow](http://msdn.microsoft.com/library/windows/desktop/ms632682) 関数を呼び出すことによって自動的に `hWnd` を破棄します。  これは、望まれなければ `hWnd` は `myWnd` が定義された\) 離れたときにスコープを `myWnd` が破棄される前に `myWnd` からデタッチする必要があります \(通常は。  `Detach` のメソッドはこれを行います。  
  
```  
myWnd.Detach();  
```  
  
## 一時オブジェクトの詳細  
 一時オブジェクトは `FromHandle` が既にラッパー オブジェクトを持っていないハンドルで提供されるたびに作成されます。  これらの一時オブジェクトがハンドルからデタッチ、`DeleteTempMap` 関数によって削除されます。  既定で [CWinThread::OnIdle](../Topic/CWinThread::OnIdle.md) は自動的に一時ハンドル マップをサポートする各クラスの `DeleteTempMap` を呼び出します。  これは、一時オブジェクトへのポインターがポインターを含む関数が終了したポイントまで有効であるとできないことを意味します。  
  
## ラッパー オブジェクトと複数のスレッド  
 一時と永続的なオブジェクトはスレッドごとに保持されます。  つまり、1 個のスレッドは一時または永続的かどうか別のスレッドの C\+\+ のラッパー オブジェクトに関係なく、アクセスできません。  
  
 1 種類のスレッドから別のプロジェクトにこれらのオブジェクトを渡すには、`HANDLE` のネイティブ型を常に移動します。  1 種類のスレッドから別の場所に C \+\+.のラッパー オブジェクトを渡すと、予期しない結果になります。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)