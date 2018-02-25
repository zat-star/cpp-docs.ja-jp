---
title: "プロバイダーでプロパティを参照 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- OLE DB providers, properties
- references, to properties in providers
- referencing properties in providers
ms.assetid: bfbb3851-5eed-467a-a179-4a97a9515525
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3a034c1f925a5b5d422be234118782b283a3d74c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="referencing-a-property-in-your-provider"></a>プロバイダーでのプロパティの参照
目的のプロパティのプロパティ グループとプロパティ ID が見つかりません。 詳細については、次を参照してください。 [OLE DB プロパティ](https://msdn.microsoft.com/en-us/library/ms722734.aspx)で、 *OLE DB プログラマーズ リファレンス*です。  
  
 次の例では、行セットからプロパティを取得しようとしていることを前提としています。 セッションまたはコマンドを使用するコードは似ていますが、別のインターフェイスを使用します。  
  
 作成、 [CDBPropSet](../../data/oledb/cdbpropset-class.md)オブジェクトのコンス トラクターにパラメーターとしてプロパティのグループを使用します。 例:  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  
```  
  
 呼び出す[AddProperty](../../data/oledb/cdbpropset-addproperty.md)プロパティに割り当てられるには、プロパティ ID と値を渡します。 値の型は、使用しているプロパティに依存します。  
  
```  
CDBPropSet propset(DBPROPSET_ROWSET);  

propset.AddProperty(DBPROP_IRowsetChange, true);  

propset.AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_INSERT | DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_DELETE);  
```  
  
 使用して、`IRowset`を呼び出すインターフェイス**GetProperties**です。 パラメーターとして設定されたプロパティを渡します。 最終的なコードを次に示します。  
  
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
  
## <a name="see-also"></a>参照  
 [OLE DB プロバイダー テンプレートの操作](../../data/oledb/working-with-ole-db-provider-templates.md)