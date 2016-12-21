---
title: "CDynamicAccessor::GetStatus | Microsoft Docs"
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
  - "ATL::CDynamicAccessor::GetStatus"
  - "CDynamicAccessor.GetStatus"
  - "ATL.CDynamicAccessor.GetStatus"
  - "CDynamicAccessor::GetStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetStatus メソッド"
ms.assetid: 8f1aba69-5c2c-4ca7-ad84-7b4b27995eb8
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された列の状態を取得します。  
  
## 構文  
  
```  
  
      bool GetStatus(   
   DBORDINAL nColumn,   
   DBSTATUS* pStatus    
) const throw( );  
bool GetStatus(  
   const CHAR* pColumnName,  
   DBSTATUS* pStatus   
) const throw( );  
bool GetStatus(  
   const WCHAR* pColumnName,  
   DBSTATUS* pStatus   
) const throw( );  
```  
  
#### パラメーター  
 `nColumn`  
 \[入力\] 列番号。  列番号は 1 から始まります。  0 番はブックマーク列です。  
  
 `pColumnName`  
 \[\]列名を含む文字列へのポインター。  
  
 `pStatus`  
 \[\]を含む変数へのポインター。列のステータス。  詳細については、" *OLE DB Programmer's Reference* の [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) を参照してください。  
  
## 戻り値  
 指定された列がある場合 **true** を返します。  それ以外の場合、この関数の戻り値 **false**。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetStatus](../Topic/CDynamicAccessor::SetStatus.md)