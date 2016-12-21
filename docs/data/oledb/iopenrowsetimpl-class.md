---
title: "IOpenRowsetImpl クラス | Microsoft Docs"
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
  - "IOpenRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IOpenRowsetImpl クラス"
ms.assetid: d259cedc-1db4-41cf-bc9f-5030907ab486
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IOpenRowsetImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

`IOpenRowset` インターフェイスの実装を提供します。  
  
## 構文  
  
```  
template <class SessionClass>  
class IOpenRowsetImpl : public IOpenRowset  
```  
  
#### パラメーター  
 `SessionClass`  
 クラス、`IOpenRowsetImpl`から派生します。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[CreateRowset](../../data/oledb/iopenrowsetimpl-createrowset.md)|行セット オブジェクトを作成します。  直接ユーザーによって呼び出された場合。|  
|[OpenRowset](../Topic/IOpenRowsetImpl::OpenRowset.md)|単一のベース テーブルまたはインデックスのすべての行を含む行セットを開き、返します。ATLDB.H\) ではなく、|  
  
## 解説  
 [IOpenRowset](https://msdn.microsoft.com/en-us/library/ms716946.aspx) インターフェイスは、セッション オブジェクトのために必須です。  これは、単一のベース テーブルまたはインデックスのすべての行を含む行セットを開き、返します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)