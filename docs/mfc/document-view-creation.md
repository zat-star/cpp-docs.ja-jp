---
title: "ドキュメントおよびビューの作成 | Microsoft Docs"
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
  - "ドキュメント/ビュー アーキテクチャ, 作成 (ドキュメント/ビューを)"
  - "ドキュメント, 作成"
  - "MFC, ドキュメント"
  - "MFC, ビュー"
  - "オブジェクトの作成内容"
  - "テーブル [C++]"
  - "テーブル [C++], オブジェクト (各 MFC オブジェクトが作成する)"
  - "ビュー, およびフレーム ウィンドウ"
  - "ビュー, 作成"
ms.assetid: bda14f41-ed50-439d-af9e-591174e7dd64
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ドキュメントおよびビューの作成
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

フレームワークは **ファイル** メニューの `New` と **開く** コマンドの実装 \(特に\) 指定します。  新規ドキュメントの作成、および関連付けられたフレーム ウィンドウとビュー アプリケーション オブジェクト、ドキュメント テンプレート、新しく作成されたドキュメントと新しく作成されたフレーム ウィンドウ内で協調工数です。  オブジェクトが作成される内容を次の表に示します。  
  
### オブジェクトの作成者  
  
|Creator|作成します。|  
|-------------|------------|  
|Application オブジェクト|ドキュメント テンプレート|  
|ドキュメント テンプレート|Document|  
|ドキュメント テンプレート|フレーム ウィンドウ|  
|フレーム ウィンドウ|ビュー|  
  
## 参照  
 [ドキュメント テンプレートとドキュメント\/ビューの作成手順](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [ドキュメント テンプレートの作成](../Topic/Document%20Template%20Creation.md)   
 [各種 MFC オブジェクト間の関係](../mfc/relationships-among-mfc-objects.md)   
 [新しいドキュメント、ウィンドウ、ビューの作成](../Topic/Creating%20New%20Documents,%20Windows,%20and%20Views.md)