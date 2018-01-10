---
title: "既存の ADO レコード セットの使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ADO recordsets [C++]
- OLE DB consumer templates, ADO recordsets
- recordsets [C++], using in OLE DB
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 02f8f29c60601e22a1b005f435d3626336628a1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="using-an-existing-ado-recordset"></a>既存の ADO レコードセットの使用
OLE DB コンシューマー テンプレート、アクティブなデータ オブジェクト (ADO) を混在させるには、ADO を使用して、レコード セット (OLE DB コンシューマー テンプレート内の行セットに対応する) を開きます。 レコード セットがある場合は、ときに、OLE DB 行セットに接続するには、次を行います。  
  
1.  呼び出す`QueryInterface`の`IRowset`と`IAccessor`ポインター。  
  
    ```  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *lpUnk*を指す、 **IUnknown** ADO レコード セットのオブジェクト。  
  
2.  アクセサーと行セットを適切な OLE DB コンシューマー テンプレート クラスにアタッチします。  
  
    ```  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## <a name="see-also"></a>参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)