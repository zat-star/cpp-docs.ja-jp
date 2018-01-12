---
title: "Intel &#39; s MMX 命令セット |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: MMX instruction set
ms.assetid: 705deb2d-c3fd-4696-9e22-8bcf25866daf
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b8aa4dc38a8ed04c2df04eaa944d43769ae996f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="intel39s-mmx-instruction-set"></a>Intel &#39; s MMX 命令セット
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 Visual C コンパイラでは、Intel の MMX (マルチ メディア拡張機能) の命令が、インライン アセンブラーのセットを使用することができます。 MMX 命令もサポートしていますデバッガー逆アセンブルします。 関数は、MMX 命令が含まれていますが、マルチ メディアの状態を空に EMMS 命令が含まれていない場合、コンパイラは警告メッセージを生成します。 詳細については、Intel の Web サイトを参照してください。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [__asm ブロックでのアセンブリ言語の使用](../../assembler/inline/using-assembly-language-in-asm-blocks.md)