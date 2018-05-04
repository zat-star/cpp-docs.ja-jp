---
title: メイクファイルのプリプロセス演算子 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], makefile preprocessing
- EXIST operator
- preprocessing NMAKE makefile operators
- NMAKE program, operators
- DEFINED operator
- makefiles, preprocessing operators
ms.assetid: a46e4d39-afdb-43c1-ac3b-025d33e6ebdb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9a99bf6388a4aa15b2126aca8e09210b7202d46
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="makefile-preprocessing-operators"></a>メイクファイルのプリプロセッサ演算子
メイクファイルのプリプロセス式では、定数値、コマンドからの終了コード、文字列、マクロ、およびファイル システムのパスに作用する演算子を使用できます。 式を評価するために、プリプロセッサは最初にマクロを展開し、次にコマンドを実行し、次に演算を実行します。 演算は、かっこ内の明示的なグループ化の順序に従って評価され、その後、演算子の優先順位の順に評価されます。 結果は定数値です。  
  
 `DEFINED` 演算子は、マクロ名に作用する論理演算子です。 式`DEFINED(` *macroname* `)`が true 場合*macroname*が定義されている場合は、割り当てられた値があるない場合でもです。 `DEFINED` と `!IF` または `!ELSE IF` を組み合わせると、`!IFDEF` または `!ELSE IFDEF` と等しくなります。 ただし、これらのディレクティブとは異なり、`DEFINED` は複合式で使用できます。  
  
 `EXIST` 演算子は、ファイル システムのパスに作用する論理演算子です。 `EXIST(`*パス*`)`が true の場合*パス*が存在します。 `EXIST` の結果は、二項式で使用できます。 場合*パス*スペースを含む二重引用符で囲みます。  
  
 2 つの文字列を比較するには、等値 (`==`) 演算子または非等値 (`!=`) 演算子を使用します。 文字列は二重引用符で囲みます。  
  
 整数定数では、算術否定 (`-`)、1 の補数 (`~`)、および論理否定 (`!`) の単項演算子を使用できます。  
  
 式では、次の演算子を使用できます。 同じ優先順位の演算子はグループ化し、グループは優先順位の高い順に示しています。 単項演算子は、右側のオペランドと結合します。 同じ優先順位の二項演算子は、左から右へオペランドを結合します。  
  
|演算子|説明|  
|--------------|-----------------|  
|`DEFINED(` *マクロ名* `)`|現在の定義の状態の論理値を生成*macroname*です。|  
|`EXIST(` *パス* `)`|ファイルが存在する論理値を生成*パス*です。|  
|||  
|`!`|単項論理 NOT。|  
|`~`|単項 1 の補数。|  
|`-`|単項否定。|  
|||  
|`*`|乗算。|  
|`/`|除算。|  
|`%`|剰余 (余り)。|  
|||  
|`+`|加算。|  
|`-`|減算。|  
|||  
|`<<`|ビットごとのシフト (左)。|  
|`>>`|ビットごとのシフト (右)。|  
|||  
|`<=`|以下。|  
|`>=`|以上。|  
|`<`|より小さい。|  
|`>`|より大きい。|  
|||  
|`==`|等値。|  
|`!=`|非等値。|  
|||  
|`&`|ビットごとの AND。|  
|`^`|ビットごとの XOR。|  
|`&#124;`|ビットごとの OR。|  
|||  
|`&&`|論理 AND。|  
|||  
|`&#124;&#124;`|論理 OR。|  
  
> [!NOTE]
>  ビットごとの XOR 演算子 (`^`) はエスケープ文字と同じであり、式で使用する場合は (`^^` として) エスケープする必要があります。  
  
## <a name="see-also"></a>関連項目  
 [メイクファイル プリプロセスの式](../build/expressions-in-makefile-preprocessing.md)