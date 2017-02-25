---
title: "CDynamicAccessor::GetValue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetValue"
  - "CDynamicAccessor::GetValue<ctype>"
  - "ATL.CDynamicAccessor.GetValue<ctype>"
  - "CDynamicAccessor.GetValue"
  - "CDynamicAccessor::GetValue"
  - "ATL.CDynamicAccessor.GetValue"
  - "ATL::CDynamicAccessor::GetValue"
  - "ATL::CDynamicAccessor::GetValue<ctype>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetValue メソッド"
ms.assetid: 553f44af-68bc-4cb6-8774-e0940003fa90
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::GetValue
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

指定された列のデータを取得します。  
  
## 構文  
  
```  
  
      void* GetValue(   
   DBORDINAL nColumn    
) const throw( );  
void* GetValue(  
   const CHAR* pColumnName   
) const throw( );  
void* GetValue(  
   const WCHAR* pColumnName   
) const throw( );  
template < class ctype >  
bool GetValue(  
   DBORDINAL nColumn,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const CHAR* pColumnName,  
   ctype* pData   
) const throw( );  
template < class ctype >  
bool GetValue(  
   const WCHAR* pColumnName,  
   ctype* pData   
) const throw( );  
```  
  
#### パラメーター  
 `ctype`  
 \[\]特別な処理を必要としますが、文字列型 \(**CHAR\***、**WCHAR\***\) 以外のデータ型を処理する A の template 宣言されたパラメーター。  `GetValue` に 応じて適切なデータ型をここで指定した内容に使用します。  
  
 `nColumn`  
 \[入力\] 列番号。  列番号は 1 から始まります。  0 番はブックマーク列です。  
  
 `pColumnName`  
 \[\]項目の名前です。  
  
 `pData`  
 \[\]指定した列の値へのポインター。  
  
## 戻り値  
 文字列データを渡す場合は、`GetValue`の template 宣言がないなバージョンを使用します。  指定された列データを含むバッファーの一部を指します。このメソッドは **void\***の template 宣言がないなバージョンです。  列がない場合 **NULL** を返します。  
  
 そのほかのすべてのデータ型の場合、`GetValue`の template 宣言されたなバージョンを使用できます。  template 宣言されたなバージョンが成功の **true** または失敗の **false** を返します。  
  
## 解説  
 他のデータ型を含む列の文字列と template 宣言されたなバージョンを含む列を返すには、template 宣言がないなバージョンを使用します。  
  
 デバッグ モードでは、`pData` のサイズが指す列のサイズに等しくない場合アサーションを取得します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)