---
title: "ファイルとストリーム | Microsoft Docs"
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
- files [C++]
- streams
ms.assetid: f61e712b-eac9-4c28-bb18-97c3786ef387
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 81caecba2f34f761706acba58afbfc55058e713b
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="files-and-streams"></a>ファイルとストリーム
プログラムは、ファイルを読み書きすることによって対象の環境と通信します。 ファイルには次のものがあります。  
  
-   繰り返し読み書きできるデータ セット。  
  
-   プログラム (パイプラインなど) によって生成されるバイト ストリーム。  
  
-   周辺デバイスとの間で送受信されるストリーム バイト。  
  
 最後の 2 つの項目は対話型ファイルです。 一般的に、ファイルはプログラムと相互に作用するための主要な手段です。 ライブラリ関数を呼び出すことによって、ほぼ同じ方法でこれらすべての種類のファイルを操作できます。 これらの関数の大半を宣言するには、標準ヘッダー STDIO.H をインクルードします。  
  
 ファイルで多くの操作を実行する前に、ファイルを開く必要があります。 ファイルを開くことによって、各種ファイル間の多くの違いが無視される標準 C ライブラリ内のデータ構造であるストリームと、ファイルが関連付けられます。 ライブラリでは、各ストリームの状態が FILE 型のオブジェクトで維持されます。  
  
 対象の環境では、プログラムの起動前に 3 つのファイルを開きます。 2 つの引数を使用してライブラリ関数 [fopen, _wfopen](../c-runtime-library/reference/fopen-wfopen.md) を呼び出すことによってファイルを開くことができます。 (`fopen` 関数は使用されていません。代わりに [fopen_s, _wfopen_s](../c-runtime-library/reference/fopen-s-wfopen-s.md) を使用してください)。1 つ目の引数は、ファイル名です。 2 つ目の引数は、次を指定する C 文字列です。  
  
-   ファイルからデータを読み込む、ファイルにデータを書き込む、または両方を行うかどうか。  
  
-   ファイルの新しい内容を生成する (またはファイルが存在していなかった場合はファイルを作成する)、または既存の内容をそのままにするかどうか。  
  
-   ファイルへの書き込みによって既存の内容が変更される、またはファイルの終端にバイトが追加されるのみかどうか。  
  
-   テキスト ストリームまたはバイナリ ストリームを操作するかどうか。  
  
 ファイルが正常に開いたら、ストリームがバイト指向 (バイト ストリーム) かワイド指向 (ワイド ストリーム) かを決めることができます。 ストリームは、初期状態ではバインドされていません。 ストリームで操作する特定の関数を呼び出すとバイト指向になり、特定の他の関数を呼び出すとワイド指向になります。 いったん確立すると、[fclose](../c-runtime-library/reference/fclose-fcloseall.md) または [freopen](../c-runtime-library/reference/freopen-wfreopen.md) への呼び出しによってファイルが閉じるまで、ストリームの指向は保持されます。  
  
 © 1989-2001 by P.J. Plauger and Jim Brodie. All rights reserved.  
  
## <a name="see-also"></a>関連項目  
 [テキスト ストリームとバイナリ ストリーム](../c-runtime-library/text-and-binary-streams.md)   
 [バイト ストリームとワイド ストリーム](../c-runtime-library/byte-and-wide-streams.md)   
 [ストリームの制御](../c-runtime-library/controlling-streams.md)   
 [ストリームの状態](../c-runtime-library/stream-states.md)
