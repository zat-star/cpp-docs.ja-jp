---
title: "CUtlProps クラス | Microsoft Docs"
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
  - "CUtlProps"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CUtlProps クラス"
ms.assetid: bb525178-765c-4e23-a110-c0fd70c05437
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CUtlProps クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

さまざまな OLE DB インターフェイスのプロパティのプロパティを実装します \(たとえば、`IDBProperties`、`IDBProperties`と `IRowsetInfo`\)。  
  
## 構文  
  
```  
template < class T >  
class ATL_NO_VTABLE CUtlProps : public CUtlPropsBase  
```  
  
#### パラメーター  
 `T`  
 `BEGIN_PROPSET_MAP`を含むクラスです。  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[GetPropValue](../Topic/CUtlProps::GetPropValue.md)|プロパティ セットからプロパティを取得します。|  
|[IsValidValue](../../data/oledb/cutlprops-isvalidvalue.md)|プロパティを設定する前に値を検証するために使用します。|  
|[OnInterfaceRequested](../../data/oledb/cutlprops-oninterfacerequested.md)|コンシューマーがオブジェクト作成インターフェイスのメソッドを呼び出すときに、省略可能なインターフェイスの要求。|  
|[OnPropertyChanged](../../data/oledb/cutlprops-onpropertychanged.md)|ハンドルへのプロパティを設定するというプロパティを連結します。|  
|[SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)|プロパティ セットのプロパティを設定します。|  
  
## 解説  
 このクラスのほとんどは実装の詳細になります。  
  
 `CUtlProps` は、プロパティを設定するためのメンバーが 2 つ内部的に含まれます: [GetPropValue](../Topic/CUtlProps::GetPropValue.md) と [SetPropValue](../../data/oledb/cutlprops-setpropvalue.md)。  
  
 プロパティ セット マップに使用されるマクロの詳細については [BEGIN\_PROPSET\_MAP](../Topic/BEGIN_PROPSET_MAP.md) と [END\_PROPSET\_MAP](../../data/oledb/end-propset-map.md)を参照します。  
  
## 必要条件  
 **ヘッダー:** atldb.h  
  
## 参照  
 [OLE DB プロバイダー テンプレート](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [OLE DB プロバイダー テンプレートのアーキテクチャ](../../data/oledb/ole-db-provider-template-architecture.md)