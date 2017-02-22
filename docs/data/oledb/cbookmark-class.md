---
title: "CBookmark クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CBookmark"
  - "ATL::CBookmark<nSize>"
  - "CBookmark"
  - "ATL.CBookmark<nSize>"
  - "ATL::CBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBookmark クラス"
ms.assetid: bc942f95-6f93-41d9-bb6e-bcdae4ae0b7a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# CBookmark クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

ブックマーク バッファーの値を保持します。  
  
## 構文  
  
```  
template < DBLENGTH nSize = 0 >  
class CBookmark : public CBookmarkBase  
template < >  
class CBookmark< 0 > : public CBookmarkBase  
```  
  
#### パラメーター  
 `nSize`  
 バイトのブックマーク バッファーのサイズ。  `nSize` がゼロの場合、ブックマーク バッファーは実行時に動的に作成されます。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CBookmark クラス](../../data/oledb/cbookmark-class.md)|コンストラクター|  
|[GetBuffer](../../data/oledb/cbookmark-getbuffer.md)|バッファーへのポインターを取得します。|  
|[GetSize](../../data/oledb/cbookmark-getsize.md)|バイトのバッファーのサイズを取得します。|  
|[SetBookmark](../../data/oledb/cbookmark-setbookmark.md)|ブックマーク値を設定します。|  
  
### 演算子  
  
|||  
|-|-|  
|[operator \=](../../data/oledb/cbookmark-operator-equal.md)|別の場所に `CBookmark` の 1 つがクラスを割り当てます。|  
  
## 解説  
 **CBookmark\<0\>** は `CBookmark`のテンプレートの特殊化;です このバッファーは実行時に動的に作成されます。  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)