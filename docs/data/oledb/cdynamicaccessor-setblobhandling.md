---
title: "CDynamicAccessor::SetBlobHandling | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::SetBlobHandling"
  - "CDynamicAccessor.SetBlobHandling"
  - "ATL::CDynamicAccessor::SetBlobHandling"
  - "SetBlobHandling"
  - "ATL.CDynamicAccessor.SetBlobHandling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBlobHandling メソッド"
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetBlobHandling
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

現在の行の BLOB の処理値を設定します。  
  
## 構文  
  
```  
  
      bool SetBlobHandling(  
   DBBLOBHANDLINGENUM eBlobHandling   
);  
```  
  
#### パラメーター  
 `eBlobHandling`  
 BLOB データをどのように処理されるかどうかを指定します。  これは、次の値を設定できます。:  
  
-   **DBBLOBHANDLING\_DEFAULT**: BLOB データとして `nBlobSize` 大 \(ように `SetBlobSizeLimit`で設定された\) 列のデータを処理し、`ISequentialStream` または `IStream` オブジェクトを通じて取得してください。  このオプションは `nBlobSize` より大きい、または BLOB データとして **DBTYPE\_IUNKNOWN** として一覧表示されている任意のデータを含む列をバインドするようにしようとします。  
  
-   **DBBLOBHANDLING\_NOSTREAMS**: BLOB データとして `nBlobSize` 大 \(ように `SetBlobSizeLimit`で設定された\) 列のデータを処理し、プロバイダーは、コンシューマー所有割り当てられたメモリの参照によって取得してください。  このオプションは、複数の BLOB の列には、プロバイダーは、アクセサー 1 人の `ISequentialStream` の 1 種類のオブジェクトだけをサポートするテーブルに役立ちます。  
  
-   **DBBLOBHANDLING\_SKIP**: \(バインド\) は Blob を含むとして修飾する列を省略します \(アクセサーに列の値をバインドしませんされますが、まだ取得しません列のステータスと長さを取得します。  
  
## 解説  
 **開く**を呼び出す前に `SetBlobHandling` を呼び出す必要があります。  
  
 コンストラクター メソッド [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) は **DBBLOBHANDLING\_DEFAULT**BLOB の処理に値を設定します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)