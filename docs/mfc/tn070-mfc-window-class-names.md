---
title: "テクニカル ノート 70: MFC のウィンドウ クラス名 | Microsoft Docs"
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
  - "vc.mfc.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TN070"
  - "ウィンドウ クラス名"
ms.assetid: 90617912-dd58-4a7c-9082-ced71736d7cd
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 70: MFC のウィンドウ クラス名
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  次のテクニカル ノートは、最初にオンライン ドキュメントの一部とされてから更新されていません。  結果として、一部のプロシージャおよびトピックが最新でないか、不正になります。  最新の情報について、オンライン ドキュメントのキーワードで関係のあるトピックを検索することをお勧めします。  
  
 MFC ウィンドウはウィンドウの機能を反映し、動的に作成されたクラス名を使用します。  MFC は、フレーム ウィンドウ、アプリケーションで作成されるビューおよびポップアップ ウィンドウのクラス名を動的に生成します。  MFC アプリケーションで生成されたダイアログ ボックスとコントロールに対象のウィンドウのウィンドウ クラスの指定された名前があります。  
  
 独自のウィンドウ クラスを登録し、[PreCreateWindow](../Topic/CWnd::PreCreateWindow.md)のオーバーライドで使用すると、指定したクラス名を置き換えることができます。  MFC から提供されるクラス名は 2 個の後続のフォームの 1 つがに含めます:  
  
```  
Afx:%x:%x  
Afx:%x:%x:%x:%x:%x  
```  
  
 `%x` の文字を置き換える十六進数字が [WNDCLASS](http://msdn.microsoft.com/library/windows/desktop/ms633576) 構造体のデータが格納されます。  MFC は **WNDCLASS** の構造を必要とする複数の C\+\+ クラスが同じ登録されたウィンドウ クラスを共有できるように、この方法を使用します。  最も単純な Win32 アプリケーションとは異なり、MFC アプリケーションに 1 **WNDPROC**のみであるため、簡単に時間とメモリを節約するために **WNDCLASS** 構造体を共有できます。  上記の `%x` の文字の置き換え可能な値は次のとおりです。:  
  
-   **WNDCLASS.hInstance**  
  
-   **WNDCLASS.style**  
  
-   **WNDCLASS.hCursor**  
  
-   **WNDCLASS.hbrBackground**  
  
-   **WNDCLASS.hIcon**  
  
 **hCursor**、**hbrBackground**と **hIcon** がすべての **NULL**の場合、最初のフォーム \(`Afx:%x:%x`\) が使用されます。  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)   
 [テクニカル ノート 20: ID 名および番号に関する規約](../mfc/tn020-id-naming-and-numbering-conventions.md)