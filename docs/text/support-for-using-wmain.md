---
title: "Wmain の使用 |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- wWinMain
dev_langs:
- C++
helpviewer_keywords:
- wide characters [C++], wmain function
- wWinMain function
- wmain function
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 721915ca5ebbc75b17771dae0804e94aa360177c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="support-for-using-wmain"></a>wmain の使用
Visual C のサポートを定義する、 **wmain**関数を Unicode アプリケーションにワイド文字の引数を渡すことです。 仮パラメーターを宣言する**wmain**と同様の形式を使用して**メイン**です。 さらに、ワイド文字の引数と、必要であればワイド文字環境ポインターもプログラムに渡すことができます。 **wmain** の引数 `argv` と `envp` の型は `wchar_t*` です。 例:  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  MFC の Unicode アプリケーションを使用して**wWinMain**エントリ ポイントとして。 この場合、 `CWinApp::m_lpCmdLine` Unicode 文字列です。 設定して**wWinMainCRTStartup**で、 [/ENTRY](../build/reference/entry-entry-point-symbol.md)リンカー オプション。  
  
 プログラムが **main** 関数を使用している場合、マルチバイト文字環境は、プログラムの起動時にランタイム ライブラリが作成します。 マルチバイト文字環境で使われるワイド文字のコピーは、必要に応じて作成されます (たとえば、`_wgetenv` 関数や `_wputenv` 関数が呼び出されたとき)。 最初の呼び出しで`_wputenv`、または最初の呼び出しで`_wgetenv`対応するワイド文字列環境が作成された MBCS 環境が既に存在する場合。 環境が、指す、`_wenviron`ワイド文字バージョンでは、グローバル変数の`_environ`グローバル変数。 この時点では、2 つのコピー (MBCS および Unicode) 環境のでは、同時に存在し、プログラムの有効期間全体にわたって実行時のシステムによって保持されます。  
  
 プログラムが **wmain** 関数を使っている場合は、ワイド文字環境がプログラムの起動時に作成され、また `_wenviron` グローバル変数によって環境のアドレスが示されます。 最初の呼び出しで、MBCS (ASCII) 環境が作成された`_putenv`または`getenv`によって指されると、`_environ`グローバル変数。  
  
## <a name="see-also"></a>参照  
 [Unicode のサポート](../text/support-for-unicode.md)   
 [Unicode プログラミングの要約](../text/unicode-programming-summary.md)   
 [WinMain 関数](http://msdn.microsoft.com/library/windows/desktop/ms633559)