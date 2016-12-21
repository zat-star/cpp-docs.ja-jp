---
title: "CreatorMap 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "module/Microsoft::WRL::Details::CreatorMap"
  - "implements/Microsoft::WRL::Details::CreatorMap"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreatorMap 構造体"
ms.assetid: 94e40927-90c3-4107-bca3-3ad2dc4beda9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CreatorMap 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] インフラストラクチャをサポートします。コードから直接使用するためのものではありません。  
  
## 構文  
  
```  
struct CreatorMap;  
```  
  
## 解説  
 オブジェクトを初期化し、登録および登録解除する方法について説明します。  
  
 CreatorMap は以下の情報が含まれています。:  
  
-   オブジェクトを初期化し、登録および登録解除する方法。  
  
-   標準的な COM または [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] ファクトリでアクティベーション データを比較する方法。  
  
-   インターフェイスのファクトリのキャッシュおよびサーバー名について説明します。  
  
## メンバー  
  
### パブリック データ メンバー  
  
|名前|説明|  
|--------|--------|  
|[CreatorMap::activationId データ メンバー](../windows/creatormap-activationid-data-member.md)|標準的な COM クラス ID または [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] 名で示されるオブジェクト ID を表します。|  
|[CreatorMap::factoryCache データ メンバー](../windows/creatormap-factorycache-data-member.md)|CreatorMap のファクトリのキャッシュへのポインターを格納します。|  
|[CreatorMap::factoryCreator データ メンバー](../Topic/CreatorMap::factoryCreator%20Data%20Member.md)|指定 CreatorMap のファクトリを作成します。|  
|[CreatorMap::serverName データ メンバー](../windows/creatormap-servername-data-member.md)|CreatorMap のサーバー名を格納します。|  
  
## 継承階層  
 `CreatorMap`  
  
## 必要条件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL::Details  
  
## 参照  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)