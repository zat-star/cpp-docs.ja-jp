---
title: "CTable クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CTable"
  - "ATL.CTable"
  - "CTable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTable クラス"
ms.assetid: f13fdaa3-e198-4557-977d-54b0bbc3454d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CTable クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

直接単純な行セット \(パラメーターなしで 1\) にアクセスできます。  
  
## 構文  
  
```  
template <   
   class TAccessor = CNoAccessor,    
   template <typename T> class TRowset = CRowset    
>  
class CTable :    
   public CAccessorRowset <   
      TAccessor,    
      TRowset    
   >  
```  
  
#### パラメーター  
 `TAccessor`  
 アクセサー クラス。  
  
 `TRowset`  
 行セット クラス。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[&#91;Open&#93;](../../data/oledb/ctable-open.md)|テーブルを開きます。|  
  
## 解説  
 行セットにアクセスするコマンドを実行する方法については、" [CCommand](../../data/oledb/ccommand-class.md) を参照してください。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx)