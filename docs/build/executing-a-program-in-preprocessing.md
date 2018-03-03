---
title: "前処理でプログラムを実行する |Microsoft ドキュメント"
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
- program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ef000f6611c9cb3794da8e46e6b905e57d5ecf92
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="executing-a-program-in-preprocessing"></a>プリプロセスでのプログラムの実行
プリプロセス時にコマンドの終了コードを使用するには、角かっこ () 内の任意の引数を指定して、コマンドを指定します。 すべてのマクロは、コマンドを実行前に展開します。 (Nmake の) は、コマンドの仕様を前処理を制御する式の中で使用できるコマンドの終了コードに置き換えます。  
  
## <a name="see-also"></a>参照  
 [メイクファイル プリプロセスの式](../build/expressions-in-makefile-preprocessing.md)