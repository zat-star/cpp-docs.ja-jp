---
title: "CDynamicAccessor::SetBlobSizeLimit | Microsoft Docs"
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
  - "CDynamicAccessor::SetBlobSizeLimit"
  - "SetBlobSizeLimit"
  - "CDynamicAccessor.SetBlobSizeLimit"
  - "ATL.CDynamicAccessor.SetBlobSizeLimit"
  - "ATL::CDynamicAccessor::SetBlobSizeLimit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBlobSizeLimit メソッド"
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::SetBlobSizeLimit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

最大バイト BLOB のサイズを設定します。  
  
## 構文  
  
```  
  
      void SetBlobSizeLimit(  
   DBLENGTH nBlobSize   
);  
```  
  
#### パラメーター  
 `nBlobSize`  
 BLOB のサイズ制限を指定します。  
  
## 解説  
 最大バイト BLOB のサイズを設定して; この値は、列のデータが BLOB として扱われます。  一部のプロバイダーは列のきわめて大きなサイズを与えます \(2 GB など\)。  列のメモリを割り当てようとしてではなく、このサイズ \(通常は Blob としてその列をバインドするようにします。  当然ではすべてのメモリを割り当てる必要はありません。まだ切り捨ての重大なしのすべてのデータを読み取ることができます。  ただし、ネイティブ データ型の、列をバインドするために `CDynamicAccessor` を強制することが必要な場合もあります。  これを行うには、**開く**を呼び出す前に `SetBlobSizeLimit` を呼び出します。  
  
 コンストラクター メソッド [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) は、8,000 バイトの既定値に最大 BLOB のサイズを設定します。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [CDynamicAccessor クラス](../../data/oledb/cdynamicaccessor-class.md)