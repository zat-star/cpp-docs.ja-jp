---
title: "ODBC 接続 | Microsoft Docs"
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
  - "ODBC 接続, 構成"
  - "ODBC, 接続"
ms.assetid: c9df2fa6-d9e2-4335-b885-724662968691
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# ODBC 接続
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ODBC 接続は、システムのコントロール パネルで設定します。  ODBC 接続は、ODBC ドライバーがインストールされているデータ ソースに対して設定できます。  Visual C\+\+ 6.0 以降には、テキスト ファイル、Access、Paradox、dBASE、Excel、SQL Server、および Oracle 用のドライバーが組み込まれています。  ODBC 接続を作成すると、データ ソース名 \(DSN: Data Source Name\) が自動的に設定されます。  ADO データ コントロールや RDO RemoteData コントロールなどのデータ コントロールでは、この DSN によって接続が識別されます。  
  
 **OLE DB 接続** OLE DB 接続の設定は、特に必要ありません。  たとえば、ODBC データ ソースを作成すると、ODBC 用の OLE DB プロバイダーがこのデータ ソースを自動的に検出します。  
  
### ODBC データ ソースを設定するには  
  
1.  **\[スタート\]** メニューの **\[設定\]** をポイントし、**\[コントロール パネル\]** をクリックします。  
  
2.  コントロール パネルで、32 ビット ODBC \(Windows 95 または Windows 98\) か ODBC \(Windows NT または Windows 2000\) を選択します。  
  
3.  \[ユーザー DSN\] タブまたは \[システム DSN\] タブをクリックします。  **\[ユーザー DSN\]** タブでは、ユーザー固有のデータ ソース名を作成できます。**\[システム DSN\]** では、すべてのユーザーが使用できるデータ ソースを作成できます。  
  
4.  **\[追加\]** をクリックします。ローカルにインストールされている ODBC ドライバーが一覧表示されます。  
  
5.  接続するデータベースまたは ISAM \(Indexed Sequential Access Method\) の種類に応じてドライバーを選択し、\[完了\] をクリックします。  
  
6.  ドライバー固有の手順に従います。  ODBC の設定を終了すると、DSN を使用できるようになります。  
  
 一部の ODBC ドライバーでは、DSN を作成するときに、実際のファイルの格納場所を指定する必要があります。  たとえば、Access DSN を作成する場合は、.mdb ファイルの格納場所を指定する必要があります。  また、有効なユーザー名とパスワードの入力が必要です。  たとえば、ほとんどの Access システムでは、システム ユーザー名として *admin* が使用されます。  
  
 [Oracle](../../data/ado-rdo/oracle-connections.md) DSN を作成する場合は、SQL\*Net 接続文字列を指定する必要があります。  
  
## 参照  
 [データベース接続を作成する](../Topic/Creating%20Database%20Connections.md)