---
title: "CDynamicAccessor::GetLength | Microsoft Docs"
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
  - "CDynamicAccessor.GetLength"
  - "ATL.CDynamicAccessor.GetLength"
  - "CDynamicAccessor::GetLength"
  - "ATL::CDynamicAccessor::GetLength"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetLength メソッド"
ms.assetid: 3ae8983b-b267-4cf9-bfc0-3e191f79e646
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::GetLength
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された列の長さを取得します。  
  
## 構文  
  
```  
  
      bool GetLength(   
   DBORDINAL nColumn,   
   DBLENGTH* pLength    
) const throw( );  
bool GetLength(   
   const CHAR* pColumnName,   
   DBLENGTH* pLength    
) const throw( );  
bool GetLength(   
   const WCHAR* pColumnName,   
   DBLENGTH* pLength    
) const throw( );  
```  
  
#### パラメーター  
 `nColumn`  
 \[入力\] 列番号。  列番号は 1 から始まります。  0 番はブックマーク列です。  
  
 `pColumnName`  
 \[\]列名を含む文字列へのポインター。  
  
 `pLength`  
 \[\]整数へのポインターのバイト列の長さ。  
  
## 戻り値  
 指定された列がある場合 **true** を返します。  それ以外の場合、この関数の戻り値 **false**。  
  
## 解説  
 最初のオーバーライドは列番号を受け取り、2 番目と 3 番目のオーバーライドは ANSI 形式または Unicode 形式の項目の名前を指定します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicAccessor::SetLength](../../data/oledb/cdynamicaccessor-setlength.md)