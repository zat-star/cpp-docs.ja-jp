---
title: "ITopologyNode 構造体 | Microsoft Docs"
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
  - "concrtrm/concurrency::ITopologyNode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ITopologyNode 構造体"
ms.assetid: 92e7e032-04f6-4c7c-be36-8f9a35fc4734
caps.latest.revision: 10
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ITopologyNode 構造体
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

リソース マネージャーで定義されるトポロジ ノードへのインターフェイスです。  ノードには 1 つ以上の実行リソースが含まれます。  
  
## 構文  
  
```  
struct ITopologyNode;  
```  
  
## メンバー  
  
### パブリック メソッド  
  
|名前|説明|  
|--------|--------|  
|[ITopologyNode::GetExecutionResourceCount メソッド](../Topic/ITopologyNode::GetExecutionResourceCount%20Method.md)|このノードの下にグループ化されている実行リソースの数を返します。|  
|[ITopologyNode::GetFirstExecutionResource メソッド](../Topic/ITopologyNode::GetFirstExecutionResource%20Method.md)|列挙体の順序でこのノードの下にグループ化されている最初の実行リソースを返します。|  
|[ITopologyNode::GetId メソッド](../Topic/ITopologyNode::GetId%20Method.md)|このノードのリソース マネージャーの一意の識別子を返します。|  
|[ITopologyNode::GetNext メソッド](../Topic/ITopologyNode::GetNext%20Method.md)|列挙体の順序で次のトポロジ ノードへのインターフェイスを返します。|  
|[ITopologyNode::GetNumaNode メソッド](../Topic/ITopologyNode::GetNumaNode%20Method.md)|Windows が割り当てた、このリソース マネージャー ノードが属する、NUMA ノードの数を返します。|  
  
## 解説  
 リソース マネージャーによって確認されるシステムの段階的にこのインターフェイスは通常、トポロジ利用されます。  
  
## 継承階層  
 `ITopologyNode`  
  
## 必要条件  
 **ヘッダー:** concrtrm.h  
  
 **名前空間:** concurrency  
  
## 参照  
 [concurrency 名前空間](../../../parallel/concrt/reference/concurrency-namespace.md)