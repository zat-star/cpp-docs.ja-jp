---
title: "プロバイダーでのプロパティの参照 | Microsoft Docs"
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
  - "OLE DB プロバイダー, プロパティ"
  - "参照, プロパティ (プロバイダーの) への"
  - "参照 (プロバイダーのプロパティを)"
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# プロバイダーでのプロパティの参照
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

必要なプロパティのプロパティ グループとプロパティ ID を検索します。  詳細については、『OLE DB Programmer's Reference』の「[OLE DB Properties](https://msdn.microsoft.com/en-us/library/ms722734.aspx)」を参照してください。  
  
 ここで説明するコードは、行セットからプロパティを取得する例です。  セッションまたはコマンドを使用するコードは似ていますが、使用するインターフェイスは異なります。  
  
 プロパティ グループをコンストラクターへのパラメーターとして使用して [CDBPropSet](../Topic/CDBPropSet%20Class.md) オブジェクトを作成します。  たとえば、次のようになります。  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 [AddProperty](../../data/oledb/cdbpropset-addproperty.md) を呼び出します。このとき、プロパティに割り当てるプロパティ ID と値を渡します。  値の型は使用するプロパティによって異なります。  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
propset.AddProperty(DBPROP_IRowsetChange, true);  
propset.AddProperty(DBPROP_UPDATABILITY,  
DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 `IRowset` インターフェイスを使用して **GetProperties** を呼び出します。  プロパティ セットをパラメーターとして渡します。  完成したコードを次に示します。  
  
```  
CAgentRowset<CMyProviderCommand>* pRowset = (CAgentRowset<CMyProviderCommand>*) pThis;  
  
CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;  
  
DBPROPIDSET set;  
set.AddPropertyID(DBPROP_BOOKMARKS);  
DBPROPSET* pPropSet = NULL;  
ULONG ulPropSet = 0;  
HRESULT hr;  
  
if (spRowsetProps)  
   hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);  
  
if (pPropSet)  
{  
   CComVariant var = pPropSet->rgProperties[0].vValue;  
   CoTaskMemFree(pPropSet->rgProperties);  
   CoTaskMemFree(pPropSet);  
  
   if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))  
   {  
      ...  // Use property here  
   }  
}  
```  
  
## 参照  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)