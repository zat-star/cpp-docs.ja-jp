---
title: "リンカー ツールの警告 LNK4210 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4210
dev_langs:
- C++
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
caps.latest.revision: 12
author: corob-msft
ms.author: corob
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
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 127d4bdc85d07468f91656bc0aff5f4f2d015df5
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4210"></a>リンカー ツールの警告 LNK4210
セクションが存在します。ある場合がありますハンドルされていない静的初期化子または終端文字  
  
 静的初期化子、またはターミネータ、いくつかのコードが導入されましたが、アプリケーションの起動時に、CRT またはそれと等価な (これは、静的初期化子または終端文字を実行する必要があります) が実行されていません。 これが発生するコードの例:  
  
-   コンス トラクター、デストラクター、または仮想関数テーブルを含むクラスのグローバル変数。  
  
-   グローバル変数が非コンパイル時定数を使用して初期化します。  
  
 この問題を修正するのには、次のいずれかを試してください。  
  
-   静的初期化子を持つすべてのコードを削除します。  
  
-   使用しないで[/NOENTRY](../../build/reference/noentry-no-entry-point.md)します。  /NOENTRY を削除した後、msvcrt.lib、libcmt.lib、libcmtd.lib をリンカーのコマンドラインに追加することもできます。  
  
-   Msvcrt.lib、libcmt.lib、libcmtd.lib をリンカーのコマンドラインに追加します。  
  
-   /Clr から移行する場合:/clr コンパイルは純粋な削除、 [/ENTRY](../../build/reference/entry-entry-point-symbol.md)リンカー コマンドラインのオプションです。 これは、CRT の初期化で、アプリケーションの起動時に実行する静的初期化子を有効になります。  
  
-   場合は、プロジェクトのビルドに[/ENTRY](../../build/reference/entry-entry-point-symbol.md)、/ENTRY が渡された場合、関数の他にも、`_DllMainCRTStartup`関数が CRT_INIT を呼び出す必要があります。 参照してください[ランタイム ライブラリの動作](../../build/run-time-library-behavior.md)とサポート技術情報の記事 Q94248、 [http://support.microsoft.com/default.aspx?scid=kb;en-us;94248](http://support.microsoft.com/default.aspx?scid=kb;en-us;94248)の詳細。  
  
 [/GS](../../build/reference/gs-buffer-security-check.md)コンパイラ オプションには、CRT スタートアップ コードが必要です。  
  
## <a name="see-also"></a>関連項目  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)
