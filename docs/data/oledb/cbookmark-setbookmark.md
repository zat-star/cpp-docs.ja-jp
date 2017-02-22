---
title: "CBookmark::SetBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBookmark<0>::SetBookmark"
  - "ATL.CBookmark<0>.SetBookmark"
  - "CBookmark<0>.SetBookmark"
  - "SetBookmark"
  - "ATL::CBookmark::SetBookmark"
  - "ATL::CBookmark<0>::SetBookmark"
  - "CBookmark.SetBookmark"
  - "ATL.CBookmark.SetBookmark"
  - "CBookmark::SetBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBookmark メソッド"
ms.assetid: bcd26831-6045-4e69-96d6-abf8037fc18d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBookmark::SetBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`CBookmark` バッファーに `pBuffer` によって参照されるブックマーク値をコピーし、`nSize`にバッファーのサイズを設定します。  
  
## 構文  
  
```  
  
      HRESULT SetBookmark(  
   DBLENGTH nSize,  
   BYTE* pBuffer   
) throw( );  
```  
  
#### パラメーター  
 *nSize*  
 \[\]ブックマーク バッファーのサイズ。  
  
 `pBuffer`  
 \[\]を格納するバイト配列へのポインター。ブックマーク値。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 この関数は **CBookmark\<0\>**でのみ使用できます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CBookmark クラス](../../data/oledb/cbookmark-class.md)