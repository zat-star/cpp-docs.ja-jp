---
title: "IOpenRowsetImpl::CreateRowset | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IOpenRowsetImpl.CreateRowset"
  - "IOpenRowsetImpl::CreateRowset"
  - "CreateRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRowset メソッド"
ms.assetid: 69041cf6-7a2f-4409-a26e-6e984c24986e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IOpenRowsetImpl::CreateRowset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

行セット オブジェクトを作成します。  直接ユーザーによって呼び出された場合。  *OLE DB Programmer's Reference*の [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) を参照してください。  
  
## 構文  
  
```  
  
      template <class   
      RowsetClass  
      >  
HRESULT CreateRowset(  
   IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset,  
   RowsetClass*& pRowsetObj   
);  
```  
  
#### パラメーター  
 `RowsetClass`  
 ユーザーの行セット クラスを表しているテンプレート クラスのメンバーです。  通常、ウィザードによって生成されます。  
  
 `pRowsetObj`  
 \[\]行セット オブジェクトへのポインター。  通常、このパラメーターは使用されませんが、COM オブジェクトに渡す前に行セットに多くの作業を実行する必要がある場合に使用できます。  `pRowsetObj` の有効期間は、`ppRowset`にバインドされます。  
  
 他のパラメーターには、*OLE DB Programmer's Reference*の [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IOpenRowsetImpl クラス](../../data/oledb/iopenrowsetimpl-class.md)