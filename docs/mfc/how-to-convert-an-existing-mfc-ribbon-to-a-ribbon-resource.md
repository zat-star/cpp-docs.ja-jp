---
title: "方法: 既存の MFC リボンをリボン リソースに変換する | Microsoft Docs"
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
  - "MFC リボン, 変換 (リボン リソースに)"
  - "リボン リソース, 変換 (MFC リボンから)"
ms.assetid: 324b7ff6-58f9-4691-96a9-9836a79d0fb6
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 4
---
# 方法: 既存の MFC リボンをリボン リソースに変換する
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リボン リソースは、手動でコード化されたリボンよりも、簡単に視覚化、変更、および管理できます。  ここでは、MFC プロジェクト内に手動でコード化されたリボンをリボン リソースに変換する方法について説明します。  
  
 MFC リボン クラス \([CMFCRibbonBar クラス](../mfc/reference/cmfcribbonbar-class.md)など\) を使用するコードを含む既存の MFC プロジェクトが存在する必要があります。  
  
### MFC リボンをリボン リソースに変換するには  
  
1.  Visual Studio で、既存の MFC プロジェクトにおいて、CMFCRibbonBar オブジェクトが初期化されるソース ファイルを開きます。  通常、このファイルは mainfrm.cpp です。  リボンの初期化コードの後に次のコードを追加します。  
  
    ```  
    m_wndRibbonBar.SaveToXMLFile("RibbonOutput.xml");  
    ```  
  
     ファイルを保存して閉じます。  
  
2.  MFC アプリケーションをビルドして実行した後、メモ帳で RibbonOutput.txt を開き、その内容をコピーします。  
  
3.  Visual Studio で、**\[プロジェクト\]** メニューの **\[リソースの追加\]** をクリックします。  **\[リソースの追加\]** ダイアログ ボックスで、**\[Ribbon\]** を選択し、**\[新規作成\]** をクリックします。  
  
     Visual Studio でリボン リソースが作成され、デザイン ビューで開かれます。  リボン リソース ID は IDR\_RIBBON1 です。これはリソース ビューに表示されます。  リボンは ribbon1.mfcribbon\-ms XML ファイルの中に定義されます。  
  
4.  Visual Studio で、ribbon1.mfcribbon\-ms を開き、その内容を削除します。次に、コピーしておいた  RibbonOutput.txt の内容を貼り付けます。  ribbon1.mfcribbon\-ms を保存して閉じます。  
  
5.  CMFCRibbonBar オブジェクトが初期化されるソース ファイル \(通常は mainfrm.cpp\) を再度開き、既存のリボン コードをコメント アウトします。  コメント アウトしたコードの後に次のコードを追加します。  
  
    ```  
    m_wndRibbonBar.LoadFromResource(IDR_RIBBON1);  
    ```  
  
6.  プロジェクトをビルドしてプログラムを実行します。  
  
## 参照  
 [リボン デザイナー \(MFC\)](../mfc/ribbon-designer-mfc.md)