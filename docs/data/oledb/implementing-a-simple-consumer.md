---
title: "単純なコンシューマーの実装 | Microsoft Docs"
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
  - "クライアント, 作成"
  - "OLE DB コンシューマー, 実装"
ms.assetid: 13828167-23a4-4e94-8b6c-878262fda464
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 単純なコンシューマーの実装
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

以下のトピックでは、MFC アプリケーション ウィザードや ATL OLE DB コンシューマー ウィザードで作成されたファイルを編集して、単純なコンシューマーを作成する方法について説明します。  この例は次の内容で構成されます。  
  
-   「コンシューマーによるデータの取得」では、データベース テーブルのすべてのデータを 1 行ずつ読み取るコードをコンシューマーに実装する方法を示します。  
  
-   「コンシューマーへのブックマーク サポートの追加」では、コンシューマーにブックマーク サポートを追加する方法を示します。  
  
-   「コンシューマーへの XML サポートの追加」では、取得した行セット データを XML データとして出力するようにコンシューマー コードを変更する方法を示します。  
  
> [!NOTE]
>  このセクションで説明するコンシューマー アプリケーションを使用すると、MyProv サンプル プロバイダーおよび Provider サンプル プロバイダーをテストできます。  
  
> [!NOTE]
>  MyProv \(「[単純な読み取り専用プロバイダーの機能の拡張](../../data/oledb/enhancing-the-simple-read-only-provider.md)」で説明されているのと同じプロバイダー\) をテストするコンシューマー アプリケーションを構築するには、「コンシューマーへのブックマーク サポートの追加」の説明に従ってブックマーク サポートを含める必要があります。  
  
> [!NOTE]
>  Provider をテストするコンシューマー アプリケーションを構築する場合は、「コンシューマーへのブックマーク サポートの追加」のブックマーク サポートを省略し、「コンシューマーへの XML サポートの追加」に進んでください。  
  
## コンシューマーによるデータの取得  
  
#### OLE DB コンシューマーを使用するようにコンソール アプリケーションを変更するには  
  
1.  MyCons.cpp で、次に示す太字の文字を挿入して、メイン コードを変更します。  
  
    ```  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
    #include "stdafx.h"  
    #include "Products.h"  
    ...  
    int main(int argc, char* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);        // Instantiate rowset    CProducts rs;        hr = rs.OpenAll();    ATLASSERT( SUCCEEDED( hr ) );    hr = rs.MoveFirst();        // Iterate through the rowset    while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )    {       // Print out the column information for each row       printf("Product ID: %d, Name: %s, Unit Price: %d, Quantity per Unit: %d, Units in Stock %d, Reorder Level %d\n",              rs.m_ProductID, rs.m_ProductName, rs.m_UnitPrice, rs.m_QuantityPerUnit, rs.m_UnitsInStock, rs.m_ReorderLevel );       hr = rs.MoveNext();    }        rs.Close();    rs.ReleaseCommand();        CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## コンシューマーへのブックマーク サポートの追加  
 ブックマークとは、テーブルの行を一意に識別する列です。  通常、ブックマークはキー列ですが、プロバイダーによって異なります。  ここでは、ブックマーク サポートの追加方法を説明します。  ブックマーク サポートを追加するには、ユーザー レコード クラスで次の処理を実行する必要があります。  
  
-   ブックマークをインスタンス化します。  ブックマークのインスタンスは型が [CBookmark](../../data/oledb/cbookmark-class.md) のオブジェクトです。  
  
-   **DBPROP\_IRowsetLocate** プロパティを設定して、プロバイダーのブックマーク列を要求します。  
  
-   [BOOKMARK\_ENTRY](../../data/oledb/bookmark-entry.md) マクロを使用して、列マップにブックマーク エントリを追加します。  
  
 前の手順では、ブックマーク サポートが追加され、操作できるブックマーク オブジェクトが作成されます。  このコード例では、次のようなブックマークを示します。  
  
-   書き込みを行うファイルを開きます。  
  
-   行セット データを 1 行ずつファイルに出力します。  
  
-   [MoveToBookmark](../../data/oledb/crowset-movetobookmark.md) を呼び出して、行セット カーソルをブックマークに移動します。  
  
-   ブックマークを付けた行を出力し、ファイルの最後に追加します。  
  
> [!NOTE]
>  このコンシューマー アプリケーションを使用して Provider サンプル プロバイダー アプリケーションをテストする場合は、ここで説明するブックマーク サポートの追加は行わないでください。  
  
#### ブックマークをインスタンス化するには  
  
1.  アクセサーに [CBookmark](../../data/oledb/cbookmark-class.md) 型のオブジェクトが含まれている必要があります。  `nSize` パラメーターによって、ブックマーク バッファーのサイズがバイト単位で指定されます。通常、32 ビット プラットフォームでは 4 バイト、64 ビット プラットフォームでは 8 バイトです。  ユーザー レコード クラスの列データ メンバーに次の宣言を追加します。  
  
    ```  
    //////////////////////////////////////////////////////////////////////  
    // Products.h  
    class CProductsAccessor  
    {  
    public:  
       CBookmark<4> m_bookmark;   // Add bookmark declaration  
       LONG m_ProductID;  
       ...  
    ```  
  
#### プロバイダーのブックマーク列を要求するには  
  
1.  ユーザー レコード クラスの `GetRowsetProperties` メソッドに次のコードを追加します。  
  
    ```  
    // Set the DBPROP_IRowsetLocate property.  
    void GetRowsetProperties(CDBPropSet* pPropSet)  
    {  
       pPropSet->AddProperty(DBPROP_CANFETCHBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       pPropSet->AddProperty(DBPROP_CANSCROLLBACKWARDS, true, DBPROPOPTIONS_OPTIONAL);  
       // Add DBPROP_IRowsetLocate property to support bookmarks    pPropSet->AddProperty(DBPROP_IRowsetLocate, true);  
    }  
    ```  
  
#### 列マップにブックマーク エントリを追加するには  
  
1.  ユーザー レコード クラスの列マップに次のエントリを追加します。  
  
    ```  
    // Set a bookmark entry in the column map.  
    BEGIN_COLUMN_MAP(CProductsAccessor)  
       BOOKMARK_ENTRY(m_bookmark)   // Add bookmark entry  
       COLUMN_ENTRY_LENGTH_STATUS(1, m_ProductID, m_dwProductIDLength, m_dwProductIDStatus)  
       COLUMN_ENTRY_LENGTH_STATUS(2, m_ProductName, m_dwProductNameLength, m_dwProductNameStatus)  
    ...  
    END_COLUMN_MAP()  
    ```  
  
#### メイン コードでブックマークを使用するには  
  
1.  前に作成したコンソール アプリケーションの MyCons.cpp ファイルで、次のようにメイン コードを変更します。  ブックマークを使用するには、メイン コードが独自のブックマーク オブジェクト \(`myBookmark`\) をインスタンス化する必要があります。このブックマークは、アクセサーのブックマーク \(`m_bookmark`\) とは異なります。  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       hr = rs.OpenAll();  
       hr = rs.MoveFirst();  
  
       // Cast CURRENCY m_UnitPrice to a long value  
       LONGLONG lPrice = rs.m_UnitPrice.int64;  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // Instantiate a bookmark object myBookmark for the main code  
       CBookmark<4> myBookmark;  
       int nCounter = 0;  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "initial row dump" << endl;  
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          nCounter++;  
          if( nCounter == 5 )  
             myBookmark = rs.bookmark;  
          // Output the column information for each row:  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       // Move cursor to bookmark  
       hr = rs.MoveToBookmark(myBookmark);  
  
       // Iterate through the rowset and output column data to output.txt row by row  
       // In the file, mark the beginning of this set of data:  
       outfile << "row dump starting from bookmarked row" << endl;  
       while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
       {  
          // Output the column information for each row  
          outfile << rs.m_ProductID << rs.m_ProductName << lPrice << rs.m_QuantityPerUnit << rs.m_UnitsInStock << rs.m_ReorderLevel << endl;  
          hr = rs.MoveNext();  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
 ブックマークの詳細については、「[ブックマークの使用](../../data/oledb/using-bookmarks.md)」を参照してください。  ブックマークの例は、「[行セットの更新](../../data/oledb/updating-rowsets.md)」にもあります。  
  
## コンシューマーへの XML サポートの追加  
 「[XML データへのアクセス](../../data/oledb/accessing-xml-data.md)」で説明したように、データ ソースから XML データを取得するには 2 つの方法があります。1 つは [CStreamRowset](../../data/oledb/cstreamrowset-class.md) を使用する方法で、もう 1 つは [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) を使用する方法です。  ここでは、`CStreamRowset` を使用します。この場合、効率は良くなりますが、このサンプル アプリケーションを実行するコンピューターで SQL Server 2000 を実行している必要があります。  
  
#### CStreamRowset を継承するようにコマンド クラスを変更するには  
  
1.  前に作成したコンシューマー アプリケーションで、`CCommand` 宣言を変更し、次のように `CStreamRowset` を行セット クラスとして指定します。  
  
    ```  
    class CProducts : public CCommand<CAccessor<CProductsAccessor>, CStreamRowset >  
    ```  
  
#### メイン コードを変更して XML データを取得および出力するには  
  
1.  前に作成したコンソール アプリケーションの MyCons.cpp ファイルで、次のようにメイン コードを変更します。  
  
    ```  
    ///////////////////////////////////////////////////////////////////////  
    // MyCons.cpp : Defines the entry point for the console application.  
    //  
  
    #include "stdafx.h"  
    #include "Products.h"   
    #include <iostream>  
    #include <fstream>  
    using namespace std;  
  
    int _tmain(int argc, _TCHAR* argv[])  
    {  
       HRESULT hr = CoInitialize(NULL);  
  
       // Instantiate rowset  
       CProducts rs;  
  
       // Add variable declarations for the Read method to handle sequential stream data  
       CHAR buffer[1001];  // Pointer to buffer into which data stream is read  
       ULONG cbRead;       // Actual number of bytes read from the data stream  
  
       hr = rs.OpenAll();  
  
       // Open file output.txt for writing in overwrite mode  
       ofstream outfile( "C:\\output.txt", ios::out );  
  
       if (!outfile)      // Test for invalid file  
          return -1;  
  
       // The following loop reads 1000 bytes of the data stream at a time   
       // until it reaches the end of the data stream  
       for (;;)  
       {  
          // Read sequential stream data into buffer  
          HRESULT hr = rs.m_spStream->Read(buffer, 1000, &cbRead);  
          if (FAILED (hr))  
             break;  
          // Output buffer to file  
          buffer[cbRead] = 0;  
          outfile << buffer;  
          // Test for end of data stream  
          if (cbRead < 1000)  
             break;  
       }  
  
       rs.CloseAll();  
       CoUninitialize();  
  
       return 0;  
    }  
    ```  
  
## 参照  
 [ウィザードを使用した OLE DB コンシューマーの作成](../../data/oledb/creating-an-ole-db-consumer-using-a-wizard.md)