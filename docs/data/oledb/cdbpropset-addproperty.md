---
title: "CDBPropSet::AddProperty | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDBPropSet::AddProperty"
  - "CDBPropSet.AddProperty"
  - "AddProperty"
  - "ATL::CDBPropSet::AddProperty"
  - "ATL.CDBPropSet.AddProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddProperty メソッド"
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CDBPropSet::AddProperty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

プロパティ セットにプロパティを追加します。  
  
## 構文  
  
```  
  
      bool AddProperty(   
   DWORD dwPropertyID,   
   const VARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCSTR szValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCWSTR szValue,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   bool bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   BYTE bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   short nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   long nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   float fltValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   double dblValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   CY cyValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
```  
  
#### パラメーター  
 *dwPropertyID*  
 \[\]追加するプロパティの ID。  `DBPROP` 構造体の **dwPropertyID** を初期化するために使用されるプロパティ セットを追加しました。  
  
 `var`  
 \[\] `DBPROP` 構造体のプロパティ値を初期化するために使用される A のバリアントがプロパティ セットを追加しました。  
  
 `szValue`  
 \[\] `DBPROP` 構造体のプロパティ値を初期化するために使用される A の文字列がプロパティ セットを追加しました。  
  
 `bValue`  
 \[\] `DBPROP` 構造体のプロパティ値を初期化するために使用される A **BYTE** またはブール値は、プロパティ セットを追加しました。  
  
 `nValue`  
 \[\] `DBPROP` 構造体のプロパティ値を初期化するために使用された整数値がプロパティ セットを追加しました。  
  
 *fltValue*  
 \[\] `DBPROP` 構造体のプロパティ値を初期化するために使用される A の浮動小数点値のプロパティ セットに追加します。  
  
 `dblValue`  
 \[\] `DBPROP` 構造体のプロパティ値を初期化するために使用される A の倍精度浮動小数点値のプロパティ セットに追加します。  
  
 `cyValue`  
 \[\] `DBPROP` 構造体のプロパティ値を初期化するために使用される A CY の通貨値のプロパティ セットに追加します。  
  
## 戻り値  
 プロパティが正常に追加された場合**true**。  それ以外の場合は **false** を返します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDBPropSet クラス](../Topic/CDBPropSet%20Class.md)   
 [DBPROP Structure](https://msdn.microsoft.com/en-us/library/ms717970.aspx)