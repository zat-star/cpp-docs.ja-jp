---
title: "データのフェッチ | Microsoft Docs"
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
  - "データ [C++], フェッチ"
  - "フェッチ"
  - "OLE DB コンシューマー テンプレート (C++), フェッチ (データを)"
  - "行セット [C++], フェッチ"
ms.assetid: b07f747f-9855-4f27-a03d-b1d5b10fa284
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# データのフェッチ
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ソース、セッション、および行セットのオブジェクトを開いた後、データをフェッチできます。  使用するアクセサーの種類によっては、列をバインドする必要がある場合もあります。  
  
### データをフェッチするには  
  
1.  適切な **Open** コマンドを使用して行セットを開きます。  
  
2.  `CManualAccessor` を使用している場合、まだ連結していない場合は出力列を連結します。  列をバインドするには、次の例に示すように、`GetColumnInfo` を呼び出してから、バインディングのあるアクセサーを作成します。  
  
    ```  
    // From the DBViewer Sample CDBTreeView::OnQueryEdit  
    // Get the column information  
    ULONG ulColumns       = 0;  
    DBCOLUMNINFO* pColumnInfo  = NULL;  
    LPOLESTR pStrings      = NULL;  
    if (rs.GetColumnInfo(&ulColumns, &pColumnInfo, &pStrings) != S_OK)  
        ThrowMyOLEDBException(rs.m_pRowset, IID_IColumnsInfo);  
    struct MYBIND* pBind = new MYBIND[ulColumns];  
    rs.CreateAccessor(ulColumns, &pBind[0], sizeof(MYBIND)*ulColumns);  
    for (ULONG l=0; l<ulColumns; l++)  
    rs.AddBindEntry(l+1, DBTYPE_STR, sizeof(TCHAR)*40, &pBind[l].szValue, NULL, &pBind[l].dwStatus);  
    rs.Bind();  
    ```  
  
3.  データを取得する `while` ループを記述します。  ループでは、次に示すように、`MoveNext` を呼び出してカーソルを進め、戻り値が S\_OK かどうかをテストします。  
  
    ```  
    while (rs.MoveNext() == S_OK)  
    {  
        // Add code to fetch data here  
        // If you are not using an auto accessor, call rs.GetData()  
    }  
    ```  
  
4.  `while` ループ内で、アクセサーの種類に応じてデータをフェッチできます。  
  
    -   [CAccessor](../Topic/CAccessor%20Class.md) クラスを使用する場合は、データ メンバーを含むユーザー レコードが必要です。  次の例に示すように、これらのデータ メンバーを使用してデータにアクセスできます。  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members directly. In this case, m_nFooID  
            // is declared in a user record that derives from  
            // CAccessor  
            wsprintf_s("%d", rs.m_nFooID);   
        }  
        ```  
  
    -   `CDynamicAccessor` クラスまたは `CDynamicParameterAccessor` クラスを使用する場合は、次の例に示すように、`GetValue` アクセス関数および `GetColumn` アクセス関数を使用してデータをフェッチできます。  使用しているデータの型を判断するには、`GetType` を使用します。  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the dynamic accessor functions to retrieve your data.  
  
            ULONG ulColumns = rs.GetColumnCount();  
            for (ULONG i=0; i<ulColumns; i++)  
            {  
                rs.GetValue(i);  
            }  
        }  
        ```  
  
    -   `CManualAccessor` を使用する場合は、次の例に示すように、独自のデータ メンバーを指定してバインドし、それらのメンバーに直接アクセスする必要があります。  
  
        ```  
        while (rs.MoveNext() == S_OK)  
        {  
            // Use the data members you specified in the calls to  
            // AddBindEntry.  
  
            wsprintf_s("%s", szFoo);  
        }  
        ```  
  
## 参照  
 [OLE DB コンシューマー テンプレートの操作](../../data/oledb/working-with-ole-db-consumer-templates.md)