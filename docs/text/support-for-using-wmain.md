---
title: "wmain の使用 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "wWinMain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ワイド文字 [C++], wmain 関数"
  - "wmain 関数"
  - "wWinMain 関数"
ms.assetid: 41213c41-668c-40a4-8a1e-77d9eded720d
caps.latest.revision: 9
caps.handback.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# wmain の使用
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ では、**wmain** 関数を定義して、Unicode アプリケーションにワイド文字引数を渡すことができます。  **wmain** に渡す仮引数は、**main** に渡す際の形式に準拠して宣言します。  さらに、ワイド文字の引数と、必要であればワイド文字環境ポインターもプログラムに渡すことができます。  wmain の引数 `argv` と `envp` の型は `wchar_t*` です。  たとえば、次のようになります。  
  
```  
wmain( int argc, wchar_t *argv[ ], wchar_t *envp[ ] )  
```  
  
> [!NOTE]
>  MFC の Unicode アプリケーションでは、エントリ ポイントとして **wWinMain** を使用します。  この場合、`CWinApp::m_lpCmdLine` は、Unicode 文字列になります。  [\/ENTRY](../build/reference/entry-entry-point-symbol.md) リンカー オプションを使用して **wWinMainCRTStartup** を設定してください。  
  
 プログラムが **main** 関数を使用している場合、マルチバイト文字環境は、プログラムの起動時にランタイム ライブラリが作成します。  マルチバイト文字環境で使われるワイド文字のコピーは、必要に応じて作成されます \(たとえば、`_wgetenv` 関数や `_wputenv` 関数が呼び出されたとき\)。  MBCS 環境が既に存在している場合は、`_wputenv` または `_wgetenv` を初めて呼び出したときに、対応するワイド文字列環境が作成されます。  次に、`_environ` グローバル変数のワイド文字版である `_wenviron` グローバル変数が、その環境へのポインターとなります。  この時点までで、2 つの環境のコピー \(MBCS および Unicode\) が同時に存在していることになるわけですが、両方ともプログラムが消滅するまでランタイム システムによって保持されます。  
  
 プログラムが **wmain** 関数を使っている場合は、ワイド文字環境がプログラムの起動時に作成され、また `_wenviron` グローバル変数によって環境のアドレスが示されます。  MBCS \(ASCII\) 環境は、`_putenv` または `getenv` を初めて呼び出したときに作成され、`_environ` グローバル変数によってアドレスが示されます。  
  
## 参照  
 [Unicode のサポート](../text/support-for-unicode.md)   
 [Unicode プログラミングの要約](../text/unicode-programming-summary.md)   
 [WinMain 関数](http://msdn.microsoft.com/library/windows/desktop/ms633559)