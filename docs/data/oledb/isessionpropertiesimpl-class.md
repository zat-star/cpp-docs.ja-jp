---
title: "ISessionPropertiesImpl クラス | Microsoft Docs"
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
  - "ISessionPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ISessionPropertiesImpl クラス"
ms.assetid: ca0ba254-c7dc-4c52-abec-cf895a0c6a63
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ISessionPropertiesImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[ISessionProperties](https://msdn.microsoft.com/en-us/library/ms713721.aspx) インターフェイスの実装を提供します。  
  
## 構文  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ISessionPropertiesImpl :  
   public ISessionProperties,    
   public CUtlProps<PropClass>  
```  
  
#### パラメーター  
 `T`  
 クラス、`ISessionPropertiesImpl`から派生します。  
  
 `PropClass`  
 ユーザー定義のクラスは `T`になります。  
  
## メンバー  
  
### インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/isessionpropertiesimpl-getproperties.md)|セッションで現在設定されているセッション プロパティ グループのプロパティのリストを返します。|  
|[SetProperties](../../data/oledb/isessionpropertiesimpl-setproperties.md)|セッション プロパティ グループのプロパティを設定します。|  
  
## 解説  
 セッションの必須インターフェイス。  このクラスには、静的関数を [プロパティ セット マップ](../Topic/BEGIN_PROPSET_MAP.md)によって定義された呼び出してセッション プロパティを実装します。  プロパティ セット マップには、セッション クラスで指定する必要があります。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)