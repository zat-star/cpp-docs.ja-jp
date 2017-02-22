---
title: "iostreams の規則 | Microsoft Docs"
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
  - "iostream ヘッダー"
  - "標準 C++ ライブラリ, iostreams"
ms.assetid: 9fe5ded0-37a1-48d1-9671-c81ffc4760ad
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# iostreams の規則
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

iostream ヘッダーはテキストとエンコードされたフォーム間の変換、外部ファイルへの入出力サポートします:  
  
|||  
|-|-|  
|[\<fstream\>](../standard-library/fstream.md)|[\< iomanip \>](../Topic/%3Ciomanip%3E.md)|  
|[\<ios\>](../standard-library/ios.md)|[\<iosfwd\>](../standard-library/iosfwd.md)|  
|[\<iostream\>](../standard-library/iostream.md)|[\< istream \>](../standard-library/istream.md)|  
|[\<ostream\>](../standard-library/ostream.md)|[\<sstream\>](../standard-library/sstream.md)|  
|[\< streambuf \>](../standard-library/streambuf.md)|[\<strstream\>](../standard-library/strstream.md)|  
  
 入出力ストリームの最も簡単な使用方法は、ヘッダー [\<iostream\>](../standard-library/iostream.md)を含むことだけです。  [cin](../Topic/cin.md) または [wcin](../Topic/wcin.md) から、標準入力を読み取る値を取得できます。  その規則は、クラス [basic\_istream クラス](../Topic/basic_istream%20Class.md)の説明で説明します。  また [標準出力ストリーム](../Topic/cout.md) または [wcout](../Topic/wcout.md) に値挿入標準出力を作成できます。  その規則は、クラス [basic\_ostream クラス](../Topic/basic_ostream%20Class.md)の説明で説明します。  両方の抽出器と insertors に共通の書式設定は [basic\_ios クラス](../Topic/basic_ios%20Class.md)クラスによって管理されます。  オブジェクトを取得し、挿入を装ったこの書式情報を処理することで、複数のマニピュレーターの領域です。  
  
 [\<fstream\>](../standard-library/fstream.md)で宣言されたクラスを使用して、名前で開くファイルの同じストリーム入出力操作を実行できます。  クラス [basic\_string クラス](../standard-library/basic-string-class.md)iostream とオブジェクトを変換するには、宣言されている [\<sstream\>](../standard-library/sstream.md)のクラスを使用します。  C スタイルの文字列とを同じにするには、宣言されている [\<strstream\>](../standard-library/strstream.md)のクラスを使用します。  
  
 残りのヘッダーは、iostream クラスの最先端のユーザーだけに直接対象のサポート サービスを通常提供します。  
  
## 参照  
 [STL の概要](../standard-library/cpp-standard-library-overview.md)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)   
 [C\+\+ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)