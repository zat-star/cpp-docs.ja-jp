---
title: "CDynamicAccessor::SetValue | Microsoft Docs"
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
  - "ATL.CDynamicAccessor.SetValue"
  - "ATL::CDynamicAccessor::SetValue"
  - "ATL::CDynamicAccessor::SetValue<ctype>"
  - "CDynamicAccessor.SetValue"
  - "ATL.CDynamicAccessor.SetValue<ctype>"
  - "CDynamicAccessor::SetValue"
  - "CDynamicAccessor::SetValue<ctype>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetValue メソッド"
ms.assetid: ecc18850-96e5-4845-abe5-ab34ad467238
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::SetValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された列にデータを保存します。  
  
## 構文  
  
```  
  
      template < class ctype >    
bool SetValue(   
   DBORDINAL nColumn,   
   const ctype& data    
) throw( );  
template < class ctype >    
bool SetValue(   
   const CHAR * pColumnName,   
   const ctype& data    
) throw( );  
template <class ctype>   
bool SetValue(  
   const WCHAR *pColumnName,  
   const ctype& data   
) throw( );  
```  
  
#### パラメーター  
 `ctype`  
 \[\]特別な処理を必要としますが、文字列型 \(**CHAR\***、**WCHAR\***\) 以外のデータ型を処理する A の template 宣言されたパラメーター。  `GetValue` に 応じて適切なデータ型をここで指定した内容に使用します。  
  
 `pColumnName`  
 \[\]列名を含む文字列へのポインター。  
  
 `data`  
 \[\]などメモリ データへのポインター。  
  
 `nColumn`  
 \[入力\] 列番号。  列番号は 1 から始まります。  0 番はブックマーク列です。  
  
## 戻り値  
 文字列データを設定する場合 `GetValue`の template 宣言がないなバージョンを使用します。  指定された列データを含むバッファーの一部を指します。このメソッドは **void\***の template 宣言がないなバージョンです。  列がない場合 **NULL** を返します。  
  
 そのほかのすべてのデータ型の場合、`GetValue`の template 宣言されたなバージョンを使用できます。  template 宣言されたなバージョンが成功の **true** または失敗の **false** を返します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)