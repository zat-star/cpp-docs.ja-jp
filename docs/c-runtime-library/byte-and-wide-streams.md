---
title: "バイト ストリームとワイド ストリーム | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "Byte and Wide Streams"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "バイト ストリーム"
  - "ワイド ストリーム"
ms.assetid: 61ef0587-4cbc-4eb8-aae5-4c298dbbc6f9
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# バイト ストリームとワイド ストリーム
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

バイト ストリームは、バイトのシーケンスとしてファイルを扱います。  プログラム内では、ストリームは、バイトのシーケンスです。  
  
 一方、柔軟なストリームは、エンコーディング規則の広い範囲を持つことができる汎用的なマルチバイト文字のシーケンスとしてファイルを扱います。\(テキストとバイナリ ファイルは、前に説明したように読み取って書き込まれます\)。プログラム内では、ストリームはワイド文字の対応するシーケンスのようになります。  2 個の表現との変換は標準 C ライブラリ内で発生します。  変換規則がカテゴリ `LC_CTYPE`を変更 [setlocale](../Topic/setlocale,%20_wsetlocale.md) への呼び出しによって、原則として、変更できます。  それぞれの幅ストリームは、カテゴリ `LC_CTYPE` を後で変更する細繰り返すように記述し、これらの規則を保持する変換規則について説明します。  
  
 柔軟なストリーム内の位置は、テキストのストリームのと同じ制約に陥ります。  また、ファイル位置インジケーターは状態依存エンコーディングを使用する必要があります。  通常は、ストリーム内のバイト オフセット、型 `mbstate_t`オブジェクトの両方が含まれます。  したがって、フレキシブル ストリーム内のファイルの位置を取得する唯一の信頼性の高い方法は、[fgetpos](../c-runtime-library/reference/fgetpos.md)を呼び出して実行し、配置を復元する唯一の信頼性の高い方法は、[fsetpos](../Topic/fsetpos.md)を呼び出してこのメソッドを実行して取得。  
  
## 参照  
 [ファイルとストリーム](../c-runtime-library/files-and-streams.md)   
 [setlocale、\_wsetlocale](../Topic/setlocale,%20_wsetlocale.md)