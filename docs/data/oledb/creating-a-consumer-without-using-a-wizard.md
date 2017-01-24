---
title: "ウィザードを使用しないコンシューマーの作成 | Microsoft Docs"
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
  - "OLE DB コンシューマー, 作成"
ms.assetid: e8241cfe-5faf-48f8-9de3-241203de020b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ウィザードを使用しないコンシューマーの作成
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

次の例は、OLE DB コンシューマー サポートを既存の ATL プロジェクトに追加することを前提にしています。  OLE DB コンシューマー サポートを MFC アプリケーションに追加する場合は、MFC アプリケーション ウィザードを実行する必要があります。MFC アプリケーション ウィザードは、必要なすべてのサポートを作成し、アプリケーションの実行に必要な MFC ルーチンを呼び出します。  
  
 ATL OLE DB コンシューマー ウィザードを使用せずに OLE DB コンシューマー サポートを追加するには、以下の手順に従います。  
  
-   Stdafx.h ファイルに次の `#include` ステートメントを追加します。  
  
    ```  
    #include <atlbase.h>  
    #include <atldbcli.h>  
    #include <atldbsch.h> // if you are using schema templates  
    ```  
  
 プログラムでは、通常、コンシューマーが以下の操作を実行します。  
  
-   列をローカル変数に連結するユーザー レコード クラスを作成します。  この例では、`CMyTableNameAccessor` がユーザー レコード クラスです \(「[ユーザー レコード](../../data/oledb/user-records.md)」を参照\)。  このクラスには、列マップとパラメーター マップが含まれます。  列マップに指定する各フィールドについて、ユーザー レコード クラスでデータ メンバーを宣言します。また、これらの各データ メンバーについて、ステータスのデータ メンバーと長さのデータ メンバーも宣言します。  詳細については、「[ウィザードで生成されたアクセサーのフィールド ステータスのデータ メンバー](../Topic/Field%20Status%20Data%20Members%20in%20Wizard-Generated%20Accessors.md)」を参照してください。  
  
    > [!NOTE]
    >  独自のコンシューマーを作成する場合は、データ変数をステータスの変数や長さの変数より前に記述する必要があります。  
  
-   データ ソースとセッションをインスタンス化します。  使用するアクセサーと行セットの種類を決定し、[CCommand](../../data/oledb/ccommand-class.md) または [CTable](../../data/oledb/ctable-class.md) を使用して行セットをインスタンス化します。  
  
    ```  
    CDataSource ds;  
    CSession ss;  
    class CMyTableName : public CCommand<CAccessor<CMyTableNameAccessor> >  
    ```  
  
-   **CoInitialize** を呼び出して COM を初期化します。  通常は、メイン コードで呼び出されます。  たとえば、次のようになります。  
  
    ```  
    HRESULT hr = CoInitialize(NULL);  
    ```  
  
-   [CDataSource::Open](../../data/oledb/cdatasource-open.md) またはそのバリエーションを呼び出します。  
  
-   データ ソースに接続し、セッションを開き、行セットを開いて初期化します。コマンドがある場合は実行します。  
  
    ```  
    hr = ds.Open();  
    hr = ss.Open(ds);  
    hr = rs.Open();            // (Open also executes the command)  
    ```  
  
-   必要に応じて、`CDBPropSet::AddProperty` を使用して行セット プロパティを設定し、パラメーターとして `rs.Open` に渡します。  この手順の例については、「[コンシューマー ウィザードで生成されたメソッド](../Topic/Consumer%20Wizard-Generated%20Methods.md)」の「GetRowsetProperties」を参照してください。  
  
-   これで、行セットを使用してデータの取得や操作を行うことができます。  
  
-   アプリケーションが終了したら、接続、セッション、および行セットを閉じます。  
  
    ```  
    rs.Close();  
    ss.Close();  
    ds.Close();  
    ```  
  
     コマンドを使用している場合は、**Close** の後に `ReleaseCommand` を呼び出すこともできます。  「[CCommand::Close](../Topic/CCommand::Close.md)」のコード例では、**Close** と `ReleaseCommand` の呼び出し方法が示されています。  
  
-   **CoUnInitialize** を呼び出して COM の初期化を解除します。  通常は、メイン コードで呼び出されます。  
  
    ```  
    CoUninitialize();  
    ```  
  
## 参照  
 [OLE DB コンシューマーの作成](../../data/oledb/creating-an-ole-db-consumer.md)