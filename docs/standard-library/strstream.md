---
title: '&lt;strstream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- <strstream>
dev_langs:
- C++
helpviewer_keywords:
- strstream header
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3176dafa04544b71f1a61b32af8523e8a0ab270e
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltstrstreamgt"></a>&lt;strstream&gt;
`char` オブジェクトに割り当てられた配列に格納されているシーケンスの iostreams 操作をサポートする複数のクラスを定義します。 このようなシーケンスは、C 文字列と簡単に相互変換できます。  
  
## <a name="syntax"></a>構文  
  
```  
#include <strstream>  
  
```  
  
## <a name="remarks"></a>コメント  
 型 `strstream` のオブジェクトは C 文字列の `char` * を使用します。 [\<sstream](../standard-library/sstream.md) は、型 [basic_string](../standard-library/basic-string-class.md) のオブジェクトを操作するために使用します。  
  
> [!NOTE]
>  `<strstream>` のクラスの使用は推奨されていません。 代わりに、`<sstream>` のクラスの使用を検討してください。  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[strstreambuf クラス](../standard-library/strstreambuf-class.md)|このクラスは `char` 配列オブジェクトに格納されている要素のシーケンス間で要素の送信を制御するストリーム バッファーを表します。|  
|[istrstream クラス](../standard-library/istrstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーからの、要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。|  
|[ostrstream クラス](../standard-library/ostrstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーへの、要素とエンコードされたオブジェクトの挿入を制御するオブジェクトを表します。|  
|[strstream クラス](../standard-library/strstream-class.md)|このクラスは、クラス [strstreambuf](../standard-library/strstreambuf-class.md) のストリーム バッファーを使用して要素とエンコードされたオブジェクトの挿入と抽出を制御するオブジェクトを表します。|  
  
## <a name="see-also"></a>参照  
 [\<strstream>](../standard-library/strstream.md)   
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)



