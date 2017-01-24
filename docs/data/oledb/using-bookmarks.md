---
title: "ブックマークの使用 | Microsoft Docs"
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
  - "ブックマーク, OLE DB"
  - "OLE DB プロバイダー テンプレート, ブックマーク"
  - "OLE DB プロバイダー, ブックマーク サポート"
  - "行セット, ブックマーク"
ms.assetid: 7fa1d1a8-5063-4aa9-93ee-815bb9c98fae
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ブックマークの使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セットを開く前に、ブックマークを使用することをプロバイダーに通知する必要があります。  これを通知するには、プロパティ セットの **DBPROP\_BOOKMARKS** プロパティを **true** に設定します。  プロバイダーはブックマークを列 0 として取得するため、静的アクセサーを使用している場合は、`BOOKMARK_ENTRY` という特殊マクロと `CBookmark` クラスを使用する必要があります。  `CBookmark` クラスはテンプレート クラスで、引数はブックマーク バッファーの長さ \(バイト単位\) です。  ブックマークに必要なバッファーの長さは、プロバイダーによって異なります。  次の例のように ODBC OLE DB プロバイダーを使用している場合、バッファーは 4 バイトにする必要があります。  
  
```  
class CProducts  
{  
public:  
   CBookmark<4>   bookmark;  
  
   BEGIN_COLUMN_MAP(CProducts)  
      BOOKMARK_ENTRY(bookmark)  
   END_COLUMN_MAP()  
};  
  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
  
CTable<CAccessor<CProducts> > product;  
product.Open(session, "Products", &propset);  
```  
  
 `CDynamicAccessor` を使用している場合、バッファーは実行時に動的に割り当てられます。  この場合は、バッファーの長さを指定しない特別なバージョンの `CBookmark` を使用できます。  次のコード例に示すように、`GetBookmark` 関数を使用して、現在のレコードからブックマークを取得します。  
  
```  
CTable<CDynamicAccessor> product;  
CBookmark<>              bookmark;  
CDBPropSet propset(DBPROPSET_ROWSET);  
  
propset.AddProperty(DBPROP_BOOKMARKS, true);  
product.Open(session, "Products", &propset);  
product.MoveNext();  
product.GetBookmark(&bookmark);  
```  
  
 プロバイダーでのブックマークのサポートについては、「[プロバイダーのブックマーク サポート](../../data/oledb/provider-support-for-bookmarks.md)」を参照してください。  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)