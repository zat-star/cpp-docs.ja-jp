---
title: "一時オブジェクト |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- temporary objects
- objects [C++], temporary
ms.assetid: 4c8cec02-391e-4225-9bc6-06d150201412
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 2f1e30ce63374a3b8fddb52f7d2afa3f219287d4
ms.contentlocale: ja-jp
ms.lasthandoff: 09/25/2017

---
# <a name="temporary-objects"></a>一時オブジェクト
場合によっては、コンパイラが一時オブジェクトを作成する必要があります。 このような一時オブジェクトが作成される理由として、次のことがあります。  
  
-   初期化する対象の参照の基になる型とは異なる型の初期化子を使用して `const` 参照を初期化するため。  
  
-   ユーザー定義型を返す関数の戻り値を格納するため。 これらの一時要素は、プログラムがオブジェクトに戻り値をコピーしない場合にのみ作成されます。 例:  
  
    ```  
    UDT Func1();    //  Declare a function that returns a user-defined  
                    //   type.  
  
    ...  
  
    Func1();        //  Call Func1, but discard return value.  
                    //  A temporary object is created to store the return  
                    //   value.  
    ```  
  
     戻り値は別のオブジェクトにコピーされないため、一時オブジェクトが作成されます。 一時オブジェクトが作成されるより一般的なケースは、オーバーロードされた演算子関数を呼び出す必要がある式を評価するときです。 これらのオーバーロードされた演算子関数は、多くの場合、別のオブジェクトにコピーされないユーザー定義型を返します。  
  
     式 `ComplexResult = Complex1 + Complex2 + Complex3` を考えます。 `Complex1 + Complex2` 式が評価され、結果が一時オブジェクトに格納されます。 次に、式*一時*`+ Complex3`が評価され、結果にコピーし、 `ComplexResult` (代入演算子を想定してオーバー ロードされていない)。  
  
-   キャストの結果をユーザー定義型に格納するため。 特定の型のオブジェクトがユーザー定義型に明示的に変換されるとき、新しいオブジェクトは一時オブジェクトとして作成されます。  
  
 一時オブジェクトには、作成される時点と破棄される時点とで決まる有効期間があります。 複数の一時オブジェクトを作成する式では、作成時と逆の順序で破棄が行われます。 破棄が発生するポイントを次の表に示します。  
  
### <a name="destruction-points-for-temporary-objects"></a>一時オブジェクトの破棄ポイント  
  
|一時オブジェクトが作成された理由|破棄ポイント|  
|------------------------------|-----------------------|  
|式評価の結果|式の評価の結果として作成されたすべての一時要素は、式ステートメントの最後 (セミコロンの位置)、または、`for`、`if`、`while`、`do`、および `switch` ステートメントの制御式の最後に破棄されます。|  
|`const` 参照の初期化|初期化子が初期化されている参照と同じ型の左辺値でない場合、基になるオブジェクト型の一時オブジェクトが作成され、初期化式で初期化されます。 この一時オブジェクトは、バインド先の参照オブジェクトが破棄された直後に破棄されます。|  
  

