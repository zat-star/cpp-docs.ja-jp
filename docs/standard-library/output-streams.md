---
title: "出力ストリーム | Microsoft Docs"
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
  - "出力ストリーム"
ms.assetid: b49410e3-5caa-4153-9d0d-c4266408dc83
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# 出力ストリーム
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

出力ストリーム オブジェクトは、バイトのターゲットです。  3 種類の最も重要な出力ストリーム クラスは、`ostream``ofstream`と `ostringstream`です。  
  
 `ostream` クラスは、派生クラス `basic_ostream`を通じて、定義済みのなストリーム オブジェクトをサポートする:  
  
-   `cout`の標準出力  
  
-   限られたバッファリングの`cerr`の標準エラー  
  
-   `cerr` に、フル バッファリングと同様`clog`  
  
 オブジェクトは `ostream`からあまり組み立てられません; 定義済みのオブジェクトは一般に使用されます。  場合によっては、プログラム起動後に定義済みのオブジェクトを再割り当てすることもできます。  バッファリングまたはいない操作用に構成できる `ostream` クラスは順次テキスト モードの出力に最も適しています。  基本クラス、`ios`のすべての機能は `ostream`に含まれています。  クラス `ostream`オブジェクトを作成する場合、コンストラクターへの `streambuf` オブジェクトを指定する必要があります。  
  
 `ofstream` クラスは、ディスク ファイルの出力をサポートします。  出力だけディスクが必要な場合は、クラス `ofstream`オブジェクトを構築します。  `ofstream` オブジェクトまたは `open` のメンバー関数を呼び出すと、そのオブジェクトの構築時 `ofstream` オブジェクトまたはテキスト モードがバイナリ データを受け入れるかどうかを指定できます。  さまざまな書式指定オプションとメンバー関数は `ofstream` にオブジェクトを適用し、基本クラス `ios` と `ostream` のすべての機能が含まれます。  
  
 コンストラクターにファイル名を指定した場合、そのファイルは自動的にオブジェクトを作成するときに表示されます。  それ以外の場合は、既定のコンストラクターを呼び出すと `open` メンバー関数を使用できます。  
  
 ランタイム `sprintf_s`関数と同様に、`ostringstream` クラスは、メモリ内の文字列に出力をサポートします。  I\/O のストリームの書式を使用してメモリ内に文字列を作成するには、クラス `ostringstream`オブジェクトを構築します。  
  
## このセクションの内容  
 [出力ストリーム オブジェクトのコンストラクト](../Topic/Constructing%20Output%20Stream%20Objects.md)  
  
 [挿入演算子と制御形式の使用](../standard-library/using-insertion-operators-and-controlling-format.md)  
  
 [出力ファイル ストリームのメンバー関数](../standard-library/output-file-stream-member-functions.md)  
  
 [バッファリングの効果](../standard-library/effects-of-buffering.md)  
  
 [バイナリ出力ファイル](../standard-library/binary-output-files.md)  
  
 [独自クラスのための \<\< 演算子のオーバーロード](../Topic/Overloading%20the%20%3C%3C%20Operator%20for%20Your%20Own%20Classes.md)  
  
 [引数を使用しない独自マニピュレーターの作成](../standard-library/writing-your-own-manipulators-without-arguments.md)  
  
## 参照  
 [\<ostream\> Members](http://msdn.microsoft.com/ja-jp/a5afd034-0e3c-41ee-bbd7-468d9188da1d)   
 [ofstream](../Topic/ofstream.md)   
 [ostringstream](../Topic/ostringstream.md)   
 [basic\_ostream Members](http://msdn.microsoft.com/ja-jp/82e5cc91-7c0c-4950-a8ce-ac779cfbbd93)   
 [iostream プログラミング](../Topic/iostream%20Programming.md)