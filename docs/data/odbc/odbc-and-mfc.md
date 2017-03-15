---
title: "ODBC と MFC | Microsoft Docs"
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
  - "接続 [C++], データ ソース"
  - "接続 [C++], データベース"
  - "データ ソース [C++], 接続"
  - "データベース接続 [C++], MFC ODBC クラス"
  - "データベース [C++], 接続"
  - "MFC [C++], ODBC および"
  - "ODBC [C++], MFC"
ms.assetid: 98f02fd7-1235-437b-89a9-edfd0fc797f7
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# ODBC と MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Windows NT などの Win32 プラットフォームを対象としたアプリケーションで MFC データベース クラスを使用するには、データ ソースに適切な ODBC ドライバーが必要です。  Visual C\+\+ に付属していないドライバーは、Microsoft や他社から入手することになります。  詳細については、「[ODBC ドライバーの一覧](../../data/odbc/odbc-driver-list.md)」を参照してください。  
  
 このトピックでは、MFC \(Microsoft Foundation Class\) ライブラリの ODBC ベースのデータベース クラスに関する主要な概念を説明し、クラス相互のかかわりについて簡単に紹介します。  ODBC および MFC の詳細については、次のトピックを参照してください。  
  
-   [データ ソースへの接続](../../data/odbc/connecting-to-a-data-source.md)  
  
-   [レコードの選択と操作](../../data/odbc/selecting-and-manipulating-records.md)  
  
-   [フォームでのデータの表示と操作](../Topic/Displaying%20and%20Manipulating%20Data%20in%20a%20Form.md)  
  
-   [ドキュメントとビューの使用](../../data/odbc/working-with-documents-and-views.md)  
  
-   [ODBC や SQL へのアクセス](../../data/odbc/access-to-odbc-and-sql.md)  
  
-   [MFC ODBC クラスに関する詳細情報](../../data/odbc/further-reading-about-the-mfc-odbc-classes.md)  
  
 ODBC をベースとする MFC データベース クラスは、ODBC ドライバーを使えるすべてのデータベースへのアクセスを提供します。  ODBC を使うと、アプリケーションは、各種の異なるデータ形式や異なるローカルまたはリモート設定のデータにアクセスできます。  データベース管理システム \(DBMS\) が異なる場合でも、専用コードを記述する必要はありません。  ユーザーは、アクセスするデータに対応した ODBC ドライバーを使う限り、テーブルに格納されたデータを操作できます。  
  
## 参照  
 [ODBC \(Open Database Connectivity\)](../Topic/Open%20Database%20Connectivity%20\(ODBC\).md)