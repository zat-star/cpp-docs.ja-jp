---
title: "CDataSource::GetInitializationString | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CDataSource::GetInitializationString"
  - "CDataSource.GetInitializationString"
  - "GetInitializationString"
  - "CDataSource::GetInitializationString"
  - "ATL.CDataSource.GetInitializationString"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetInitializationString メソッド"
ms.assetid: 97134723-6e99-4004-a56d-ec57543dbf3b
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDataSource::GetInitializationString
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在開いているデータ ソースの初期化文字列を取得します。  
  
## 構文  
  
```  
  
      HRESULT GetInitializationString(   
   BSTR* pInitializationString,   
   bool bIncludePassword = false    
) throw( );  
```  
  
#### パラメーター  
 *pInitializationString*  
 \[\]初期化文字列へのポインター。  
  
 *bIncludePassword*  
 \[\]文字列にパスワードが含まれている場合 **true** ; それ **false**。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 発生した初期化文字列がこのデータ ソースの接続を再開するために使用できます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDataSource クラス](../Topic/CDataSource%20Class.md)