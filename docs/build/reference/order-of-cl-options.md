---
title: CL オプションの指定順序 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- cl
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, setting options
ms.assetid: 300908ce-ae00-4b45-964b-e4e69ff6777b
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef67792b01d4d4dab535bfb180cd70beb2316b6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="order-of-cl-options"></a>CL オプションの指定順序
オプションはことができます、/link オプション、最後に発生する必要がありますを除く、CL のコマンド ラインで任意の場所が表示されます。 コンパイラがで指定されたオプションで始まる、[環境変数 CL](../../build/reference/cl-environment-variables.md)し、コマンドラインを左から右に読むと — 検出される順序でコマンド ファイルを処理します。 各オプションは、コマンドラインですべてのファイルに適用されます。 CL では、競合するオプションが発生すると、右端のオプションを使用します。  
  
## <a name="see-also"></a>参照  
 [コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)