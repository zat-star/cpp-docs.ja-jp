---
title: "構造体 RUNTIME_FUNCTION |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 84386527-d3aa-41c5-871d-78e3e1913704
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 476ce4ad532f1e02b8863e2276fe0300c5895270
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="struct-runtimefunction"></a>構造体 RUNTIME_FUNCTION
テーブル ベースの例外処理では、スタック領域を割り当てるか、または別の関数 (たとえば、非リーフ関数) を呼び出すすべての関数のテーブルのエントリが必要です。 関数のテーブルのエントリではの形式があります。  
  
|||  
|-|-|  
|ULONG|関数の開始アドレス|  
|ULONG|関数の終了アドレス|  
|ULONG|アンワインド情報のアドレス|  
  
 RUNTIME_FUNCTION 構造体には、メモリ内の配置 DWORD をする必要があります。 すべてのアドレスはイメージからの相対、つまり、関数のテーブルのエントリを格納する、イメージの開始アドレスからの 32 ビット オフセットします。 これらのエントリは並べ替えられ、pe 32 + イメージの .pdata セクションに配置します。 関数 [JIT コンパイラ] の動的に生成された場合、ランタイムをこれらの関数をサポートする必要がありますまたはを使用 RtlInstallFunctionTableCallback RtlAddFunctionTable オペレーティング システムにこの情報を提供します。 信頼性の低い例外が処理され、プロセスのデバッグを行うためにエラーが発生します。  
  
## <a name="see-also"></a>関連項目  
 [例外処理とデバッガー サポートのためのアンワインド データ](../build/unwind-data-for-exception-handling-debugger-support.md)