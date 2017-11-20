---
title: "前処理でプログラムを実行する |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: a6b98d3c03d319c2da397f969f8adf1ec858f72c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="executing-a-program-in-preprocessing"></a>プリプロセスでのプログラムの実行
プリプロセス時にコマンドの終了コードを使用するには、角かっこ () 内の任意の引数を指定して、コマンドを指定します。 すべてのマクロは、コマンドを実行前に展開します。 (Nmake の) は、コマンドの仕様を前処理を制御する式の中で使用できるコマンドの終了コードに置き換えます。  
  
## <a name="see-also"></a>関連項目  
 [メイクファイル プリプロセスの式](../build/expressions-in-makefile-preprocessing.md)