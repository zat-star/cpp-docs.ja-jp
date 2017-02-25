---
title: "ATL Predefined Symbols | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, ATL predefined"
  - "ATL symbols"
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL Predefined Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

以下に示すシンボルは ATL ヘッダー ファイルに定義されていますが、標準の Windows アプリケーションの関数とアクションをサポートします。  これらのシンボルは主にダイアログ ボックスで使用されます。  [ダイアログ エディター](../mfc/dialog-editor.md)でダイアログ ボックスとコントロールを扱う場合は、これらのシンボルはコモン コントロールに関連付けられて、\[プロパティ\] ウィンドウに表示されます。  たとえば、ダイアログ ボックスに \[キャンセル\] ボタンがある場合、そのコマンドは [&#91;プロパティ&#93; ウィンドウ](../Topic/Properties%20Window.md)のシンボル IDCANCEL に関連付けられます。  
  
|||  
|-|-|  
|IDABORT|コントロール : ダイアログ ボックスの \[中止\] ボタン|  
|IDC\_STATIC|コントロール : 静的コントロール|  
|IDCANCEL|コントロール : ダイアログ ボックスの \[キャンセル\] ボタン|  
|IDIGNORE|コントロール : ダイアログ ボックスの \[無視\] ボタン|  
|IDNO|コントロール : ダイアログ ボックスの \[いいえ\] ボタン|  
|IDOK|コントロール : ダイアログ ボックスの \[OK\] ボタン|  
|IDR\_ACCELERATOR1|リソース : アクセラレータ テーブル|  
|IDRETRY|コントロール : ダイアログ ボックスの \[再試行\] ボタン|  
|IDS\_PROJNAME|文字列 : 現在のアプリケーション名|  
|IDYES|コントロール : ダイアログ ボックスの \[はい\] ボタン|  
  
## 要件  
 ATL  
  
## 参照  
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)