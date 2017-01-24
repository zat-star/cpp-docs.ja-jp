---
title: "nonextensible 属性 | Microsoft Docs"
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
  - "nonextensible"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "デュアル インターフェイス, nonextensible 属性"
  - "nonextensible 属性"
ms.assetid: 02a4a18b-ffd3-4d53-8fd1-feb1c05ad5ac
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# nonextensible 属性
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

デュアル インターフェイスが、実行時 \(つまり、**IDispatch::Invoke** によって vtable で使用できないメソッドまたはプロパティを提供しません\) に拡張であるか、またはインターフェイスの定義に **nonextensible** の属性を適用する必要があります。  この属性は、コンパイル時に完全なコード検証を有効にするために使用できるクライアントの言語に関する情報を提供します \(Visual Basic など\)。  この属性を指定しない場合、バグは実行時までのクライアント コードで非表示のままになる場合があります。  
  
 **nonextensible** の属性と例の詳細については、[nonextensible](../Topic/nonextensible.md)を参照してください。  
  
## 参照  
 [デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)