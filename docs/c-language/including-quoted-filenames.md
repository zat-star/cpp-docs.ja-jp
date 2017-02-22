---
title: "引用符で囲まれたファイル名を含む | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 789a047e-ea38-4c99-b71d-a2ad9c81daee
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# 引用符で囲まれたファイル名を含む
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 3.8.2** インクルード可能なソース ファイルの引用された名前のサポート  
  
 2 組の二重引用符 \(" "\) 間にインクルード ファイルのあいまいでない完全なパスを指定すると、プリプロセッサはそのパスのみを検索し、標準ディレクトリを無視します。  
  
 [\#include](../preprocessor/hash-include-directive-c-cpp.md) "path\-spec" に指定されたインクルード ファイルでは、ディレクトリの検索は親ファイルのディレクトリから始まり、その後にすべての祖父母ファイルのディレクトリが検索されます。  したがって、検索は現在処理中のソース ファイルが含まれるディレクトリに対して相対的に開始されます。  親の親ファイルが存在せず、見つからなかった場合は、ファイル名が山かっこで囲まれているものとして検索が続行されます。  
  
## 参照  
 [プリプロセス ディレクティブ](../Topic/Preprocessing%20Directives.md)