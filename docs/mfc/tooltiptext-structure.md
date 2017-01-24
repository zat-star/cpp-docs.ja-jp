---
title: "TOOLTIPTEXT 構造体 | Microsoft Docs"
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
  - "TOOLTIPTEXT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ツール ヒント [C++], 通知"
  - "TOOLTIPTEXT 構造体"
ms.assetid: 547591bf-80f5-400e-a2a7-0708cfffbb5d
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TOOLTIPTEXT 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[ツール ヒントの通知ハンドラー](../Topic/Handling%20TTN_NEEDTEXT%20Notification%20for%20Tool%20Tips.md)を作成すると、`TOOLTIPTEXT` 構造体を使用する必要があります。  `TOOLTIPTEXT`構造体のメンバーは、次の操作:  
  
 `typedef struct {`  
  
 `NMHDR     hdr;        // required for all WM_NOTIFY messages`  
  
 `LPTSTR    lpszText;   // see below`  
  
 `TCHAR     szText[80]; // buffer for tool tip text`  
  
 `HINSTANCE hinst;      // see below`  
  
 `UINT      uflags;     // flag indicating how to interpret the`  
  
 `// idFrom member of the NMHDR structure`  
  
 `// that is included in the structure`  
  
 `} TOOLTIPTEXT, FAR *LPTOOLTIPTEXT;`  
  
 `hdr`  
 テキストを必要とするツールを指定します。  必要となるこの構造体のメンバーは、コントロールの ID です。  コントロールの ID は、構文 `hdr.idFrom`とアクセスされた `NMHDR` 構造体の `idFrom` のメンバーです。  `NMHDR` 構造体のメンバーの説明の [NMHDR](http://msdn.microsoft.com/library/windows/desktop/bb775514) を参照してください。  
  
 `lpszText`  
 ツールのテキストを受け取る文字列のアドレス。  
  
 `szText`  
 バッファリングします。ツールヒント テキストを受け取る。  アプリケーションは文字列のアドレス指定にこのバッファーにテキストを代替コピーできます。  
  
 `hinst`  
 ツールヒント テキストとして使用される文字列を含むインスタンスのハンドル。  `lpszText` がツールヒント テキストのアドレスは、このメンバーは null です。  
  
 `TTN_NEEDTEXT` の通知メッセージを処理するときは、次の方法で 1 つに表示する文字列を指定する:  
  
-   `szText` のメンバーで指定されたバッファーにテキストをコピーします。  
  
-   `lpszText` のメンバーにテキストを含むバッファーのアドレスをコピーします。  
  
-   文字列リソースの識別子を `lpszText` のメンバーにコピーし、`hinst` のメンバーにリソースを含むインスタンス ハンドルをコピーします。  
  
## 参照  
 [CFrameWnd から派生していないウィンドウのツール ヒント](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)