---
title: "テクニカル ノート 54: MFC DAO クラス使用中の DAO の直接呼び出し | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.dao"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DAO (データ アクセス オブジェクト), および MFC"
  - "DAO (データ アクセス オブジェクト), 呼び出し (直接に)"
  - "DAO (データ アクセス オブジェクト), セキュリティ"
  - "MFC [C++], DAO および"
  - "パスワード [C++], 呼び出し (DAO を)"
  - "セキュリティ [MFC]"
  - "セキュリティ [MFC], DAO"
  - "TN054"
ms.assetid: f7de7d85-8d6c-4426-aa05-2e617c0da957
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テクニカル ノート 54: MFC DAO クラス使用中の DAO の直接呼び出し
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Visual C\+\+ .NET では、Visual C\+\+ 開発環境およびウィザードでは DAO はサポートされなくなりました \(DAO クラスは含まれているので、このクラスを使うことはできます\)。  Microsoft は、新しいプロジェクトに [OLE DB テンプレート](../Topic/OLE%20DB%20Templates.md) または [ODBC と MFC](../data/odbc/odbc-and-mfc.md) を使用することをお勧めします。  DAO は、既存のアプリケーションを保守するためだけに使用してください。  
  
 MFC DAO データベース クラスを使用すると、DAO を直接使用する必要がある状況になる場合があります。  通常、これはそうではありませんが、MFC の使用を組み合わせることが直接 DAO の呼び出しに使用すると、MFC DAO の直接呼び出しを簡単にする手段を提供するように、ヘルパーの機能を提供します。  MFC マネージ DAO オブジェクトのメソッドに直接 DAO を呼び出すと、数行のコードを必要とする必要があります。  MFC によって管理されない DAO オブジェクトを作成し、使用する必要がある場合は、実際にはオブジェクトの **リリース** を呼び出すことによって、より多くの作業を少しする必要があります。  このテクニカル ノートはヘルプへのヘルパーが実行できる操作と DAO OLE インターフェイスを使用する方法、および DAO を直接呼び出すことについてします。  最後に、ここではサンプリングされた関数を参照する DAO のセキュリティ機能の DAO を直接呼び出すことができます。  
  
## いつ DAO の直接呼び出しを行う。  
 DAO の直接呼び出すための一般的な状況はコレクションを更新する必要がある場合や、MFC でラップされない機能を実装している場合に発生します。  MFC には公開されない最も重要な機能はセキュリティがあります。  セキュリティ機能を実装し、DAO の場合は、ユーザーを使用する必要があり、グループを直接使用する。  セキュリティだけでなく、MFC でサポートされていない他の DAO 機能だけです。  これらは、DAO にレコードセットの複製とデータベースのレプリケーション機能、少数の後の追加があります。  
  
## DAO と MFC の実装の概要  
 MFC の DAO のラップすると、DAO を使用して詳細の多くの処理になり、小さいことを心配する必要はありません。  これは、OLE の初期化、DAO オブジェクト \(特にコレクション オブジェクト\) の作成と管理、エラー チェック、および提供する厳密に型指定された、簡単なインターフェイスが含まれます \(`BSTR` の **VARIANT** または引数なし\)。  まだ直接 DAO を呼び出して、これらの機能を利用できます。  コードは、MFC を内部的に依存することによって作成されたオブジェクトに対する **リリース** を直接 DAO の呼び出しによって呼び出され、インターフェイス ポインターは一切変更しないようにする必要があります。  たとえば、*すべての* 内部動作を理解していない場合、`CDaoRecordset` の開いているオブジェクトの **m\_pDAORecordset** のメンバーは変更しないでください。  ただし、フィールドのコレクションを取得する DAO を直接呼び出すために **m\_pDAORecordset** インターフェイスを使用できます。  この場合 **m\_pDAORecordset** のメンバーは変更されません。  オブジェクトを使い終わったら、fields コレクション オブジェクトの **リリース** を呼び出す必要があります。  
  
## DAO の呼び出しを容易にするヘルパーの説明  
 DAO を簡単に呼び出すことができるように用意されているヘルパーは、MFC DAO データベース クラスの内部で使用されているヘルパーです。  これらのヘルパーがリターン コードをチェックするために使用され、作成した DAO の直接呼び出し、記録のデバッグ出力が予想されるエラーをチェックし、必要に応じて適切な例外をスローします。  これら二つのヘルパーの 1 にマップする 4 とおりのマクロと 2 桁の基になるヘルパー関数があります。  最適な説明はコードを読み取ることです。  マクロを参照するに AFXDAO.H の **DAO\_CHECK**、**DAO\_CHECK\_ERROR**、**DAO\_CHECK\_MEM**と **DAO\_TRACE** を参照し DAOCORE.CPP の **AfxDaoCheck** と **AfxDaoTrace** を参照してください。  
  
## DAO OLE インターフェイスを使用します。  
 DAO オブジェクト階層の各オブジェクトの OLE インターフェイスは\\Program の Files\\Microsoft の Visual Studio .NET 2003\\VC7\\include のディレクトリにある DBDAOINT.H ヘッダー ファイルで定義されています。  これらのインターフェイスは、DAO の階層を処理できるようにするメソッドを提供します。  
  
 DAO インターフェイスのメソッドの多くには、`BSTR` オブジェクト \(OLE オートメーションで使用される期間プレフィックスが付けられた文字列\) を処理する必要があります。  `BSTR` オブジェクトは **VARIANT** のデータ型の中で一般にカプセル化されます。  MFC クラス `COleVariant` 自体は **VARIANT** のデータ型から継承します。  によって ANSI 形式または Unicode のプロジェクトをビルドするかどうか、DAO インターフェイスは ANSI 文字または Unicode `BSTR`s.を返します。  2 種類のマクロは、**V\_BSTR** と **V\_BSTRT**は、DAO インターフェイスが、予期される型の `BSTR` を取得するようにする場合に便利です。  
  
 **V\_BSTR** は `COleVariant`の **bstrVal** のメンバーを取得します。  このマクロは、通常は DAO インターフェイスのメソッドに `COleVariant` の内容を渡す必要がある場合に使用します。  次のコードは **V\_BSTR** マクロを使用する DAOUser DAO インターフェイスの 2 種類のメソッドの宣言と実際面の両方を持つ T:  
  
```  
COleVariant varOldName;  
COleVariant varNewName( _T("NewUser"), VT_BSTRT );  
  
// Code to assign pUser to a valid value omitted  
DAOUser *pUser = NULL;  
  
// These method declarations were taken from DBDAOINT.H  
// STDMETHOD(get_Name) (THIS_ BSTR FAR* pbstr) PURE;  
// STDMETHOD(put_Name) (THIS_ BSTR bstr) PURE;  
  
DAO_CHECK( pUser->get_Name( &V_BSTR ( &varOldName ) ));  
DAO_CHECK( pUser->put_Name( V_BSTR ( &varNewName ) ));  
```  
  
 アプリケーションで ANSI バージョンおよびアプリケーションの Unicode バージョンの Unicode `BSTR` をビルドする場合は `COleVariant` に ANSI `BSTR` が上の `COleVariant` のコンストラクターで指定された `VT_BSTRT` の引数を使用することに注意してください。  これは、DAO が予想どおりになります。  
  
 他のマクロは、**V\_BSTRT**は、ビルドの種類に応じて、`COleVariant` の ANSI 文字または Unicode **bstrVal** のメンバーを取得します \(ANSI 文字または Unicode\)。  次のコードは `CString`に `COleVariant``BSTR` から値を取得する方法を示しています。:  
  
```  
COleVariant varName( _T( "MyName" ), VT_BSTRT );  
CString str = V_BSTRT( &varName );  
```  
  
 `COleVariant`に格納されるそのほかの型を開くなどの手法とともに **V\_BSTRT** マクロは、DAOVIEW サンプルでは、表示されます。  具体的には、この変換は **CCrack::strVARIANT** のメソッドで実行されます。  このメソッドは `CString`のインスタンスに、可能な限り `COleVariant` の値を変換します。  
  
## DAO への直接呼び出しの例  
 状況は、基になる DAO のコレクション オブジェクトを更新する必要がある場合に発生することがあります。  通常、必要なことはありませんが、必要な場合は、単純なプロシージャです。  コレクションを更新する必要がある場合には、の新しいテーブル定義を作成する複数のユーザーによるマルチユーザー環境でアクティブになります。  この場合テーブル定義のコレクションは古くなる可能性があります。  コレクションを更新するには、特定のオブジェクトのコレクション **最新の情報に更新** のメソッドを呼び出して、エラーを確認するだけです:  
  
```  
DAO_CHECK( pMyDaoDatabase->  
    m_pDAOTableDefs->Refresh( ) );  
```  
  
 現在すべての DAO のコレクション オブジェクト インターフェイスが MFC DAO データベース クラスの非公開のな実装の詳細であることに注意してください。  
  
## DAO のセキュリティ機能の DAO を使用して直接  
 DAO データベース クラスは、MFC DAO のセキュリティ機能をラップしません。  DAO のセキュリティ機能を使用するには、DAO インターフェイスのメソッドを呼び出す必要があります。  次の関数のセットは、システム データベース、ユーザーのパスワードを変更します。  この関数は後で定義されている 3 つが他の関数。  
  
```  
void ChangeUserPassword( )  
{  
   // Specify path to the Microsoft Access  
   // system database  
   CString strSystemDB =   
     _T( "c:\\Program Files\\MSOffice\\access\\System.mdw" );  
  
   // Set system database before MFC initilizes DAO  
   // NOTE: An MFC module uses only one instance   
   // of a DAO database engine object. If you have   
   // called a DAO object in your application prior   
   // to calling the function below, you must call   
   // AfxDaoTerm to destroy the existing database   
   // engine object. Otherwise, the database engine   
   // object already in use will be reused, and setting  
   // a system datbase will have no effect.  
   //  
   // If you have used a DAO object prior to calling   
   // this function it is important that DAO be   
   // terminated with AfxDaoTerm since an MFC  
   // module only gets one copy of the database engine   
   // and that engine will be reused if it hasn't been   
   // terminated. In other words, if you do not call   
   // AfxDaoTerm and there is currently a database   
   // initialized, setting the system database will   
   // have no affect.  
  
   SetSystemDB( strSystemDB );  
  
   // User name and password manually added  
   // by using Microsoft Access  
   CString strUserName = _T( "NewUser" );  
   CString strOldPassword = _T( "Password" );  
   CString strNewPassword = _T( "NewPassword" );  
  
   // Set default user so that MFC will be able  
   // to log in by default using the user name and   
   // password from the system database  
   SetDefaultUser( strUserName, strOldPassword );  
  
   // Change the password. You should be able to  
   // call this function from anywhere in your   
   // MFC application  
   ChangePassword( strUserName, strOldPassword,   
                   strNewPassword );  
  
   .  
   .  
   .  
  
}  
```  
  
 次の 4 例の操作手順について説明します。:  
  
-   システム DAO データベース \(.MDW ファイル\) を設定します。  
  
-   既定のユーザーとパスワードを設定します。  
  
-   ユーザーのパスワードを変更します。  
  
-   .MDB ファイルのパスワードを変更します。  
  
### システム データベースの設定  
 アプリケーションで使用されるシステム データベースを設定するサンプリングされた関数を次に示します。  この関数は、他の DAO の呼び出しが行われる前に呼び出す必要があります。  
  
```  
// Set the system database that the   
// DAO database engine will use  
  
void SetSystemDB( CString & strSystemMDB )  
{  
   COleVariant varSystemDB( strSystemMDB, VT_BSTRT );  
  
   // Initialize DAO for MFC  
   AfxDaoInit( );  
   DAODBEngine* pDBEngine = AfxDaoGetEngine( );  
  
   ASSERT( pDBEngine != NULL );  
  
   // Call put_SystemDB method to set the   
   // system database for DAO engine  
   DAO_CHECK( pDBEngine->put_SystemDB( varSystemDB.bstrVal ) );  
}  
```  
  
### 既定のユーザーとパスワードの設定  
 システム データベースの既定のユーザーとパスワードを設定するには、次の関数を使用する:  
  
```  
void SetDefaultUser(CString & strUserName, CString & strPassword)  
{  
  COleVariant varUserName( strUserName, VT_BSTRT );  
  COleVariant varPassword( strPassword, VT_BSTRT );  
  
  DAODBEngine* pDBEngine = AfxDaoGetEngine( );  
  ASSERT( pDBEngine != NULL );  
  
  // Set default user:  
  DAO_CHECK( pDBEngine->put_DefaultUser( varUserName.bstrVal ) );  
  
  // Set default password:  
  DAO_CHECK( pDBEngine->put_DefaultPassword( varPassword.bstrVal ) );  
}  
```  
  
### ユーザーのパスワードの変更  
 ユーザーのパスワードを変更するには、次の関数を使用する:  
  
```  
void ChangePassword( CString &strUserName,   
                     CString &strOldPassword,   
                     CString &strNewPassword )  
{  
   // Create (open) a workspace  
   CDaoWorkspace wsp;  
   CString strWspName = _T( "Temp Workspace" );  
  
   wsp.Create( strWspName, strUserName,  
               strOldPassword );  
   wsp.Append( );  
  
   // Determine how many objects there are  
   // in the Users collection  
   short nUserCount;  
   short nCurrentUser;  
   DAOUser *pUser  = NULL;  
   DAOUsers *pUsers = NULL;  
  
   // Side-effect is implicit OLE AddRef( )   
   // on DAOUser object:  
   DAO_CHECK( wsp.m_pDAOWorkspace->get_Users( &pUsers ) );  
  
   // Side-effect is implicit OLE AddRef( )   
   // on DAOUsers object  
    DAO_CHECK( pUsers->get_Count( &nUserCount ) );  
  
   // Traverse through the list of users   
   // and change password for the userid  
   // used to create/open the workspace  
   for( nCurrentUser = 0; nCurrentUser < nUserCount;  
        nCurrentUser++ )  
   {  
       COleVariant varIndex( nCurrentUser, VT_I2 );  
       COleVariant varName;  
  
       // Retrieve information for user nCurrentUser  
       DAO_CHECK( pUsers->get_Item( varIndex, &pUser ) );  
  
       // Retrieve name for user nCurrentUser  
       DAO_CHECK( pUser->get_Name( &V_BSTR( &varName ) ) );  
  
       CString strTemp = V_BSTRT( &varName );  
  
       // If there is a match, change the password  
       if( strTemp == strUserName )  
       {  
           COleVariant varOldPwd( strOldPassword,   
                                  VT_BSTRT );  
           COleVariant varNewPwd( strNewPassword,   
                                  VT_BSTRT );  
  
           DAO_CHECK( pUser->NewPassword( V_BSTR( &varOldPwd ),  
                      V_BSTR( &varNewPwd ) ) );  
  
           TRACE( "\t Password is changed\n" );  
       }  
   }  
  
   // Clean up: decrement the usage count  
   // on the OLE objects  
   pUser->Release( );  
   pUsers->Release( );  
  
   wsp.Close( );  
}  
```  
  
### .MDB ファイルのパスワードの変更  
 .MDB ファイルのパスワードを変更するには、次の関数を使用する:  
  
```  
void SetDBPassword( LPCTSTR pDB, LPCTSTR pszOldPassword, LPCTSTR pszNewPassword )  
{  
   CDaoDatabase db;  
   CString strConnect( _T( ";pwd=" ) );  
  
   // the database must be opened as exclusive  
   // to set a password  
   db.Open( pDB, TRUE, FALSE,   
            strConnect + pszOldPassword );  
  
   COleVariant NewPassword( pszNewPassword, VT_BSTRT ),  
               OldPassword( pszOldPassword, VT_BSTRT );  
  
   DAO_CHECK( db.m_pDAODatabase->NewPassword( V_BSTR( &OldPassword ),  
              V_BSTR( &NewPassword ) ) );  
  
   db.Close();  
}  
```  
  
## 参照  
 [番号順テクニカル ノート](../mfc/technical-notes-by-number.md)   
 [カテゴリ別テクニカル ノート](../mfc/technical-notes-by-category.md)