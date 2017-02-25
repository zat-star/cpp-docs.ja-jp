---
title: "ICommandPropertiesImpl クラス | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ICommandPropertiesImpl"
  - "ATL.ICommandPropertiesImpl"
  - "ATL::ICommandPropertiesImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ICommandPropertiesImpl クラス"
ms.assetid: b3cf6aea-527e-4f0d-96e0-669178b021a2
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# ICommandPropertiesImpl クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[ICommandProperties](https://msdn.microsoft.com/en-us/library/ms723044.aspx) インターフェイスの実装を提供します。  
  
## 構文  
  
```  
template <class T, class PropClass = T>  
class ATL_NO_VTABLE ICommandPropertiesImpl   
   : public ICommandProperties, public CUtlProps<PropClass>  
```  
  
#### パラメーター  
 `T`  
 クラス、からの派生  
  
 `PropClass`  
 プロパティ クラス。  
  
## メンバー  
  
### インターフェイス メソッド  
  
|||  
|-|-|  
|[GetProperties](../../data/oledb/icommandpropertiesimpl-getproperties.md)|行セットに現在要求された行セット プロパティ グループのプロパティのリストを返します。|  
|[SetProperties](../Topic/ICommandPropertiesImpl::SetProperties.md)|行セット プロパティ グループのプロパティを設定します。|  
  
## 解説  
 これは、コマンドで必須です。  実装は [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md) マクロによって定義された静的関数によって提供されます。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)