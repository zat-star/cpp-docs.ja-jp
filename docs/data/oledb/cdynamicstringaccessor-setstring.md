---
title: "CDynamicStringAccessor::SetString | Microsoft Docs"
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
  - "CDynamicStringAccessor::SetString"
  - "CDynamicStringAccessor.SetString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetString メソッド"
ms.assetid: 94846d8b-4c1b-47fe-acdc-1752981cee25
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicStringAccessor::SetString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

文字列として指定された列データを設定します。  
  
## 構文  
  
```  
HRESULT SetString(  
   DBORDINAL nColumn,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const CHAR* pColumnName,  
   BaseType* data  
) throw( );  
HRESULT SetString(  
   const WCHAR* pColumnName,  
   BaseType* data  
) throw( );  
```  
  
#### パラメーター  
 `nColumn`  
 \[入力\] 列番号。  列番号は 1 から始まります。  0 の特殊な値はブックマーク列です。  
  
 `pColumnName`  
 \[入力\] 列名を含む文字列へのポインター。  
  
 `data`  
 \[\]指定された列に書き込まれる文字列データへのポインター。  
  
## 戻り値  
 指定された列を設定した文字列値へのポインター。  値の型は `BaseType``_UNICODE`が定義されているかどうか `CHAR`または `WCHAR`のです。  
  
## 解説  
 2 番目のオーバーライド フォームは ANSI を対象とし、3 番目のオーバーライド フォームは、Unicode 文字列として列名を受け取るとして列名を取得します。  
  
 0 以外の値で `_SECURE_ATL` は定義されているランタイムのアサーションは入力 `data` の文字列の参照元データ列の最大長よりも生成されます。  それ以外の場合は、入力文字列が最大長よりも切り捨てられます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicStringAccessor クラス](../../data/oledb/cdynamicstringaccessor-class.md)