---
title: "リンカ ツール エラー LNK1181 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1181
dev_langs:
- C++
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8f5092d4f3ce7b4f96ca4dc5c1554483a7fc3a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1181"></a>リンカ ツール エラー LNK1181
入力ファイル 'filename' を開くことができません。  
  
 リンカーが見つかりませんでした`filename`が存在しないか、パスが見つかりませんでした。  
  
 LNK1181 含めるエラーの一般的な原因がいくつか:  
  
-   `filename`リンカーのコマンドラインは、ファイルに追加の依存関係が存在しないのでが参照されます。  
  
-   A **/LIBPATH**ステートメントを含むディレクトリを指定する`filename`がありません。  
  
 上記の問題を解決するのには、リンカーのコマンドラインで参照されているすべてのファイルが、システムに存在を確認します。  あることを確認、 **/LIBPATH**リンカーの依存ファイルを含むディレクトリごとにステートメントです。  
  
 LNK1181 の他の考えられる原因は、長いファイル名に埋め込まれたスペースが引用符で囲まれていないことです。  その場合は、リンカーだけ最初のスペースでは、最大のファイル名が認識され、ファイル拡張子を想定します obj.。このような状況を解決するには長いファイル名を囲む (パスとファイル名) 引用符で囲んで指定します。  
  
 詳細については、次を参照してください。[リンカー入力としての .lib ファイル](../../build/reference/dot-lib-files-as-linker-input.md)です。  
  
## <a name="see-also"></a>参照  
 [/LIBPATH (追加ライブラリのパス)](../../build/reference/libpath-additional-libpath.md)