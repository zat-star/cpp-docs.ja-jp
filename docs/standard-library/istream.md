---
title: '&lt;istream&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- istream/std::<istream>
- <istream>
- std::<istream>
dev_langs:
- C++
helpviewer_keywords:
- istream header
ms.assetid: efcf24e4-05d1-4719-ab0b-9e7ebe845d89
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 83ad1cd6a07e4b8b6ce71e6803170ce3cc1c0342
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/23/2018
---
# <a name="ltistreamgt"></a>&lt;istream&gt;
iostream の抽出を仲介するテンプレート クラス basic_istream と、挿入と抽出の両方を仲介するテンプレート クラス basic_iostream を定義します。 ヘッダーは、関連するマニピュレーターも定義します。 このヘッダー ファイルは通常、別の iostream ヘッダーに含まれているため、ほとんどの場合、直接含める必要はありません。  
  
## <a name="syntax"></a>構文  
  
```  
#include <istream>  
  
```  
  
### <a name="typedefs"></a>Typedefs  
  
|||  
|-|-|  
|[iostream](../standard-library/istream-typedefs.md#iostream)|`char` に特殊化された型 `basic_iostream`。|  
|[istream](../standard-library/istream-typedefs.md#istream)|`char` に特殊化された型 `basic_istream`。|  
|[wiostream](../standard-library/istream-typedefs.md#wiostream)|**wchar** に特殊化された型 `basic_iostream`。|  
|[wistream](../standard-library/istream-typedefs.md#wistream)|**wchar** に特殊化された型 `basic_istream`。|  
  
### <a name="manipulators"></a>マニピュレーター  
  
|||  
|-|-|  
|[ws](../standard-library/istream-functions.md#ws)|ストリーム内の空白をスキップします。|  
|[swap](../standard-library/istream-functions.md#istream_swap)|2 つのストリーム オブジェクトを交換します。|  
  
### <a name="operators"></a>演算子  
  
|||  
|-|-|  
|[operator>>](../standard-library/istream-operators.md#op_gt_gt)|ストリームから文字と文字列を抽出します。|  
  
### <a name="classes"></a>クラス  
  
|||  
|-|-|  
|[basic_iostream](../standard-library/basic-iostream-class.md)|入力と出力の両方を行うことができるストリーム クラス。|  
|[basic_istream](../standard-library/basic-istream-class.md)|このテンプレート クラスは、**Elem** 型の要素を含むストリーム バッファーからの要素とエンコードされたオブジェクトの抽出を制御するオブジェクトを表します。Elem 型は [char_type](../standard-library/basic-ios-class.md#char_type) とも呼ばれ、その特性は、[traits_type](../standard-library/basic-ios-class.md#traits_type) とも呼ばれるクラス **Tr** によって決定されます。|  
  
## <a name="see-also"></a>参照  
 [C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream プログラミング](../standard-library/iostream-programming.md)   
 [iostreams の規則](../standard-library/iostreams-conventions.md)



