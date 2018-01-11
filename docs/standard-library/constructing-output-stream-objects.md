---
title: "出力ストリーム オブジェクトのコンストラクト | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: output stream objects
ms.assetid: 93c8eab6-610c-4f48-b76d-1d960cac7641
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 04cbb5ae7433dc31e99136c11c4022e60ad4808e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="constructing-output-stream-objects"></a>出力ストリーム オブジェクトのコンストラクト
定義済みの `cout`、`cerr`、または `clog` オブジェクトのみを使う場合は、出力ストリームをコンストラクトする必要はありません。 次の場合はコンストラクターを使う必要があります。  
  
- [出力ファイル ストリーム コンストラクター](#vclrfoutputfilestreamconstructorsanchor1)  
  
- [出力文字列ストリーム コンストラクター](#vclrfoutputstringstreamconstructorsanchor2)  
  
##  <a name="vclrfoutputfilestreamconstructorsanchor1"></a> 出力ファイル ストリーム コンストラクター  
 2 つの方法のいずれかで、出力ファイル ストリームをコンストラクトできます。  
  
-   既定のコンストラクターを使った後、`open` メンバー関数を呼び出します。  
  
 ```  
    ofstream myFile; // Static or on the stack  
    myFile.open("filename");

 
    ofstream* pmyFile = new ofstream; // On the heap  
    pmyFile->open("filename");
```  
  
-   コンストラクターの呼び出しで、ファイル名とモード フラグを指定します。  
  
 ```  
    ofstream myFile("filename", ios_base::out);
```  
  
##  <a name="vclrfoutputstringstreamconstructorsanchor2"></a> 出力文字列ストリーム コンストラクター  
 出力文字列ストリームをコンストラクトするには、次のように `ostringstream` を使うことができます。  
  
```  
    using namespace std;  
string sp;  
ostringstream myString;  
myString <<"this is a test" <<ends;  
sp = myString.str();
// Obtain string  
cout <<sp <endl;   
```  
  
 `ends` "マニピュレーター" は、必要な終端 null 文字を文字列に追加します。  
  
## <a name="see-also"></a>参照  
 [出力ストリーム](../standard-library/output-streams.md)

