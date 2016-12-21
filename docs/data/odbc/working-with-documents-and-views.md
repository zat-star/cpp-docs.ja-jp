---
title: "ドキュメントとビューの使用 | Microsoft Docs"
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
  - "ドキュメント [C++], MFC"
  - "MFC [C++], ドキュメント"
  - "MFC [C++], ビュー"
  - "ビュー [C++], MFC"
ms.assetid: 349b142d-1c5a-4b99-9de4-241e41d3d2f1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ドキュメントとビューの使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC \(Microsoft Foundation Class\) ライブラリは、ドキュメント\/ビュー アーキテクチャを基本としてその多くの機能を実現しています。  通常、ビューは、ドキュメントが格納したデータをフレーム ウィンドウのクライアント領域内に表示してユーザーと対話します。  ビューは、ドキュメントと通信してデータの取得や更新を行います。  データベース クラスは、フレームワークなしでも使えます。  
  
 データベース クラスをフレームワークで使用する方法の詳細については、「[MFC : ドキュメントとビューを用いたデータベース クラスの使用](../../data/mfc-using-database-classes-with-documents-and-views.md)」を参照してください。  
  
 MFC アプリケーション ウィザードが既定で作成するスケルトン アプリケーションには、データベースのサポートがありません。  ただし、オプションを選択して、最小限のデータベースのサポートや完全なフォーム ベースのデータベースのサポートを追加できます。  アプリケーション ウィザードのオプションの詳細については、「[&#91;データベース サポート&#93; \(MFC アプリケーション ウィザード\)](../../mfc/reference/database-support-mfc-application-wizard.md)」を参照してください。  
  
 データベース クラスは、ドキュメント\/ビュー アーキテクチャなしでも使えます。  詳細については、「[MFC : ドキュメントとビューを用いないデータベース クラスの使用](../../data/mfc-using-database-classes-without-documents-and-views.md)」を参照してください。  
  
## 参照  
 [ODBC と MFC](../../data/odbc/odbc-and-mfc.md)