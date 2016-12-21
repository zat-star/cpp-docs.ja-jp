---
title: "Win32 Predefined Symbols | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Win32 [C++], predefined symbols"
  - "symbols, Win32 predefined"
  - "Windows API [C++], predefined symbols"
ms.assetid: 45c8e193-ee2a-4024-bfc2-34d1ec9c9239
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Win32 Predefined Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

以下に示すシンボルは Win32 ヘッダー ファイルに定義されており、標準の Windows アプリケーションの関数とアクションをサポートします。  これらのシンボルは主に共通の UI 要素で使用されます。  リソース エディターでコントロールを扱う場合は、これらのシンボルはコモン コントロールに関連付けられて、[&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)に表示されます。  たとえば、アプリケーション アイコンがツール バーに表示される場合、そのアイコンは \[プロパティ\] ウィンドウのシンボル IDI\_SMALL に関連付けられます。  
  
|||  
|-|-|  
|IDABORT|コントロール : ダイアログ ボックスの \[中止\] ボタン|  
|IDC\_STATIC|コントロール : ダイアログ ボックスの静的テキスト|  
|IDCANCEL|コントロール : ダイアログ ボックスの \[キャンセル\] ボタン|  
|IDD\_ABOUTBOX|ダイアログ : \[バージョン情報\] ダイアログ ボックス|  
|IDI\_PROJECTNAME|アイコン : 現在のプロジェクトのアイコン|  
|IDI\_SMALL|アイコン : 現在のプロジェクトの小さいアイコン|  
|IDIGNORE|コントロール : ダイアログ ボックスの \[無視\] ボタン|  
|IDM\_ABOUT|メニュー項目 : \[ヘルプ\] メニューの \[バージョン情報\]|  
|IDM\_EXIT|メニュー項目 : \[ファイル\] メニューの \[終了\]|  
|IDNO|コントロール : ダイアログ ボックスの \[いいえ\] ボタン|  
|IDOK|コントロール : ダイアログ ボックスの \[OK\] ボタン|  
|IDRETRY|コントロール : ダイアログ ボックスの \[再試行\] ボタン|  
|IDS\_APP\_TITLE|文字列 : 現在のアプリケーション名|  
|IDYES|コントロール : ダイアログ ボックスの \[はい\] ボタン|  
  
## 要件  
 Win32  
  
## 参照  
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)