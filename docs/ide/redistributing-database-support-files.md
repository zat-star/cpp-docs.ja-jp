---
title: "データベース サポート ファイルの再頒布 | Microsoft Docs"
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
  - "データベース サポート ファイル [C++], 再配布"
  - "再配布 (データベース サポート ファイル)"
ms.assetid: d80cffe0-177c-4515-9de7-fbf0517eb8d6
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# データベース サポート ファイルの再頒布
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

データ アクセス オブジェクト \(DAO: Data Access Object\) 用のサポート ファイルの再配布、および Microsoft Data Access SDK のデータベース テクノロジのサポート ファイルの再配布が可能です。  
  
## DAO サポート ファイルのインストール  
 DAO の最新バージョンを入手する方法については、マイクロソフト サポート オンラインの「[文書番号 239114: Microsoft Jet 4.0 データベース エンジン用の最新の Service Pack の入手方法](http://go.microsoft.com/fwlink/?LinkId=198014)」を参照してください。  
  
## Microsoft Data Access SDK のサポート ファイル  
 Mdac\_typ.exe を使用して、ODBC、OLE DB、ActiveX データ オブジェクト \(ADO: ActiveX Data Object\)、および RDS \(Remote Data Services\) に対するサポートをインストールします。  Mdac\_typ.exe は、Visual Studio インストール メディアの \\WCU\\MDAC28\\ フォルダーにあります。  Mdac\_typ.exe は、[Microsoft ダウンロード センター](http://go.microsoft.com/fwlink/?LinkId=198015)の Web サイトからもダウンロードできます。  
  
 詳細については、[MSDN](http://go.microsoft.com/fwlink/?LinkId=198016) Web サイトで、"Redistributing MDAC 2.8 SP1" を検索してください。  Visual Studio セットアップ プロジェクトを使用してアプリケーションを配置する場合は、「[Deployment and Dependencies](http://msdn.microsoft.com/ja-jp/49e9b84d-bd6a-4388-b9ac-46ea79cf0733)」を参照してください。  
  
## 参照  
 [Visual C\+\+ ファイルの再配布](../Topic/Redistributing%20Visual%20C++%20Files.md)