---
title: "CAccessorBase クラス | Microsoft Docs"
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
  - "CAccessorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessorBase クラス"
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessorBase クラス
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

OLE DB テンプレートのすべてのアクセサーは、クラスから派生します。  `CAccessorBase` は 1 行セットでの複数アクセサーを管理できるようになります。  また、パラメーターと出力列の両方にバインドを提供します。  
  
## 構文  
  
```  
// Replace with syntax  
```  
  
## メンバー  
  
### メソッド  
  
|||  
|-|-|  
|[&#91;閉じる&#93;](../../data/oledb/caccessorbase-close.md)|アクセサーを閉じます。|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|アクセサー ハンドルを取得します。|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|クラスによって作成されたアクセサーの数を取得します。|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|指定アクセサー番号であるかどうかをテストします。|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|アクセサーを解放します。|  
  
## 必要条件  
 **ヘッダー:** atldbcli.h  
  
## 参照  
 [OLE DB コンシューマー テンプレート](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [OLE DB コンシューマー テンプレート リファレンス](../../data/oledb/ole-db-consumer-templates-reference.md)