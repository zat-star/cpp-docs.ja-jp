---
title: "ITopologyExecutionResource 構造体 | Microsoft Docs"
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
  - "concrtrm/concurrency::ITopologyExecutionResource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyExecutionResource 構造体"
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ITopologyExecutionResource 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

リソース マネージャーで定義される実行リソースへのインターフェイスです。  
  
## 構文  
  
```  
struct ITopologyExecutionResource;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ITopologyExecutionResource::GetId メソッド](../Topic/ITopologyExecutionResource::GetId%20Method.md)|この実行リソースのリソース マネージャーの一意の識別子を返します。|  
|[ITopologyExecutionResource::GetNext メソッド](../Topic/ITopologyExecutionResource::GetNext%20Method.md)|列挙体の次の順序で実行リソースへのインターフェイスを返します。|  
  
## 解説  
 リソース マネージャーによって確認されるシステムの段階的にこのインターフェイスは通常、トポロジ利用されます。  
  
## 継承階層  
 `ITopologyExecutionResource`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)