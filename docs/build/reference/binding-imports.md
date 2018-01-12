---
title: "インポートのバインド |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- /DELAY:NOBIND linker option
- DELAY:NOBIND linker option
ms.assetid: bb766038-deb1-41b1-bcbc-29a30e8c1e2a
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4f462eeea9f2bca566745d425b84bd1506f52fc8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="binding-imports"></a>インポートのバインド
既定のリンカー動作では、遅延読み込みされた DLL のバインド可能なインポート アドレス テーブルを作成します。 ヘルパー関数が呼び出す代わりに、バインドされた情報を使用しようとして、DLL がバインドされている場合**GetProcAddress**参照されているインポートごとにします。 タイムスタンプまたは優先アドレスが一致しない場合、読み込まれた DLL のヘルパー関数とバインドされたインポート アドレス テーブルが古すぎますが存在しないかのように続行されます。  
  
 DLL の遅延読み込みしたインポートをバインドしない場合を指定する[/delay](../../build/reference/delay-delay-load-import-settings.md): リンカーのコマンドラインでは防止バインドのインポート アドレス テーブル、イメージ ファイルに領域を生成し、使用できます。  
  
## <a name="see-also"></a>参照  
 [リンカーによる DLL の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)