---
title: "ブロック スコープを持つ名前にあるリンケージ | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ブロック スコープ [C++]"
  - "外部リンケージ, スコープ リンケージの規則"
  - "リンケージ [C++], スコープ リンケージの規則"
  - "名前 [C++], スコープ リンケージの規則"
  - "スコープ [C++], リンケージの規則"
ms.assetid: 73efa91a-f761-47f7-bbd9-9f9e3508e218
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# ブロック スコープを持つ名前にあるリンケージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

次のリンケージ規則はブロック スコープの名前に適用されます \(ローカル名\)。  
  
-   `extern`static として宣言されていない限り、 **として宣言されている名前には外部リンケージがあります。**  
  
-   ブロック スコープを持つ他のすべての名前にはリンケージがありません。  
  
## 参照  
 [プログラムとリンケージ](../cpp/program-and-linkage-cpp.md)