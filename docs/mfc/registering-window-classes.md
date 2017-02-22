---
title: "ウィンドウ クラスの登録 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WndProc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxRegisterWndClass メソッド"
  - "クラス [C++], 登録 (ウィンドウ クラスを)"
  - "MFC, ウィンドウ"
  - "登録 (ウィンドウ クラスを)"
  - "レジストリ, 登録 (クラスを)"
  - "ウィンドウ クラス, 登録"
  - "WinMain メソッド"
  - "WinMain メソッド, および登録 (ウィンドウ クラスの)"
  - "WndProc メソッド"
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ウィンドウ クラスの登録
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィンドウが定義されます。ウィンドウ数を作成できる「クラス」の特性を「Windows の通常のプログラミングを設定します」。\(非 C\+\+.クラス\)。  このようなクラスには、ウィンドウを作成するためのテンプレートまたはモデルです。  
  
## Windows の通常のプログラムのウィンドウ クラスの登録  
 Windows の通常のプログラムでは、MFC を使わない「ウィンドウ プロシージャ」または「**WndProc**ウィンドウにすべてのメッセージを処理します」。**WndProc** は「Windows クラスの登録」プロセスによってウィンドウに関連付けられます。  メイン ウィンドウが `WinMain` 関数に登録されているウィンドウの他のクラスはアプリケーション内のあらゆる場所で登録できます。  登録は、カーソル、背景ブラシの仕様とともに **WndProc** 関数へのポインターを含む構造体などによって異なります。  構造体は **RegisterClass** 関数、前の呼び出しのクラスの文字列名とともにパラメーターとして渡されます。  したがって、登録クラスは複数のウィンドウで共有できます。  
  
## MFC プログラムのウィンドウ クラスの登録  
 これに対し、ほとんどのウィンドウ クラスの登録アクティビティは、MFC フレームワークのプログラムで自動的に行われます。  MFC を使用すると、クラスの継承の標準 C\+\+ 構文を使用すると、既存のライブラリ クラスからその C \+\+.ウィンドウ クラスを派生します。  フレームワークは、従来の「登録クラスを使用し」、必要に応じて、複数の標準ものも、登録して提供します。  [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) のグローバル関数を呼び出し、`CWnd`の **作成** メンバー関数に登録したクラスを渡すことによって、追加登録クラスを登録できます。  、従来の「登録クラス」は Windows で以下で説明するように、C.クラスと混同しないようにしてください。  
  
 詳細については、「[テクニカル ノート 1](../mfc/tn001-window-class-registration.md)」を参照してください。  
  
## 参照  
 [ウィンドウの作成](../Topic/Creating%20Windows.md)