---
title: "入出力ストリーム | Microsoft Docs"
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
- I/O [C++], stream
- stream I/O
ms.assetid: 21a97566-91a7-42d6-b2f8-a4c16bc926f1
caps.latest.revision: 11
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4fdfb4ece713c071a4b740127428c16303c0ab10
ms.contentlocale: ja-jp
ms.lasthandoff: 02/24/2017

---
# <a name="inputoutput-streams"></a>入出力ストリーム
ヘッダー ファイル \<istream> で定義される `basic_iostream` は、入力および出力の両方の文字ベースの I/O ストリームを処理するオブジェクトのクラス テンプレートです。  
  
 `basic_iostream` の文字に固有の特殊化を定義し、コードを読みやすくするのに役立つ&2; つの typedef があります。`iostream` (ヘッダー ファイル \<iostream> と混同しないでください) は、`basic_iostream<char>` に基づいている I/O ストリームです。`wiostream` は、`basic_iostream<wchar_t>` に基づいている I/O ストリームです。  
  
 詳細については、「[basic_iostream クラス](../standard-library/basic-iostream-class.md)」、「[iostream](../standard-library/basic-iostream-class.md)」、および「[wiostream](../standard-library/basic-iostream-class.md)」を参照してください。  
  
 `basic_iostream` からはクラス テンプレート `basic_fstream` が派生され、これ、ファイルとの間で文字データをストリーミングするのに使用されます。  
  
 `basic_fstream` の文字に固有の特殊化を提供する typedef もあります。 `char` に基づくファイルの I/O ストリームである `fstream`、および `wchar_t` に基づくファイルの I/O ストリームである `wfstream` があります。 詳細については、「[basic_fstream クラス](../standard-library/basic-fstream-class.md)」、「[fstream](../standard-library/basic-fstream-class.md)」、および「[wfstream](../standard-library/basic-fstream-class.md)」を参照してください。 これらの typedef を使用するには、ヘッダー ファイル \<fstream> を含める必要があります。  
  
> [!NOTE]
>  `basic_fstream` オブジェクトを使用してファイル I/O を実行する場合、基になるバッファーに、個別に指定された読み取りと書き込みの位置が含まれていても、現在の入力位置と現在の出力位置が一緒に関連付けられるため、一部のデータを読み取ると、出力位置が移動します。  
  
 クラス テンプレート `basic_stringstream` とその一般的な特殊化 `stringstream` は、通常、I/O ストリーム オブジェクトで使用して、文字データを挿入および抽出します。 詳細については、「[basic_stringstream クラス](../standard-library/basic-stringstream-class.md)」を参照してください。  
  
## <a name="see-also"></a>関連項目  
 [stringstream](../standard-library/basic-stringstream-class.md)   
 [basic_stringstream クラス](../standard-library/basic-stringstream-class.md)   
 [\<sstream>](../standard-library/sstream.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [C++ 標準ライブラリ](../standard-library/cpp-standard-library-reference.md)




