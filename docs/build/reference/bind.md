---
title: "-BIND |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /bind
dev_langs:
- C++
helpviewer_keywords:
- -BIND editbin option
- entry points, addresses
- BIND editbin option
- entry points
- /BIND editbin option
- import address table
ms.assetid: 3772b330-1868-4c90-857d-c31faa867982
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50f2f1856b4718af8e87728a79511d9b18654efb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="bind"></a>/BIND
```  
/BIND[:PATH=path]  
```  
  
## <a name="remarks"></a>コメント  
 このオプションは、実行可能ファイルまたは DLL のインポート アドレス テーブルにエントリ ポイントのアドレスを設定します。 このオプションを使用すると、プログラムの読み込み時間を短縮できます。  
  
 プログラムの実行可能ファイルとで Dll を指定、*ファイル*EDITBIN コマンドラインの引数。 省略可能な*パス*/BIND への引数が指定されたファイルによって使用されている Dll の場所を指定します。 複数のディレクトリをセミコロンで区切ります (**;**)。 場合*パス*が指定されていない、EDITBIN が PATH 環境変数で指定されたディレクトリを検索します。 場合*パス*を指定すると、EDITBIN パス変数は無視されます。  
  
 既定は、プログラムのローダーは、プログラムを読み込むときに、エントリ ポイントのアドレスを設定します。 このプロセスにかかる時間の量は、Dll の数と、プログラムで参照されているエントリ ポイントの数によって異なります。 /Bind、プログラムが変更された場合、および実行可能ファイルのベース アドレスし、その Dll は既に読み込まれている Dll と競合しない場合は、オペレーティング システムがこれらのアドレスを設定する必要はありません。 ここで、ファイルが正しく基づいての状況では、オペレーティング システムは、プログラムの Dll を再配置し、プログラムの読み込み時に追加されるエントリ ポイントのアドレスを再計算されます。  
  
## <a name="see-also"></a>参照  
 [EDITBIN オプション](../../build/reference/editbin-options.md)