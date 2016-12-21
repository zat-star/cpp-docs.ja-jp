---
title: "MixIn 構造体 | Microsoft Docs"
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
  - "implements/Microsoft::WRL::MixIn"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MixIn 構造体"
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MixIn 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次にランタイム クラスが [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] インターフェイス \(存在する場合\)、および従来の COM インターフェイスから派生することを確認します。  
  
## 構文  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### パラメーター  
 `Derived`  
 [実装](../Topic/Implements%20Structure.md) 構造体から派生される型。  
  
 `MixInType`  
 基本データ型。  
  
 `hasImplements`  
 `MixInType` が 現在の実装から基本型派生されれば`true` ; 別の方法で `false`。  
  
## 解説  
 次に、クラスが [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] の両方から派生され、クラスを COM インターフェイスは、クラスの宣言では、最初に [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] インターフェイスと標準的な COM インターフェイスを記述する必要があります。  MixIn はインターフェイスが正しい順序で指定されていることを確認します。  
  
## 継承階層  
 `MixIn`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)