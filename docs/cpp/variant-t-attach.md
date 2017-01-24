---
title: "_variant_t::Attach | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "_variant_t::Attach"
  - "_variant_t.Attach"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Attach メソッド"
  - "VARIANT オブジェクト"
  - "VARIANT オブジェクト, アタッチ"
ms.assetid: 2f02bd08-2306-4477-aa88-d2a5dee2b859
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _variant_t::Attach
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `_variant_t` オブジェクトに **VARIANT** オブジェクトをアタッチします。  
  
## 構文  
  
```  
  
      void Attach(  
   VARIANT& varSrc   
);  
```  
  
#### パラメーター  
 *varSrc*  
 この `_variant_t` オブジェクトにアタッチされる **VARIANT** オブジェクト。  
  
## 解説  
 **VARIANT** をカプセル化することで、その所有権を取得します。  このメンバー関数は、既存のカプセル化された **VARIANT** を解放し、指定された **VARIANT** をコピーし、その **VARTYPE** を `VT_EMPTY` に設定して、そのリソースを `_variant_t` デストラクターのみが解放できるようにします。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [\_variant\_t クラス](../cpp/variant-t-class.md)