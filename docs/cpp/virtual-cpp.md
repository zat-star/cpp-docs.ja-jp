---
title: "virtual (C++) | Microsoft Docs"
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
  - "virtual_cpp"
  - "virtual"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "基本クラス, virtual"
  - "仮想基本クラス, 宣言"
  - "仮想関数, 宣言"
  - "virtual キーワード [C++]"
ms.assetid: c2eb987d-6cf3-43b6-aa0c-29a6f561b1ae
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# virtual (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`virtual` キーワードは仮想関数または仮想基底クラスを宣言します。  
  
## 構文  
  
```  
virtual [type-specifiers] member-function-declarator  
virtual [access-specifier] base-class-name  
```  
  
#### パラメーター  
 `type-specifiers`  
 仮想メンバー関数の戻り値の型を指定します。  
  
 `member-function-declarator`  
 メンバー関数を宣言します。  
  
 `access-specifier`  
 基底クラスへのアクセス レベルとして `public`、`protected`、または `private` を定義します。  `virtual` キーワードの前または後に指定できます。  
  
 `base-class-name`  
 以前に宣言されたクラス型を識別します。  
  
## 解説  
 詳細については、「[仮想関数](../cpp/virtual-functions.md)」および「[仮想基底クラス](../Topic/Virtual%20Base%20Classes.md)」を参照してください。  
  
 また、次のキーワードも参照してください。[class](../cpp/class-cpp.md)、[private](../Topic/private%20\(C++\).md)、[public](../cpp/public-cpp.md)、および [protected](../Topic/protected%20\(C++\).md)。  
  
## 参照  
 [C\+\+ キーワード](../cpp/keywords-cpp.md)