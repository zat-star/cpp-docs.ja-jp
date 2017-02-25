---
title: "CDynamicAccessor::AddBindEntry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDynamicAccessor::AddBindEntry"
  - "AddBindEntry"
  - "CDynamicAccessor.AddBindEntry"
  - "CDynamicAccessor::AddBindEntry"
  - "ATL.CDynamicAccessor.AddBindEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddBindEntry メソッド"
ms.assetid: 8f139376-7db3-4193-ba3b-63fe938ffa79
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::AddBindEntry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

出力列にバインド エントリを追加します。  
  
## 構文  
  
```  
  
      HRESULT AddBindEntry(   
   const DBCOLUMNINFO& info    
) throw( );  
```  
  
#### パラメーター  
 `info`  
 \[\] A **DBCOLUMNINFO** を含む構造体の列情報。  「DBCOLUMNINFO 構成して *OLE DB Programmer's Reference*の [IColumnsInfo::GetColumnInfo](https://msdn.microsoft.com/en-us/library/ms722704.aspx) 」を参照してください。  
  
## 戻り値  
 `HRESULT` 標準値のいずれか 1 つが。  
  
## 解説  
 `CDynamicAccessor` で作成された既定のアクセサーをオーバーライドするときにこのメソッドを使用します。[How Do I のデータをフェッチします。](../../data/oledb/fetching-data.md)を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)