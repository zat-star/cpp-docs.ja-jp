---
title: "C++ コマンドライン処理のカスタマイズ |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _setenvp
- _setargv
dev_langs:
- C++
helpviewer_keywords:
- command line [C++], processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line [C++], processing arguments
- suppressing environment processing
- _setenvp function
ms.assetid: aae01cbb-892b-48b8-8e1f-34f22421f263
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 396f2a314c185f39593c92745346f988d666980f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="customizing-c-command-line-processing"></a>C++ コマンド ライン処理のカスタマイズ
## <a name="microsoft-specific"></a>Microsoft 固有の仕様  
 プログラムがコマンド ラインの引数を受け取らない場合は、コマンド ライン処理を実行するライブラリ ルーチンの使用を制約することで、領域を節約できます。 このルーチンを呼び出す**_setargv**しで説明されているが[ワイルドカードの展開](../cpp/wildcard-expansion.md)です。 使用を抑制するには、定義を含むファイルで何も実行しないルーチン、**メイン**関数、および名前を付けます**_setargv**です。 呼び出し**_setargv**の定義によって満たされる**_setargv**ライブラリのバージョンは読み込まれません。  
  
 同様に、環境を使用してテーブルにアクセスしない場合、`envp`引数の代わりに使用する独自の空ルーチンを提供できます**_setenvp**、環境処理ルーチンです。 同様、 **_setargv**関数、 **_setenvp**として宣言する必要があります**extern"C"**です。  
  
 プログラムは、呼び出しを行うことがあります、**生成**または`exec`C ランタイム ライブラリ ルーチンのファミリです。 この場合、このルーチンは親プロセスから子プロセスに環境を渡すために使用されるため、環境処理ルーチンを抑制しないでください。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [main: プログラムの起動](../cpp/main-program-startup.md)