---
title: "方法: リボン コントロールとイベント ハンドラーを追加する | Microsoft Docs"
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
  - "イベント ハンドラー, 追加"
  - "リボン コントロール, 追加"
ms.assetid: b31f25bc-ede7-49c3-9e3c-dffe4e174a69
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# 方法: リボン コントロールとイベント ハンドラーを追加する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リボン コントロールは、ボタンやコンボ ボックスなど、パネルに追加する要素です。  パネルは、関連するコントロールのグループが表示されるリボン バーの領域です。  
  
 このトピックでは、リボン デザイナーを開き、ボタンを追加して、"Hello World" を表示するイベントをリンクします。  
  
### リボン デザイナーを開くには  
  
1.  Visual Studio で、**\[表示\]** メニューの **\[リソース ビュー\]** をクリックします。  
  
2.  **\[リソース ビュー\]** でリボン リソースをダブルクリックして、デザイン サーフェイスに表示します。  
  
### ボタンとイベント ハンドラーを追加するには  
  
1.  **ツール バー**の **\[Button\]** をクリックし、デザイン サーフェイスのパネルにドラッグします。  
  
2.  ボタンを右クリックし、**\[イベント ハンドラーの追加\]** をクリックします。  
  
3.  **イベント ハンドラー ウィザード**で、既定の設定を確認し、**\[追加と編集\]** をクリックします。  詳細については、「[イベント ハンドラー ウィザード](../ide/event-handler-wizard.md)」を参照してください。  
  
4.  コード エディターで、ハンドラー関数に次のコードを追加します。  
  
    ```  
    MessageBox((LPCTSTR)L"Hello World");  
    ```  
  
## 参照  
 [RibbonGadgets サンプル : Ribbon Gadgets アプリケーション](../top/visual-cpp-samples.md)   
 [リボン デザイナー \(MFC\)](../mfc/ribbon-designer-mfc.md)