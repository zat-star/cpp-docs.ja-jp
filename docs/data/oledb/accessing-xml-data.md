---
title: "XML データへのアクセス | Microsoft Docs"
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
  - "CStreamRowset クラス, 取得 (XML データを)"
  - "CXMLAccessor クラス, 取得 (XML データを)"
  - "データ [C++], XML データ アクセス"
  - "データ アクセス [C++], XML データ"
  - "行セット [C++], 取得 (XML データを)"
  - "XML [C++], アクセス (データに)"
ms.assetid: 6b693d55-a554-4846-8118-e8773b79b572
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# XML データへのアクセス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ソースから XML データを取得するには、2 つの方法があります。1 つは [CStreamRowset](../../data/oledb/cstreamrowset-class.md) を使用する方法で、もう 1 つは [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) を使用する方法です。  
  
|機能|CStreamRowset|CXMLAccessor|  
|--------|-------------------|------------------|  
|転送されるデータの量|すべての列と行のデータを一度に取得します。|すべての列から一度に 1 行だけデータを取得します。  `MoveNext` などのメソッドを使用して行を移動する必要があります。|  
|文字列の書式設定|SQL Server は、書式を XML 文字列に設定し、コンシューマーに送信します。|ネイティブな形式で行セット データを取得 \(プロバイダーがそのデータを Unicode 文字列として送信することを要求\) し、そのデータを含む文字列を XML 書式で作成します。|  
|書式設定の制御|SQL Server 2000 に固有のプロパティを設定することにより、XML 文字列の書式設定の方法をある程度制御できます。|生成された XML 文字列の書式は制御できません。|  
  
 `CStreamRowset` を使用すると、より効率的に XML 形式でデータを取得できますが、この方法は SQL Server 2000 でだけサポートされます。  
  
## CStreamRowset を使用した XML データの取得  
 `CCommand` または `CTable` の宣言で、行セットの種類として [CStreamRowset](../../data/oledb/cstreamrowset-class.md) を指定します。  独自のアクセサーと共に使用するか、またはアクセサーなしで使用できます。たとえば、次のようにします。  
  
```  
CCommand<CAccessor<CMyAccessor>, CStreamRowset> myCmd;  
```  
  
 または  
  
```  
CCommand<CNoAccessor, CStreamRowset> myCmd;  
```  
  
 通常、たとえば `CRowset` を `TRowset` クラスとして指定して `CCommand::Open` を呼び出すと、`IRowset` ポインターが取得されます。  `ICommand::Execute` は `IRowset` ポインターを返し、そのポインターは `CRowset` オブジェクトの `m_spRowset` メンバーに格納されます。  `MoveFirst`、`MoveNext`、`GetData` などのメソッドは、このポインターを使用してデータを取得します。  
  
 対照的に、`CStreamRowset` を `TRowset` クラスとして指定して `CCommand::Open` を呼び出すと、`ICommand::Execute` は `ISequentialStream` ポインターを返します。このポインターは、[CStreamRowset](../../data/oledb/cstreamrowset-class.md) の `m_spStream` データ メンバーに格納されます。  その後、`Read` メソッドを使用して、XML 形式でデータ \(Unicode 文字列\) を取得できます。  たとえば、次のようになります。  
  
```  
myCmd.m_spStream->Read()  
```  
  
 SQL Server 2000 は、XML 書式設定を実行し、行セットのすべての列とすべての行を 1 つの XML 文字列として返します。  
  
 `Read` メソッドの使用例については、「[単純なコンシューマーの実装](../../data/oledb/implementing-a-simple-consumer.md)」の「コンシューマーへの XML サポートの追加」を参照してください。  
  
> [!NOTE]
>  `CStreamRowset` を使用する XML サポートが機能するのは SQL Server 2000 だけです。また、この場合は、\(MDAC と共にインストールされる\) OLE DB Provider for SQL Server 2000 が必要です。  
  
## CXMLAccessor を使用した XML データの取得  
 [CXMLAccessor](../../data/oledb/cxmlaccessor-class.md) を使用すると、データ ストアのスキーマについて何も知らなくても、データ ソースのデータを文字列データとしてアクセスできます。  `CXMLAccessor` は `CDynamicStringAccessorW` と同じように動作しますが、データ ストアからアクセスされたすべてのデータを XML 形式の \(タグ付き\) データとして変換する点が異なります。  XML タグ名は、データ ストアの列名に可能な限り一致するように付けられます。  
  
 ほかのアクセサー クラスの場合と同様に `CXMLAccessor` を使用し、テンプレート パラメーターとして `CCommand` または `CTable` に渡します。  
  
```  
CTable<CXMLAccessor, CRowset> rs;  
```  
  
 [GetXMLRowData](../Topic/CXMLAccessor::GetXMLRowData.md) を使用してテーブルから一度に 1 行のデータを取得し、`MoveNext` などのメソッドを使用して行を移動します。たとえば、次のようにします。  
  
```  
// Open data source, session, and rowset  
hr = rs.MoveFirst();  
while( SUCCEEDED(hr) && hr != DB_S_ENDOFROWSET )  
{  
    CStringW strRowData;  
    myCmd.GetXMLRowData(strRowData);  
  
    printf_s( "%S\n", strRowData );  
  
    hr = rs.MoveNext();  
}  
```  
  
 [GetXMLColumnData](../Topic/CXMLAccessor::GetXMLColumnData.md) を使用すると、列 \(データ型\) 情報を XML 形式の文字列データとして取得できます。  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)