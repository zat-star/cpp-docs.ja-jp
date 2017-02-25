---
title: "IRowsetChangeImpl::FlushData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetChangeImpl::FlushData"
  - "IRowsetChangeImpl.FlushData"
  - "FlushData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FlushData メソッド"
ms.assetid: fd4bc73b-bc25-4aab-90d5-0bed92670c88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetChangeImpl::FlushData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

データ ストアにコミットをプロバイダーによって Overidden。  
  
## 構文  
  
```  
  
      HRESULT FlushData(  
   HROW hRowToFlush,  
   HACCESSOR hAccessorToFlush   
);  
```  
  
#### パラメーター  
 *hRowToFlush*  
 \[\]データの行へのハンドル。  この行の種類は `IRowsetImpl` クラス`CSimpleRow` \(既定\) の *RowClass の* テンプレート引数によって決定されます。  
  
 *hAccessorToFlush*  
 \[\]含むアクセサーのハンドル、バインディング情報と **PROVIDER\_MAP** の型情報 \([IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)を参照してください。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetChangeImpl クラス](../../data/oledb/irowsetchangeimpl-class.md)