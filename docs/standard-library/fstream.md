---
title: '&lt;fstream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <fstream>
dev_langs: C++
helpviewer_keywords: fstream header
ms.assetid: 660de351-0489-41df-b239-40e0cdcab46b
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dc68979d4dc4b79a2b1e6e987f51bebc6d15aa3b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ltfstreamgt"></a>&lt;fstream&gt;
外部ファイルに格納されているシーケンスの iostream の操作をサポートする複数のクラスを定義します。  
  
## <a name="syntax"></a>構文  
  
```  
#include <fstream>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[filebuf](../standard-library/fstream-typedefs.md#filebuf)|`char` テンプレート パラメーターに特殊化された型 `basic_filebuf`。|  
|[fstream](../standard-library/fstream-typedefs.md#fstream)|`char` テンプレート パラメーターに特殊化された型 `basic_fstream`。|  
|[ifstream](../standard-library/fstream-typedefs.md#ifstream)|`char` テンプレート パラメーターに特殊化された型 `basic_ifstream`。|  
|[ofstream](../standard-library/fstream-typedefs.md#ofstream)|`char` テンプレート パラメーターに特殊化された型 `basic_ofstream`。|  
|[wfstream](../standard-library/fstream-typedefs.md#wfstream)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_fstream`。|  
|[wifstream](../standard-library/fstream-typedefs.md#wifstream)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_ifstream`。|  
|[wofstream](../standard-library/fstream-typedefs.md#wofstream)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_ofstream`。|  
|[wfilebuf](../standard-library/fstream-typedefs.md#wfilebuf)|`wchar_t` テンプレート パラメーターに特殊化された型 `basic_filebuf`。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[basic_filebuf](../standard-library/basic-filebuf-class.md)|このテンプレート クラスは、**Elem** 型の要素と外部ファイルに格納されている要素のシーケンスとの間でやり取りされる転送を制御するストリーム バッファーを記述します。Elem 型の特性は **Tr** クラスによって決められます。|  
|[basic_fstream](../standard-library/basic-fstream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含む [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> クラスのストリーム バッファーを使用して要素とエンコードされたオブジェクトを挿入または抽出する際に、その処理を制御するオブジェクトを記述します。Elem 型の特性は **Tr** クラスによって決められます。|  
|[basic_ifstream](../standard-library/basic-ifstream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含む [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> クラスのストリーム バッファーから要素とエンコードされたオブジェクトを抽出する処理を制御するオブジェクトを記述します。Elem 型の特性は **Tr** クラスによって決められます。|  
|[basic_ofstream](../standard-library/basic-ofstream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含む [basic_filebuf](../standard-library/basic-filebuf-class.md)\<**Elem**, **Tr**> クラスのストリーム バッファーに要素とエンコードされたオブジェクトを挿入する処理を制御するオブジェクトを記述します。Elem 型の特性は **Tr** クラスによって決められます。|  
  
## <a name="see-also"></a>関連項目  
 [ヘッダー ファイル リファレンス](../standard-library/cpp-standard-library-header-files.md)   
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)



