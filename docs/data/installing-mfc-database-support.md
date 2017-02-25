---
title: "MFC データベース サポートのインストール | Microsoft Docs"
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
  - "DAO [C++], インストール (コンポーネントを)"
  - "データベース [C++], インストール (データベース サポートを)"
  - "データベース [C++], MFC"
  - "インストール (DAO を)"
  - "インストール (ODBC を)"
  - "ODBC コンポーネント [C++], インストール"
  - "ODBC ドライバー [C++], インストール"
ms.assetid: a6c2fc84-9e0e-4f39-a464-0bcbc415b946
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# MFC データベース サポートのインストール
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

##  <a name="_core_odbc_drivers_installed"></a> ODBC ドライバーのインストール  
 セットアップ プログラムでは、以下の ODBC ドライバーがインストールされます。  
  
-   Microsoft Access ドライバー  
  
-   Microsoft dBASE ドライバー  
  
-   Microsoft Excel ドライバー  
  
-   Microsoft FoxPro VFP ドライバー  
  
-   Microsoft Visual FoxPro ドライバー  
  
-   Microsoft ODBC for Oracle ドライバー  
  
-   Microsoft Paradox ドライバー  
  
-   Microsoft Text ドライバー  
  
-   Microsoft SQL Server ドライバー  
  
 他のドライバーを取得する方法、および Visual C\+\+ のこのバージョンに含まれている ODBC ドライバー一覧については、「[ODBC ドライバーの一覧](../data/odbc/odbc-driver-list.md)」を参照してください。  
  
##  <a name="_core_odbc_sdk_components_installed"></a> ODBC SDK コンポーネントのインストール  
 Visual C\+\+ には、必要なヘッダー ファイル、ライブラリ、DLL、ツールなど、主要 ODBC コンポーネントが多数含まれています。  これらの主要コンポーネントの中には、ODBC データ ソースを設定するための ODBC データ ソース アドミニストレーター コントロール パネルや、ODBC ドライバー マネージャーがあります。  また、「[ODBC ドライバーのインストール](#_core_odbc_drivers_installed)」に示す多くの一般的な DBMS 用 ODBC ドライバーもあります。  
  
 ODBC SDK には、ODBC ドライバーの作成とテストのための追加情報とツールも用意されています。  Visual C\+\+ .NET では、ODBC SDK は Visual C\+\+ .NET インストール メディアに含まれていません。ODBC SDK は、Visual Studio .NET 必須コンポーネントにインストールされた [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] の一部として入手できます。  
  
##  <a name="_core_dao_sdk_components_installed"></a> DAO SDK コンポーネントのインストール  
  
> [!NOTE]
>  Microsoft は、新しいプロジェクトには OLE DB または ODBC を使用することをお勧めします。  DAO は、既存のアプリケーションを保守するためだけに使用します。  
  
 既定では、以下の DAO SDK コンポーネントがインストールされます。  
  
-   Microsoft Jet \(4.0 SP3\)  
  
-   Microsoft Jet \(3.x MDB\)  
  
-   Microsoft Jet \(1.x、2.x\)  
  
-   「[DAO と ODBC を使ってアクセスできるデータ ソース](../data/what-data-sources-can-i-access-with-dao-and-odbc-q.md)」の一覧にあるすべてのデータベース形式  
  
 Visual C\+\+ .NET では、DAO SDK は Visual Studio .NET 必須コンポーネントと共にインストールされます。  \\Jet\\Jetsetup.exe を実行します。  
  
> [!NOTE]
>  Microsoft は、Jet 4.0 Service Pack 3 \(Version 2927.04\) 以降を使用することをお勧めします。  Jet 4.0 Service Pack 3 は、Windows 2000 と Windows ME に付属しています。  このバージョンの Jet を使用すると、アプリケーションでテストする必要のある Jet のバージョンの数は少なくなります。  Windows XP で同梱される Jet のバージョンは異なる場合があります。  「[コントロールを再配布する](../Topic/Redistributing%20Controls.md)」の「コンポーネントの再配布に関する重要事項」を参照してください。  
  
 DAO SDK C\+\+ クラス、サンプル ファイル、Windows ヘルプ形式の DAO ヘルプ ファイルなど、ほかの DAO SDK コンポーネントをインストールするには、Visual C\+\+ 6.0 CD\-ROM の DAO SDK をインストールします。  
  
 OLE DB の更新やニュースについてのは、Universal Data Access Web サイトを参照してください [http:\/\/go.microsoft.com\/fwlink\/?LinkId\=121548](http://go.microsoft.com/fwlink/?LinkId=121548)。  
  
## 参照  
 [データ アクセス プログラミング \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)