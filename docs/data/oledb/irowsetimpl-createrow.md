---
title: "IRowsetImpl::CreateRow | Microsoft Docs"
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
  - "IRowsetImpl.CreateRow"
  - "ATL.IRowsetImpl.CreateRow"
  - "ATL::IRowsetImpl::CreateRow"
  - "CreateRow"
  - "IRowsetImpl::CreateRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateRow メソッド"
ms.assetid: b01c430c-9484-4fef-a6cf-a2e8d9d99130
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetImpl::CreateRow
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

新しい **HROW**を割り当てるに [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) で呼び出されるヘルパー メソッド。  
  
## 構文  
  
```  
  
      HRESULT CreateRow(  
   DBROWOFFSET lRowsOffset,  
   DBCOUNTITEM& cRowsObtained,  
   HROW* rgRows   
);  
```  
  
#### パラメーター  
 *lRowsOffset*  
 作成された行の挿入位置。  
  
 *cRowsObtained*  
 参照が作成された行数を示すユーザーに対して合格しました。  
  
 *rgRows*  
 新しく作成された行ハンドルを持つ呼び出し元に返される **HROW**s の配列。  
  
## 解説  
 行がある場合は、メソッドの呼び出し [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) を返します。  それ以外の場合は、可変 RowClass テンプレートの新しいインスタンスを割り当て、[m\_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)に追加します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetImpl クラス](../Topic/IRowsetImpl%20Class.md)