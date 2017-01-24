---
title: "入出力ストリーム | Microsoft Docs"
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
helpviewer_keywords: 
  - "I/O [C++], ストリーム"
  - "ストリーム入出力"
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
caps.latest.revision: 11
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# 入出力ストリーム
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`basic_iostream`はヘッダー ファイルの istream\>で \<定義される入出力両方とも文字ベースの I\/O ストリームを処理するオブジェクトのクラス テンプレートです。  
  
 `basic_iostream` の文字固有の特殊化を定義し、読み込み、コードを読みやすくするために役立つ 2 typedef があります: `iostream` \(ヘッダー ファイルの入出力ストリームと \<\>は違います\) `basic_iostream<char>`に基づく I\/O のストリームに; `wiostream` は `basic_iostream<wchar_t>`に基づく I\/O ストリームです。  
  
 詳細については、「[basic\_iostream クラス](../standard-library/basic-iostream-class.md)」、「[iostream](../Topic/iostream.md)」、および「[wiostream](../Topic/wiostream.md)」を参照してください。  
  
 `basic_iostream` からの派生は、ファイルに対する文字データをストリームに使用されるクラス テンプレート `basic_fstream`です。  
  
 また `basic_fstream`の文字固有の特殊な形式を指定する typedef があります。  これらは、`fstream``char`に基づく、`wfstream`ですファイル I\/O ストリームの、`wchar_t`に基づくファイル I\/O ストリーム。  詳細については、「[basic\_fstream クラス](../standard-library/basic-fstream-class.md)」、「[fstream](../Topic/fstream.md)」、および「[wfstream](../Topic/wfstream.md)」を参照してください。  これらの typedef を使用してヘッダー ファイルの fstream\>のコンテナー \<が必要です。  
  
> [!NOTE]
>  したがって、ファイル I\/O を実行するために `basic_fstream` オブジェクトを使用する場合は、基になるバッファーが読み取りおよび書き込み用の個別に指定位置を含むが、現在の入力と現在の出力の位置は、と一緒に結び付けられ、あるデータが移動出力位置読み取ります。  
  
 クラス テンプレート `basic_stringstream` と共通の特殊化、`stringstream`は I\/O ストリーム オブジェクトと同じように、頻繁に使用される文字データを挿入、取得します。  詳細については、「[basic\_stringstream クラス](../standard-library/basic-stringstream-class.md)」を参照してください。  
  
## 参照  
 [stringstream](../Topic/stringstream.md)   
 [basic\_stringstream クラス](../standard-library/basic-stringstream-class.md)   
 [\<sstream\>](../standard-library/sstream.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [C\+\+ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)