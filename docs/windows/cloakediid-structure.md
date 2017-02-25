---
title: "CloakedIid 構造体 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::CloakedIid"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CloakedIid 構造体"
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 3
---
# CloakedIid 構造体
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

指定されたインターフェイスの IID の一覧にアクセスできないこと RuntimeClass、実装と ChainInterfaces のテンプレートについて説明します。  
  
## 構文  
  
```  
template<  
   typename T  
>  
struct CloakedIid : T;  
```  
  
#### パラメーター  
 `T`  
 非インターフェイス \(クローク\)。  
  
## 解説  
 次に CloakedIid を使用する方法の例です: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`。  
  
## 継承階層  
 `T`  
  
 `CloakedIid`  
  
## 必要条件  
 **ヘッダー:** implements.h  
  
 **名前空間:** Microsoft::WRL  
  
## 参照  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)