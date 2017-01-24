---
title: "内部リンケージ | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "内部リンケージ"
  - "リンケージ [C++], internal"
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 内部リンケージ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

オブジェクトまたは関数のファイル スコープ ID の宣言に \<ストレージ クラス指定子\> **static** が含まれている場合、ID には内部リンケージがあります。  それ以外の場合、識別子は外部リンケージを持ちます。  必須ではない要素である *storage\-class\-specifier* の詳細については、「[ストレージ クラス](../c-language/c-storage-classes.md)」を参照してください。  
  
 1 つの翻訳単位内では、内部リンケージを持つ識別子の各インスタンスは、同じ識別子または関数を表します。  内部リンク ID は 1 つの翻訳単位において一意です。  
  
## 参照  
 [extern を使用したリンケージの指定](../cpp/using-extern-to-specify-linkage.md)