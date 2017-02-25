---
title: "com::ptr | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "com::ptr"
ms.assetid: ee302e3c-8fed-4875-a372-2e55003718d3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# com::ptr
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

CLR クラスのメンバーとして使用できる COM オブジェクトのラッパー。  ラッパーは、デストラクターが呼び出されると、所有されているオブジェクトの参照を解放する COM オブジェクトの有効期間管理を自動化します。  [CComPtr クラス](../atl/reference/ccomptr-class.md)と似ています。  
  
## 構文  
  
```  
#include <msclr\com\ptr.h>  
```  
  
## 解説  
 [com::ptr Class](../dotnet/com-ptr-class.md) は msclr\\com\\ptr.h ファイルで \<定義されます\>。  
  
## 参照  
 [C\+\+ のサポート ライブラリ](../dotnet/cpp-support-library.md)