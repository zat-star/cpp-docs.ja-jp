---
title: "vararg | Microsoft Docs"
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
ms.assetid: aac0c54b-0a2d-4a22-b1de-ee41381a3eb1
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# vararg
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

vararg \(たとえば、省略記号 \(...\) の引数など\) を使用してパラメーターを渡す場合、基本的に、5 番目以降の引数があふれることを含めて、通常のパラメーター渡しの方法が適用されます。  受け取るアドレスを持つ引数をダンプするのは、呼び出し先の役割です。  浮動小数点値だけの場合、呼び出し先の整数レジスタに float 型の値を渡す必要があるときには、整数レジスタと浮動小数点レジスタの両方に float 型の値が含まれます。  
  
## 参照  
 [呼び出し規約](../build/calling-convention.md)