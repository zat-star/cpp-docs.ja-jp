---
title: "フレーム ウィンドウ スタイル (MFC) | Microsoft Docs"
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
  - "FWS_ADDTOTITLE"
  - "FWS_SNAPTOBARS"
  - "FWS_PREFIXTITLE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "フレーム ウィンドウ, スタイル"
  - "FWS_ADDTOTITLE 定数"
  - "FWS_PREFIXTITLE 定数"
  - "FWS_SNAPTOBARS 定数"
  - "スタイル, ウィンドウ"
ms.assetid: d21f270e-a088-4962-a2ae-8c03334b5a06
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# フレーム ウィンドウ スタイル (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **FWS\_ADDTOTITLE**は、フレーム ウィンドウのタイトルの末尾に追加する情報を指定します。  たとえば、「Microsoft 描画\- Document1 の描画」。  アプリケーション ウィザードのドキュメント テンプレート文字列タブに表示される文字列を指定できます。  このオプションをオフにする必要がある場合 `CWnd::PreCreateWindow` のメンバー関数をオーバーライドします。  
  
-   **FWS\_PREFIXTITLE**がフレーム ウィンドウのタイトルにアプリケーション名の前にドキュメント名を示します。  たとえば、「ドキュメント\- WordPad」。  アプリケーション ウィザードのドキュメント テンプレート文字列タブに表示される文字列を指定できます。  このオプションをオフにする必要がある場合 `CWnd::PreCreateWindow` のメンバー関数をオーバーライドします。  
  
-   フレーム ウィンドウにドッキングされるのではなく、フローティング ウィンドウである場合にコントロール バーを囲むフレーム ウィンドウの**FWS\_SNAPTOBARS** のコントロールのサイズ変更。  このスタイルは、コントロール バーに収まるようにウィンドウのサイズを変更します。  
  
## 参照  
 [MFC で使用するスタイル](../../mfc/reference/styles-used-by-mfc.md)