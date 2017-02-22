---
title: "方法: MFC アプリケーションからリボン リソースを読み込む | Microsoft Docs"
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
  - "リボン リソース, 読み込み"
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# 方法: MFC アプリケーションからリボン リソースを読み込む
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

アプリケーションでリボン リソースを使用するには、リボン リソースを読み込むようにアプリケーションを変更します。  
  
### リボン リソースを読み込むには  
  
1.  `CMainFrame` クラス内に、`Ribbon Control` オブジェクトを宣言します。  
  
    ```  
    CMFCRibbonBar m_wndRibbonBar;   
    ```  
  
2.  `CMainFrame::OnCreate` で、リボン コントロールを作成し、初期化します。  
  
    ```  
    if (!m_wndRibbonBar.Create (this))  
    {  
        return -1;  
    }  
  
    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))  
    {  
        return -1;  
    }  
    ```  
  
## 参照  
 [リボン デザイナー \(MFC\)](../mfc/ribbon-designer-mfc.md)