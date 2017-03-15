---
title: "naked (C) | Microsoft Docs"
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
helpviewer_keywords: 
  - "エピローグ コード"
  - "naked キーワード [C]"
  - "naked キーワード [C], ストレージ クラス属性"
  - "プロローグ コード"
ms.assetid: 23b1209b-93ba-46ad-a60f-2327c1933eaf
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# naked (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 naked ストレージ クラス属性は C 言語への Microsoft 固有の拡張機能です。  コンパイラは、naked ストレージ クラス属性を指定して宣言されている関数に対しては、プロローグ コードおよびエピローグ コードを含まないコードを生成します。  naked 関数は、インライン アセンブラー コードを使用してプロローグとエピローグのコード シーケンスを独自に作成する必要がある場合に便利です。  naked 関数は、仮想デバイス ドライバーの記述時に特に便利です。  
  
 naked 属性の使用に関する具体的情報については、「[naked 関数](../c-language/naked-functions.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [C 拡張ストレージ クラス属性](../c-language/c-extended-storage-class-attributes.md)