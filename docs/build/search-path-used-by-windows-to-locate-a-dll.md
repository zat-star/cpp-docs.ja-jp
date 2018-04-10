---
title: Windows が DLL の検索に使用するパスを検索 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- searching [C++], DLLs
- DLLs [C++], Windows search path
- Windows [C++], DLL search path
- known DLL searches [C++]
- locating DLLs
- finding DLLs
- search paths [C++]
ms.assetid: 84bfb380-ad7b-4962-b2d0-51b19a45f1bb
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 53350ed473226c86dd4fefa93cff376a371dedf7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="search-path-used-by-windows-to-locate-a-dll"></a>Windows が使用する DLL 検索パス
暗黙的なリンクと明示的なリンクの両方で、Windows は、Kernel32.dll や User32.dll などの "既知の DLL" を最初に検索します。 次に、以下に示す順序で DLL が検索されます。  
  
1.  実行中のプロセスの実行形式モジュールがあるフォルダー。  
  
2.  現在のフォルダー。  
  
3.  Windows システム フォルダー。 **GetSystemDirectory**関数は、このディレクトリのパスを取得します。  
  
4.  Windows ディレクトリ。 **GetWindowsDirectory**関数は、このディレクトリのパスを取得します。  
  
5.  環境変数 PATH 内に記述されたフォルダー。  
  
    > [!NOTE]
    >  環境変数 LIBPATH は使用しません。  
  
## <a name="what-do-you-want-to-do"></a>実行する操作  
  
-   [DLL を暗黙的にリンクする方法](../build/linking-an-executable-to-a-dll.md#linking-implicitly)  
  
-   [DLL を明示的にリンクする方法](../build/linking-an-executable-to-a-dll.md#linking-explicitly)  
  
-   [リンク方式を使い分け](../build/linking-an-executable-to-a-dll.md#determining-which-linking-method-to-use)  
  
## <a name="see-also"></a>参照  
 [Visual C++ の DLL](../build/dlls-in-visual-cpp.md)