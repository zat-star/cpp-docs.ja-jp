---
title: "IRowsetImpl::m_bReset | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetImpl.m_bReset"
  - "IRowsetImpl.m_bReset"
  - "m_bReset"
  - "IRowsetImpl::m_bReset"
  - "ATL::IRowsetImpl::m_bReset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_bReset"
ms.assetid: d423f9f3-4d48-4d0c-b152-684c81a0b34e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::m_bReset
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

小さい行セット カーソル位置が定義されているかどうかを確認するために使用するフラグ。  
  
## 構文  
  
```  
  
unsigned m_bReset:1;  
  
```  
  
## 解説  
 負のな `lOffset` または *カラス* とコンシューマーの呼び出し [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) と `m_bReset` が TRUE の場合、`GetNextRows` は行セットの末尾に移動します。  `m_bReset` が false の場合、コンシューマーは、OLE DB 仕様に一致するエラー コードを受け取ります。  `m_bReset` フラグを **true** に行セットが最初に作成されたときや、コンシューマーが [IRowsetImpl::RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)を呼び出すときに設定を取得します。  これは **false** に `GetNextRows`を呼び出すときに設定を取得します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [IRowsetImpl クラス](../Topic/IRowsetImpl%20Class.md)