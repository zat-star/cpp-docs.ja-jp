---
title: "Dll の遅延読み込みの制約 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- constraints [C++], delayed loading of DLLs
- delayed loading of DLLs, constraints
- DLLs [C++], constraints
ms.assetid: 0097ff65-550f-4a4e-8ac3-39bf6404f926
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1f952de894cad02638a7f304590562f1846bc003
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="constraints-of-delay-loading-dlls"></a>DLL の遅延読み込みの制約
インポートの遅延読み込みには制約があります。  
  
-   データのインポートはサポートされません。 その回避策として、`LoadLibrary` (または遅延読み込みヘルパーが DLL を読み込んだことが確認された後は `GetModuleHandle`) および `GetProcAddress` を使用してデータ インポートを自分で明示的に処理します。  
  
-   遅延読み込み Kernel32.dll はサポートされません。 この DLL は、遅延読み込みヘルパー ルーチンが遅延読み込みを実行するのに必要です。  
  
-   [バインド](../../build/reference/binding-imports.md)のエントリ ポイントは、転送されることはできません。  
  
-   遅延読み込み DLL のエントリ ポイントでプロセスごとに初期化が起こる場合、DLL の遅延読み込みでプロセスの動作が同じにならない可能性があります。 それ以外の場合を使用して宣言する静的 TLS (スレッド ローカル ストレージ) を含める[_declspec](../../cpp/thread.md)を使用して、DLL が読み込まれるときに処理されません`LoadLibrary`です。 `TlsAlloc`、`TlsFree`、`TlsGetValue`、および `TlsSetValue` を使用した動的 TLS は、静的または遅延読み込み DLL で引き続き利用可能です。  
  
-   静的 (グローバル) 関数ポインターは、関数への最初の呼び出しの後に、インポートされた関数について再初期化する必要があります。 これは、関数ポインターを最初に使用するときにはサンクをポイントするからです。  
  
-   現時点では、通常のインポート メカニズムを使いながら、DLL の特定の手順の読み込みだけを遅延する方法はありません。  
  
-   カスタム呼び出し規約 (x86 アーキテクチャでの条件コードの使用など) はサポートされません。 また、浮動小数点レジスタはどのプラットフォームにも保存されません。 カスタム ヘルパー ルーチンまたはフック ルーチンが浮動小数点型を使用する場合、浮動小数点パラメーターのレジスタ呼び出し規約を持つコンピューターで浮動小数点状態を完全に保存およびリストアする必要があります。 ヘルプ関数内の数値データ プロセッサ (NDP) スタックで、浮動小数点パラメーターを取得する CRT 関数を呼び出す場合、CRT DLL の遅延呼び出しに注意します。  
  
## <a name="see-also"></a>関連項目  
 [リンカーによる Dll の遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)   
 [LoadLibrary 関数](http://msdn.microsoft.com/library/windows/desktop/ms684175.aspx)   
 [GetModuleHandle 関数](http://msdn.microsoft.com/library/windows/desktop/ms683199.aspx)   
 [GetProcAddress 関数](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx)   
 [TlsAlloc 関数](http://msdn.microsoft.com/library/windows/desktop/ms686801.aspx)   
 [TlsFree 関数](http://msdn.microsoft.com/library/windows/desktop/ms686804.aspx)   
 [TlsGetValue 関数](http://msdn.microsoft.com/library/windows/desktop/ms686812.aspx)   
 [TlsSetValue 関数](http://msdn.microsoft.com/library/windows/desktop/ms686818.aspx)