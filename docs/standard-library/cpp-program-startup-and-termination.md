---
title: "C++ プログラムの起動と終了 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- C++ Standard Library, program startup and termination
- terminating execution
- Function Main procedures
- control text streams
- startup code, and C++ program termination
- main function, program startup
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f69f0c3176d2fbe19e11ce08c071691a72d858d
ms.openlocfilehash: 53e31f3f3a175013a248401f4231bb87cf444681
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="c-program-startup-and-termination"></a>C++ プログラムの起動と終了
C++ プログラムは、プログラムの起動時と終了時に C プログラムと同じ操作に加えて、ここで説明する追加の操作を実行します。  
  
 対象環境が `main` 関数を呼び出す前、および静的存続期間があるすべてのオブジェクトで指定されている定数初期値が格納された後、プログラムはこのような静的オブジェクトに対する残りのコンストラクターを実行します。 翻訳単位の間で実行順序は指定されていませんが、それでも、これらの静的コンストラクターによる使用のために一部の [iostreams](../standard-library/iostreams-conventions.md) オブジェクトが正しく初期化されるものと想定できます。 このようなコントロール テキスト ストリームは次のとおりです。  
  
-   [cin](../standard-library/iostream.md#cin) — 標準入力の場合。  
  
-   [cout](../standard-library/iostream.md#cout) — 標準出力の場合。  
  
-   [cerr](../standard-library/iostream.md#cerr) — バッファーされない標準エラー出力の場合。  
  
-   [clog](../standard-library/iostream.md#clog) — バッファーされる標準エラー出力の場合。  
  
 また、プログラムの終了時に、静的オブジェクトに対して呼び出されるデストラクター内で、これらのオブジェクトを使用できます。  
  
 C と同様に、`main` からの戻りまたは `exit` の呼び出しでは、`atexit` に登録されているすべての関数が、登録と逆の順序で呼び出されます。 このような登録されている関数からスローされる例外は、`terminate` を呼び出します。  
  
## <a name="see-also"></a>関連項目  
 [C++ 標準ライブラリの概要](../standard-library/cpp-standard-library-overview.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)



