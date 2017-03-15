---
title: "データベース属性によるデータ アクセスの簡略化 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc-attr.db_param"
  - "vc-attr.db_column"
  - "vc-attr.db_accessor"
  - "vc-attr.db_command"
  - "vc-attr.db_table"
  - "vc-attr.db_source"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "属性 [C++], データ アクセス"
  - "属性 [C++], データベース"
  - "属性 [C++], OLE DB コンシューマー"
  - "データ [C++], 簡略化 (アクセスを)"
  - "データ アクセス [C++], データベース属性"
  - "データベース属性 [C++]"
  - "データベース [C++], 属性"
  - "OLE DB コンシューマー [C++], データベース属性"
ms.assetid: 560d2456-e307-4cb7-ba7b-4d0ed674697f
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# データベース属性によるデータ アクセスの簡略化
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ここでは、データベース属性を使用してデータベース操作を簡略化する方法について説明します。  
  
 データベースの情報にアクセスするための基本的な方法では、データベースの特定のテーブルのためのコマンド \(またはテーブル\) クラスとユーザー レコード クラスを作成します。  データベース属性は、以前には必要とされたテンプレート宣言の一部を簡略化します。  
  
 このトピックの各セクションでは、2 つの等価のテーブル クラスおよびユーザー レコード クラス宣言を示して、データベース属性の使用方法を説明します。最初の宣言では属性を使用し、2 番目の宣言では OLE DB テンプレートを使用しています。  このような宣言コードは、通常、テーブルまたはコマンド オブジェクトに対して指定されたヘッダー ファイル \(Authors.h など\) に配置されます。  
  
 2 つのファイルを比較することにより、属性を使用するとどの程度単純になるかがわかります。  次のような違いがあります。  
  
-   属性を使用する場合は、`CAuthors` というクラスだけを宣言する必要があります。テンプレートを使用する場合は、`CAuthorsNoAttrAccessor` と `CAuthorsNoAttr` の 2 つのクラスを宣言する必要があります。  
  
-   属性付きバージョンの `db_source` 呼び出しは、テンプレート宣言の `OpenDataSource()` 呼び出しと等価です。  
  
-   属性を使用するバージョンの **db\_table** 呼び出しは、次のテンプレート宣言と等価です。  
  
    ```  
    class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
    ```  
  
-   属性を使用するバージョンの **db\_column** 呼び出しは、テンプレート宣言の列マップ \(`BEGIN_COLUMN_MAP ... END_COLUMN_MAP` に関するトピックを参照\) と等価です。  
  
 属性により、ユーザー レコード クラス宣言が挿入されます。  ユーザー レコード クラスは、テンプレート宣言の `CAuthorsNoAttrAccessor` と等価です。  テーブル クラスが `CAuthors` の場合、挿入されるユーザー レコード クラスの名前は `CAuthorsAccessor` になります。また、ユーザー レコード クラスの宣言は挿入されたコードでだけ参照できます。  詳細については、「[ユーザー レコード](../../data/oledb/user-records.md)」の「属性により挿入されたユーザー レコード クラス」を参照してください。  
  
 属性を使用するコードまたはテンプレートを使用するコードのどちらの場合でも、`CDBPropSet::AddProperty` を使用して行セット プロパティを設定する必要があります。  
  
 このトピックで説明した属性については、「[OLE DB コンシューマー属性](../../windows/ole-db-consumer-attributes.md)」を参照してください。  
  
## 属性を使用したテーブルとアクセサーの宣言  
 以下のコードでは、テーブル クラスの`db_source` と **db\_table** を呼び出しています。  `db_source` は、使用するデータ ソースと接続を指定します。  **db\_table** は、テーブル クラスを宣言するための適切なテンプレート コードを挿入します。  **db\_column** は、列マップを指定し、アクセサー宣言を挿入します。  OLE DB コンシューマー属性は、ATL をサポートするすべてのプロジェクトで使用できます。  
  
 属性を使用したテーブルとアクセサーの宣言は次のようになります。  
  
```  
//////////////////////////////////////////////////////////////////////  
// Table and accessor declaration using attributes  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// Table class declaration  
// (Note that you must provide your own connection string for db_source.)  
[  
   db_source(L"your connection string"),  
   db_table("Authors")  
]  
class CAuthors  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
};  
```  
  
## テンプレートを使用したテーブルとアクセサーの宣言  
 テンプレートを使用したテーブルとアクセサーの宣言は次のようになります。  
  
```  
//////////////////////////////////////////////////////////////////////  
// Table and user record class declaration using templates  
// authors.h  
//////////////////////////////////////////////////////////////////////  
  
// User record class declaration  
class CAuthorsNoAttrAccessor  
{  
public:  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
   LONG m_AuID;  
   TCHAR m_Author[51];  
   SHORT m_YearBorn;  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true);  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
   }  
   HRESULT OpenDataSource()  
   {  
      CDataSource _db;  
      HRESULT hr;  
      hr = _db.OpenFromInitializationString(L"your connection string");  
      if (FAILED(hr))  
      {  
#ifdef _DEBUG  
         AtlTraceErrorRecords(hr);  
#endif  
         return hr;  
      }  
      return m_session.Open(_db);  
   }  
   void CloseDataSource()  
   {  
      m_session.Close();  
   }  
   operator const CSession&()  
   {  
      return m_session;  
   }  
   CSession m_session;  
   BEGIN_COLUMN_MAP(CAuthorsNoAttrAccessor)  
      COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, m_dwAuIDLength, m_dwAuIDStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, m_dwAuthorLength, m_dwAuthorStatus)  
      COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, m_dwYearBornLength, m_dwYearBornStatus)  
   END_COLUMN_MAP()  
};  
class CAuthorsNoAttr : public CTable<CAccessor<CAuthorsNoAttrAccessor> >  
{  
public:  
   HRESULT OpenAll()  
   {  
      HRESULT hr;  
      hr = OpenDataSource();  
      if (FAILED(hr))  
         return hr;  
      __if_exists(GetRowsetProperties)  
      {  
         CDBPropSet propset(DBPROPSET_ROWSET);  
         __if_exists(HasBookmark)  
         {  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
         }  
         GetRowsetProperties(&propset);  
         return OpenRowset(&propset);  
      }  
      __if_not_exists(GetRowsetProperties)  
      {  
         __if_exists(HasBookmark)  
         {  
            CDBPropSet propset(DBPROPSET_ROWSET);  
            propset.AddProperty(DBPROP_IRowsetLocate, true);  
            return OpenRowset(&propset);  
         }  
      }  
      return OpenRowset();  
   }  
   HRESULT OpenRowset(DBPROPSET *pPropSet = NULL)  
   {  
      HRESULT hr = Open(m_session, "Authors", pPropSet);  
#ifdef _DEBUG  
      if(FAILED(hr))  
         AtlTraceErrorRecords(hr);  
#endif  
      return hr;  
   }  
   void CloseAll()  
   {  
      Close();  
      CloseDataSource();  
   }  
};  
```  
  
## 参照  
 [OLE DB Consumer Attributes](../../windows/ole-db-consumer-attributes.md)   
 [Attributes Walkthroughs](http://msdn.microsoft.com/ja-jp/73df1d5d-261a-4521-98fb-06dcbf5ec0d0)