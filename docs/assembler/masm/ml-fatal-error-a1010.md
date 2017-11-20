---
title: "ML の致命的なエラー A1010 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: A1010
dev_langs: C++
helpviewer_keywords: A1010
ms.assetid: 9e0b5241-67f4-4740-8701-3b2d2d1ad9e4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 22b9886587b07958650a0624386867d4bc69cfd9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="ml-fatal-error-a1010"></a>ML の致命的なエラー A1010
**一致しないブロックの入れ子。**  
  
 ブロックの先頭には、対応する end がなかったか、ブロックの終了が開始に対応するありませんでした。 次のいずれかが関係している可能性があります。  
  
-   などの高度なディレクティブ[です。IF](../../assembler/masm/dot-if.md)、[です。繰り返し](../../assembler/masm/dot-repeat.md)、または[です。中に](../../assembler/masm/dot-while.md)です。  
  
-   などの条件付きアセンブリ ディレクティブ[IF](../../assembler/masm/if-masm.md)、[繰り返します](../../assembler/masm/repeat.md)、または**中**です。  
  
-   構造体または共用体の定義。  
  
-   プロシージャの定義。  
  
-   セグメントの定義。  
  
-   A [POPCONTEXT](../../assembler/masm/popcontext.md)ディレクティブです。  
  
-   条件付きのアセンブリのように、ディレクティブ、 [ELSE](../../assembler/masm/else-masm.md)、 [ELSEIF](../../assembler/masm/elseif-masm.md)、または**ENDIF**が対応する[IF](../../assembler/masm/if-masm.md)です。  
  
## <a name="see-also"></a>関連項目  
 [ML エラー メッセージ](../../assembler/masm/ml-error-messages.md)