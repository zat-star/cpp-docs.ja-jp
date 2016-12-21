---
title: "CDaoWorkspace クラス | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoWorkspace"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoWorkspace クラス"
  - "DAO ワークスペース [C++]"
  - "DAO ワークスペース [C++], CDaoWorkspace クラス"
  - "データベース エンジン [C++], アクセス (ワークスペースを通じた)"
  - "DDLs [C++]"
  - "既定のワークスペース [C++]"
  - "既定のワークスペース [C++], DAO"
  - "既定 [C++], ワークスペース"
  - "ODBC クラス [C++], および DAO クラス"
  - "永続化 [C++], DAO ワークスペース"
  - "セキュリティ [MFC]"
  - "セキュリティ [MFC], DAO ワークスペース"
  - "セッション [C++], DAO ワークスペース"
  - "トランザクション空間 [C++]"
  - "トランザクション空間 [C++], DAO ワークスペース"
  - "Workspace クラス"
  - "ワークスペース [C++], DAO"
  - "ワークスペース [C++], default"
  - "ワークスペース [C++], インターフェイス (データベース エンジンに対する)"
  - "ワークスペース [C++], 永続化"
  - "Workspaces コレクション"
ms.assetid: 64f60de6-4df1-4d4a-a65b-c489b5257d52
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoWorkspace クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

シングル ユーザーによる名前付きの、パスワードで保護されたデータベース セッションのログインからログオフまでを管理します。  
  
## 構文  
  
```  
class CDaoWorkspace : public CObject  
```  
  
## メンバー  
  
### パブリック コンストラクター  
  
|名前|説明|  
|--------|--------|  
|[CDaoWorkspace::CDaoWorkspace](../Topic/CDaoWorkspace::CDaoWorkspace.md)|ワークスペース オブジェクトを構築します。  その後、呼び出し **\[作成\]** か **\[開く\]**。|  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[CDaoWorkspace::Append](../Topic/CDaoWorkspace::Append.md)|データベース エンジンのワークスペースのコレクションに新しく作成されたワークスペースを追加します。|  
|[CDaoWorkspace::BeginTrans](../Topic/CDaoWorkspace::BeginTrans.md)|ワークスペースで開いているすべてのデータベースに適用する新しいトランザクションを開始します。|  
|[CDaoWorkspace::Close](../Topic/CDaoWorkspace::Close.md)|ワークスペースと含むオブジェクトをすべて閉じます。  保留中のトランザクション転がされます。|  
|[CDaoWorkspace::CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md)|現在のトランザクションが終了し、変更内容を保存します。|  
|[CDaoWorkspace::CompactDatabase](../Topic/CDaoWorkspace::CompactDatabase.md)|\(または\) 複製データベースを最適化します。|  
|[CDaoWorkspace::Create](../Topic/CDaoWorkspace::Create.md)|新しい DAO のワークスペース オブジェクトを作成します。|  
|[CDaoWorkspace::GetDatabaseCount](../Topic/CDaoWorkspace::GetDatabaseCount.md)|ワークスペースのデータベースのコレクションの DAO データベース オブジェクトの数を返します。|  
|[CDaoWorkspace::GetDatabaseInfo](../Topic/CDaoWorkspace::GetDatabaseInfo.md)|ワークスペースのデータベースのコレクションで定義される指定した DAO データベースに関する情報を返します。|  
|[CDaoWorkspace::GetIniPath](../Topic/CDaoWorkspace::GetIniPath.md)|Windows レジストリの Microsoft Jet データベース エンジンの初期化の設定の場所を返します。|  
|[CDaoWorkspace::GetIsolateODBCTrans](../Topic/CDaoWorkspace::GetIsolateODBCTrans.md)|データ ソースへの強制変換、複数のコネクションから独立している同一の ODBC データ ソースを含む複数のトランザクションかどうかを示す値を返します。|  
|[CDaoWorkspace::GetLoginTimeout](../Topic/CDaoWorkspace::GetLoginTimeout.md)|ユーザーが ODBC データベースにログインしようとしたときにエラーが発生するまでの秒数を返します。|  
|[CDaoWorkspace::GetName](../Topic/CDaoWorkspace::GetName.md)|ワークスペース オブジェクトのユーザー定義の名前を返します。|  
|[CDaoWorkspace::GetUserName](../Topic/CDaoWorkspace::GetUserName.md)|ワークスペースが作成されたときに指定されたユーザー名を返します。  これは、ワークスペースの所有者の名前です。|  
|[CDaoWorkspace::GetVersion](../Topic/CDaoWorkspace::GetVersion.md)|ワークスペースに関連付けられているデータベース エンジンのバージョンを含む文字列を返します。|  
|[CDaoWorkspace::GetWorkspaceCount](../Topic/CDaoWorkspace::GetWorkspaceCount.md)|データベース エンジンのワークスペースのコレクションの DAO のワークスペースのオブジェクトの数を返します。|  
|[CDaoWorkspace::GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md)|データベース エンジンのワークスペースのコレクションで定義される指定した DAO のワークスペースに関する情報を返します。|  
|[CDaoWorkspace::Idle](../Topic/CDaoWorkspace::Idle.md)|データベース エンジンでバックグラウンド タスクを実行するようにします。|  
|[CDaoWorkspace::IsOpen](../Topic/CDaoWorkspace::IsOpen.md)|ワークスペースが開いている場合は、を返します。|  
|[CDaoWorkspace::Open](../Topic/CDaoWorkspace::Open.md)|明示的に DAO の既定のワークスペースに関連付けられているワークスペース オブジェクトを開きます。|  
|[CDaoWorkspace::RepairDatabase](../Topic/CDaoWorkspace::RepairDatabase.md)|損なわれたデータベースを修復します。|  
|[CDaoWorkspace::Rollback](../Topic/CDaoWorkspace::Rollback.md)|現在のトランザクションが終了し、変更を保存しません。|  
|[CDaoWorkspace::SetDefaultPassword](../Topic/CDaoWorkspace::SetDefaultPassword.md)|ワークスペースのオブジェクトが特定のパスワードを指定せずに作成されるとデータベース エンジンで使用するパスワードを設定します。|  
|[CDaoWorkspace::SetDefaultUser](../Topic/CDaoWorkspace::SetDefaultUser.md)|ワークスペースのオブジェクトが特定のユーザー名を指定せずに作成されるとデータベース エンジンで使用するユーザー名を設定します。|  
|[CDaoWorkspace::SetIniPath](../Topic/CDaoWorkspace::SetIniPath.md)|Windows レジストリの Microsoft Jet データベース エンジンの初期化の設定の場所を設定します。|  
|[CDaoWorkspace::SetIsolateODBCTrans](../Topic/CDaoWorkspace::SetIsolateODBCTrans.md)|同じ ODBC データ ソースを含む複数のトランザクションがようにデータ ソースに対して複数の接続の強制変換によって分離するかを指定します。|  
|[CDaoWorkspace::SetLoginTimeout](../Topic/CDaoWorkspace::SetLoginTimeout.md)|ユーザーが ODBC データ ソースにログインしようとしたときにエラーが発生するまでの秒数を設定します。|  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CDaoWorkspace::m\_pDAOWorkspace](../Topic/CDaoWorkspace::m_pDAOWorkspace.md)|基になる DAO のワークスペース オブジェクトへのポインター。|  
  
## 解説  
 ほとんどの場合、複数のワークスペースを必要とせず、明示的なワークスペース オブジェクトを作成する必要はありません; データベースとレコードセット オブジェクトを開くと、DAO の既定のワークスペースを使用します。  ただし、必要に応じて、追加のワークスペースのオブジェクトを作成することによって、複数のセッションを同時に実行できます。  各ワークスペース オブジェクトは独自のデータベースのコレクションで複数の開いているデータベース オブジェクトを含めることができます。  MFC では、ワークスペースは同じです「トランザクション空間における開いているデータベースを指定する主にトランザクション マネージャー」。  
  
> [!NOTE]
>  DAO データベース クラスは、ODBC \(Open Database Connectivity\) に基づく MFC データベース クラスとは異なります。  すべての DAO データベース クラス名に「CDao」が付きます。  一般に、に基づく MFC DAO クラスは、ODBC に基づいて MFC クラスよりもできます。  DAO ベースのクラスは、ODBC ドライバーなどの Microsoft Jet データベース エンジンを使用してデータにアクセスします。  これらは、クラスによって DAO を直接呼び出さないでデータベースの作成、テーブル、およびフィールドの追加など、データ定義言語の \(DDL\)、操作をサポートします。  
  
## Capabilities  
 クラスは、次 `CDaoWorkspace` が用意されています:  
  
-   明示的なアクセス、必要に応じて、データベース エンジンの初期化で作成された既定のワークスペースへ。  通常使用 DAO の既定のワークスペース暗黙的にデータベースとレコードセット オブジェクトを作成する。  
  
-   トランザクションがワークスペースで開いているすべてのデータベースに適用するトランザクションの領域。  他のトランザクションの空間を管理するために追加のワークスペースを作成できます。  
  
-   基になる Microsoft Jet データベース エンジンの多くのプロパティへのインターフェイス \(静的メンバー関数を参照\)。  開くか作成する前に、ワークスペースまたは静的メンバー関数を呼び出してレコードを開くか作成して、データベース エンジンを初期化します。  
  
-   そのパスに追加されるすべてのアクティブなワークスペースを格納するデータベース エンジンのワークスペースのコレクションへのアクセス。  また、ワークスペースをコレクションに追加せずに作成して使用できます。  
  
## セキュリティ  
 MFC では、ユーザーを実装せず、機密管理に使用する DAO のコレクションをグループ化されません。  DAO の側面を必要とする場合は、独自の DAO インターフェイスに直接呼び出しによってプログラムする必要があります。  ついては、[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)を参照してください。  
  
## 使用方法  
 クラス `CDaoWorkspace` を使用する:  
  
-   明示的に既定のワークスペースを開きます。  
  
     通常、既定のワークスペースを使用すると、— [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) または [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) の新しいオブジェクトを開くと暗黙的です。  しかし、たとえば\) を明示的にアクセスし、データベース エンジンのプロパティまたはワークスペースのコレクションにアクセスする必要がある場合があります。  「既定のワークスペースの暗黙の使用」を参照してください。  
  
-   新しいワークスペースを作成します。  ワークスペースのコレクションに追加する場合は、[&#91;追加&#93;](../Topic/CDaoWorkspace::Append.md) を呼び出します。  
  
-   ワークスペースのコレクションの既存のワークスペースを開きます。  
  
 ワークスペースのコレクションにない新しいワークスペースを作成することは [&#91;作成&#93;](../Topic/CDaoWorkspace::Create.md) のメンバー関数の下で説明します。  ワークスペース オブジェクトは datababase エンジンのセッションの間に任意の方法で保持されません。  アプリケーションのリンクの MFC と静的に、アプリケーションを終了データベース エンジンを uninitializes。  MFC DLL がアンロードされたときの MFC アプリケーションのリンクが動的に、データベース エンジン初期化されていない場合は。  
  
 明示的に既定のワークスペースを開くか、ワークスペース コレクションの既存のワークスペースを開くには [&#91;開く&#93;](../Topic/CDaoWorkspace::Open.md) のメンバー関数では、示します。  
  
 [&#91;閉じる&#93;](../Topic/CDaoWorkspace::Close.md) のメンバー関数のワークスペースを閉じることで、ワークスペースのセッションを終了します。  **\[閉じる\]** は、以前に閉じていないデータベースを閉しました、変更されていないトランザクションをロールバックされます。  
  
## トランザクション  
 DAO はワークスペースのレベルでトランザクションを管理します; したがって、複数の開いているデータベースを使用して、ワークスペースのトランザクションは、データベースすべてに適用されます。  たとえば、2 種類のデータベースに対するいない更新プログラムがあり、[CommitTrans](../Topic/CDaoWorkspace::CommitTrans.md)を呼び出すと、更新はすべてコミットされます。  一つのデータベースにトランザクションを制限する場合は、の別のワークスペースのオブジェクトが必要です。  
  
## 既定のワークスペースの暗黙の使用  
 MFC の DAO 使用の既定のワークスペース暗黙的に次の場合:  
  
-   `CDaoDatabase` の新しいオブジェクトを作成しますが、`CDaoWorkspace` の既存のオブジェクトを使用しない場合は、MFC DAO の既定のワークスペースに対応する一時的なワークスペース オブジェクトを作成します。  複数のデータベースに対してすると、データベース オブジェクトはすべて、既定のワークスペースに関連付けられます。  `CDaoDatabase` のデータ メンバーを通じてデータベースのワークスペースにアクセスできます。  
  
-   同様に `CDaoDatabase` オブジェクトへのポインターを指定せず `CDaoRecordset` のオブジェクトを作成する場合、MFC は、拡張子によって、一時データベース オブジェクトとワークスペースの一時的なオブジェクトを作成します。  `CDaoRecordset` のデータ メンバーを通じてレコードセットのデータベースや間接的にワークスペースにアクセスできます。  
  
## 他の操作  
 他のデータベース操作は、破損したデータベースを修復またはデータベースを最適化することなど、に用意されます。  
  
 DAO を直接呼び出すことと DAO のセキュリティについては、[テクニカル ノート 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md)を参照してください。  
  
## 継承階層  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CDaoWorkspace`  
  
## 必要条件  
 **Header:** afxdao.h  
  
## 参照  
 [CObject クラス](../Topic/CObject%20Class.md)   
 [階層図](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase クラス](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset クラス](../../mfc/reference/cdaorecordset-class.md)   
 [CDaoTableDef クラス](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef クラス](../../mfc/reference/cdaoquerydef-class.md)   
 [CDaoException クラス](../../mfc/reference/cdaoexception-class.md)