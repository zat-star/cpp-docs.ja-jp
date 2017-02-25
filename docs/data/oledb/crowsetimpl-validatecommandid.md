---
title: "CRowsetImpl::ValidateCommandID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl.ValidateCommandID"
  - "CRowsetImpl::ValidateCommandID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ValidateCommandID メソッド"
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowsetImpl::ValidateCommandID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

一方または両方の **DBID**s がある場合、文字列値が含まれている場合、参照するかどうかは、データ メンバー [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) と [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)にコピーします。  
  
## 構文  
  
```  
  
      HRESULT CRowsetBaseImpl::ValidateCommandID(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### パラメーター  
 `pTableID`  
 \[\]テーブルを表す **DBID** ID へのポインター。  
  
 `pIndexID`  
 \[\]インデックスを表す **DBID** ID へのポインター。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは `CRowsetImpl` で静的なアップキャストを通じてデータ メンバー [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) と [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)を設定するために呼び出されます。  既定では、その場合、またはデータ メンバーにコピーする場合は **DBID**両方 s に文字列値が含まれている場合、このメソッドを確認します。  `CRowsetImpl`にこのシグネチャを持つメソッドを設定して\-派生クラスは、基本実装の代わりに、メソッドが呼び出されます。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)