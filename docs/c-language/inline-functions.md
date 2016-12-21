---
title: "インライン関数 | Microsoft Docs"
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
  - "高速コード"
  - "関数 [C++], インライン関数"
  - "インライン関数, __inline キーワード"
ms.assetid: 00f4b2ff-8ad0-4165-9f4c-2ef157d03f31
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# インライン関数
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Microsoft 固有の仕様 →**  
  
 `__inline` キーワードは、関数呼び出しのすべてのインスタンスを、関数定義内のコードに置き換えるようコンパイラに指示します。  ただし、実際に置き換えるかどうかは、コンパイラの判断に任されています。  たとえば、関数のアドレスが取得されている場合、または、関数が大きすぎてインライン展開できない場合、関数はインライン展開されません。  
  
 関数をインライン展開の候補とするには、新しいスタイルの関数定義を使用する必要があります。  
  
 インライン関数を指定するには、この形式を使用します。  
  
 `__inline` *type*opt *function\-definition*`;`  
  
 インライン関数を使用すると、次の理由により、同等の関数呼び出しで生成されるコードよりも速いコードが生成され、ときにはサイズが小さくなることもあります。  
  
-   関数呼び出しを実行するために必要な時間が短縮されます。  
  
-   引数と戻り値を処理するコードが生成されないため、小さなインライン関数 \(およそ 3 行以下\) であれば、同等の関数呼び出しよりも生成されるコードが小さくなります。  
  
-   コンパイラでは関数を超えた最適化が実行されないため、通常の関数呼び出しではコード最適化の対象になりませんが、インライン展開された関数はコード最適化の対象になります。  
  
 `__inline` を使用する関数を、インライン アセンブラー コードと混同しないでください。  詳細については、「[インライン アセンブラー](../c-language/inline-assembler-c.md)」を参照してください。  
  
 **END Microsoft 固有の仕様**  
  
## 参照  
 [inline、\_\_inline、\_\_forceinline](../misc/inline-inline-forceinline.md)