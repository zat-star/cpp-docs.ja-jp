---
title: "&lt;iostream&gt; | Microsoft Docs"
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
  - "std.<iostream>"
  - "std::<iostream>"
  - "<iostream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "iostream ヘッダー"
ms.assetid: de5d39e1-7e77-4b55-bcd1-7c77b41515c8
caps.latest.revision: 23
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;iostream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

標準ストリームに対する読み取りと書き込みを制御するオブジェクトを宣言します。  これは、多くの場合、C\+\+ プログラムから入力と出力を実行するために含める必要がある唯一のヘッダーです。  
  
## 構文  
  
```  
  
#include <iostream>  
  
```  
  
## 解説  
 このオブジェクトは、次の 2 つのグループに分類されます。  
  
-   [cin](../Topic/cin.md)、[cout](../Topic/cout.md)、[cerr](../Topic/cerr.md)、および [clog](../Topic/clog.md) はバイト指向で、従来のバイト単位の転送を実行します。  
  
-   [wcin](../Topic/wcin.md)、[wcout](../Topic/wcout.md)、[wcerr](../Topic/wcerr.md)、および [wclog](../Topic/wclog.md) はワイド指向で、プログラムが内部で操作するワイド文字に翻訳したり、ワイド文字から翻訳したりします。  
  
 標準入力など、ストリームで特定の操作を実行すると、同じストリームで別の指向の操作を実行できません。  そのため、[cin](../Topic/cin.md) と [wcin](../Topic/wcin.md) など、両者に対するプログラムの操作に互換性はありません。  
  
 このヘッダーで共有されたすべてのオブジェクトは、特有のプロパティを共有します。\<iostream\> を含む翻訳単位では、定義するすべての静的なオブジェクトの前に、これらのオブジェクトが構築されていると仮定できます。  同様に、このような定義するすべての静的オブジェクトのデストラクターの前に、これらのオブジェクトが破棄されないと仮定できます   \(ただし、出力ストリームはプログラムの終了時にフラッシュされます\)。 そのため、プログラムの開始前とプログラムの終了後に、標準ストリームに対する安全な読み取りまたは書き込みを行うことができます。  
  
 ただし、この保証は汎用的ではありません。  静的コンストラクターは、別の翻訳単位で、関数を呼び出す場合があります。  静的な構築に含まれる翻訳単位の順序が不明な場合、呼び出された関数では、このヘッダーで宣言されたオブジェクトが構築済みであるとは仮定できません。  このようなコンテキストでこれらのオブジェクトを使用するには、最初にクラス [ios\_base::Init](../Topic/ios_base::Init.md) のオブジェクトを構築します。  
  
### グローバル ストリーム オブジェクト  
  
|||  
|-|-|  
|[cerr](../Topic/cerr.md)|`cerr` グローバル ストリームを指定します。|  
|[cin](../Topic/cin.md)|`cin` グローバル ストリームを指定します。|  
|[clog](../Topic/clog.md)|`clog` グローバル ストリームを指定します。|  
|[cout](../Topic/cout.md)|`cout` グローバル ストリームを指定します。|  
|[wcerr](../Topic/wcerr.md)|`wcerr` グローバル ストリームを指定します。|  
|[wcin](../Topic/wcin.md)|`wcin` グローバル ストリームを指定します。|  
|[wclog](../Topic/wclog.md)|`wclog` グローバル ストリームを指定します。|  
|[wcout](../Topic/wcout.md)|`wcout` グローバル ストリームを指定します。|  
  
## 参照  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)