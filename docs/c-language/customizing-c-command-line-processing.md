---
title: "C コマンド ライン パラメーターの処理 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- _spawn functions
- command line, processing
- command-line processing
- startup code, customizing command-line processing
- environment, environment-processing routine
- _setargv function
- command line, processing arguments
- suppressing environment processing
- _exec function
ms.assetid: c20fa11d-b35b-4f3e-93b6-2cd5a1c3c993
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: fd7217a12616fca234ed1fcd8a3c31f0b46a1ba0
ms.contentlocale: ja-jp
ms.lasthandoff: 05/18/2017

---
# <a name="customizing-c-command-line-processing"></a>コマンド ライン パラメーターの処理
プログラムがコマンド ラインの引数を受け取らない場合は、コマンド ライン処理を実行するライブラリ ルーチンの使用を制約することで、領域を節約できます。 このルーチンは、「[ワイルドカード引数の展開](../c-language/expanding-wildcard-arguments.md)」で説明されているように、**_setargv** (ワイド文字環境では **_wsetargv**) と呼ばれます。 使用を抑制するには、**main** 関数を含むファイルの中に何も実行しないルーチンを定義し、**_setargv** (ワイド文字環境の場合は **_wsetargv**) という名前を付けます。 これにより、**_setargv** または **_wsetargv** の呼び出しが **_setargv** または **_wsetargv** の定義によって満たされるため、ライブラリ バージョンは読み込まれません。  
  
 同様に、`envp` 引数を使用して環境テーブルにアクセスしない場合は、環境処理ルーチンである **_setenvp** (または **_wsetenvp**) の代わりに独自の空ルーチンを指定できます。  
  
 プログラムが C ランタイム ライブラリ ルーチンの **_spawn** または **_exec** ファミリを呼び出す場合、起動元のプロセスから新しいプロセスに環境を渡すためにこのルーチンが使用されているので、環境処理ルーチンを抑制しないでください。  
  
## <a name="see-also"></a>関連項目  
 [main 関数とプログラム実行](../c-language/main-function-and-program-execution.md)
