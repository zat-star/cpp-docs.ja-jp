---
title: "CRowsetImpl::GetCommandFromID | Microsoft Docs"
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
  - "CRowsetImpl::GetCommandFromID"
  - "GetCommandFromID"
  - "CRowsetImpl.GetCommandFromID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCommandFromID メソッド"
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::GetCommandFromID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

その場合は、いずれか一方または両方のパラメーターがデータ メンバー [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) と [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)に文字列値をコピー文字列値に含まれている参照するかどうかを調べます。  
  
## 構文  
  
```  
  
      HRESULT CRowsetBaseImpl::GetCommandFromID(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### パラメーター  
 `pTableID`  
 \[\]テーブルを表す **DBID** ID へのポインター。  
  
 `pIndexID`  
 \[\]インデックスを表す **DBID** ID へのポインター。  
  
## 戻り値  
 標準の `HRESULT` を返します。  
  
## 解説  
 このメソッドは `CRowsetImpl` で静的なアップキャストを通じてデータ メンバー [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) と [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)を設定するために呼び出されます。  既定では、いずれか一方または両方のパラメーターが文字列値が含まれている場合は、メソッドを確認します。  これらの文字列値が含まれている場合、このメソッドのコピー データ メンバーに文字列値。  `CRowsetImpl`にこのシグネチャを持つメソッドを設定して\-派生クラスは、基本実装の代わりに、メソッドが呼び出されます。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [CRowsetImpl クラス](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)