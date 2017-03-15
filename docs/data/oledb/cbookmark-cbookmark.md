---
title: "CBookmark::CBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBookmark<0>.CBookmark<0>"
  - "CBookmark::CBookmark"
  - "ATL.CBookmark.CBookmark"
  - "CBookmark.CBookmark"
  - "CBookmark"
  - "ATL::CBookmark<0>::CBookmark<0>"
  - "ATL.CBookmark<0>.CBookmark<0>"
  - "CBookmark<0>::CBookmark<0>"
  - "ATL::CBookmark::CBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBookmark クラス, コンストラクター"
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBookmark::CBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コンストラクターです。  
  
## 構文  
  
```  
  
      CBookmark( );   
CBookmark(  
   DBLENGTH nSize   
);  
```  
  
#### パラメーター  
 `nSize`  
 \[\]バイトのブックマーク バッファーのサイズ。  
  
## 解説  
 最初の関数のセット **NULL** へのバッファーと 0 へのバッファーのサイズ。  2 番目の関数のセット `nSize`へのバッファーのサイズおよび `nSize` バイトのバイト配列へのバッファー。  
  
> [!NOTE]
>  この関数は **CBookmark\<0\>**でのみ使用できます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CBookmark クラス](../../data/oledb/cbookmark-class.md)