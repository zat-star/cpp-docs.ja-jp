---
title: "メイクファイル プリプロセスの式 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- preprocessing makefiles
- expressions [C++], makefile preprocessing
- makefiles, preprocessing
ms.assetid: 37f0f413-97e0-452c-a83f-3c9002c44c92
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7bea4f0c4fea2c2d04681674734bc989424c7951
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="expressions-in-makefile-preprocessing"></a>メイクファイル プリプロセスの式
**!IF**または**!ELSE IF** `constantexpression` 10 進数または C 言語表記で整数の定数、文字列定数、またはコマンドで構成されます。 グループ式にかっこを使用します。 式は、C スタイル付き長整数算術; を使用します。数値、32 ビット 2 の補数形式、範囲 - 2147483648 ~ 2147483647 です。  
  
 式は、定数値、コマンド、文字列、マクロ、およびファイル システムのパスからの終了コードに作用する演算子を使用できます。  
  
## <a name="what-do-you-want-to-know-more-about"></a>さらに詳しくは次のトピックをクリックしてください  
 [メイクファイルのプリプロセッサ演算子](../build/makefile-preprocessing-operators.md)  
  
 [前処理でプログラムを実行します。](../build/executing-a-program-in-preprocessing.md)  
  
## <a name="see-also"></a>参照  
 [メイクファイルのプリプロセス](../build/makefile-preprocessing.md)