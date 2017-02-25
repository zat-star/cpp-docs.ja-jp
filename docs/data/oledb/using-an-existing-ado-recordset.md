---
title: "既存の ADO レコードセットの使用 | Microsoft Docs"
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
  - "ADO レコードセット [C++]"
  - "OLE DB コンシューマー テンプレート, ADO レコードセット"
  - "レコードセット [C++], 使用 (OLE DB で)"
ms.assetid: a9b1de8a-d379-49b1-a26e-578741e9f6a8
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 既存の ADO レコードセットの使用
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB コンシューマー テンプレートと Active データ オブジェクト \(ADO: Active Data Object\) を混在させるには、ADO を使用してレコードセットを開きます。このレコードセットは、OLE DB コンシューマー テンプレートの行セットに相当します。  レコードセットを開いたら、次の手順に従って OLE DB 行セットに接続します。  
  
1.  `IRowset` ポインターと `IAccessor` ポインターに対して `QueryInterface` を呼び出します。  
  
    ```  
    IRowset* lpRowset = NULL;  
    IAccessor* lpAccessor = NULL;  
    lpUnk->QueryInterface(IID_IRowset, (void**)&lpRowset);  
    lpUnk->QueryInterface(IID_IAccessor, (void**)&lpAccessor);  
    ```  
  
    > [!NOTE]
    >  *lpUnk* は、ADO レコードセットの **IUnknown** オブジェクトを指します。  
  
2.  アクセサーと行セットを適切な OLE DB コンシューマー テンプレート クラスに割り当てます。  
  
    ```  
    CRowset rs;  
    CAccessor accessor;  
  
    accessor.AddAccessorInfo(0ul);      // 0 is the ordinal of an ADO accessor  
    rs.m_spRowset.Attach(lpRowset);      // use the Attach method of CComPtr<>  
    rs.SetAccessor(accessor);  
    ```  
  
## 参照  
 [アクセサーの使用](../../data/oledb/using-accessors.md)