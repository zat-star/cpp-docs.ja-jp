---
title: "関数の概要 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 16612a32a0e5cb2294f4b74f46c14c206c1cbcbc
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="overview-of-functions"></a>関数の概要
関数には定義が必要で、宣言を含む必要がありますが、関数が呼び出される前に宣言が存在している場合は定義を宣言として使用できます。 関数定義は、関数本体、つまり関数が呼び出されたとき実行するコードを含みます。  
  
 関数宣言は、プログラムの別の場所で定義された関数の名前、戻り値の型、および属性を設定します。 関数宣言は関数への呼び出しを付ける必要があります。 このため、ランタイム関数の宣言を含むヘッダー ファイルは、ランタイム関数への呼び出しよりも前に、コードにインクルードされます。 宣言にパラメーターの型と数に関する情報が含まれる場合、宣言はプロトタイプになります。 詳細については、「[関数プロトタイプ](../c-language/function-prototypes.md)」をご覧ください。  
  
 コンパイラは、プロトタイプを使用して、後続の関数呼び出しの引数の型を関数のパラメーターと比較し、必要な場合はいつでも引数の型をパラメーターの型に変換します。  
  
 関数呼び出しは、呼び出し元の関数から呼び出された関数に実行制御を渡します。 引数 (存在する場合) は、呼び出された関数に値渡しされます。 呼び出された関数内で `return` ステートメントを実行すると、呼び出し元の関数に制御を戻し、場合によっては値を返します。  
  
## <a name="see-also"></a>関連項目  
 [関数](../c-language/functions-c.md)
