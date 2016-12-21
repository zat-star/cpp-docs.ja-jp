---
title: "マルチバイト文字セット (MBCS) のサポート | Microsoft Docs"
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
  - "_mbcs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "文字セット [C++], マルチバイト"
  - "MBCS [C++]"
  - "MBCS [C++], 概要 (MBCS の)"
  - "マルチバイト文字 [C++]"
ms.assetid: b498733c-a1e1-45e3-8f26-d6da3cb5f2dd
caps.latest.revision: 11
caps.handback.revision: 11
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# マルチバイト文字セット (MBCS) のサポート
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

マルチバイト文字セット \(MBCS: Multibyte Character Set\) は、日本語や中国語など、1 バイト文字では表現できない文字セットをサポートするニーズに対する古いアプローチです。  新規開発を行う場合は、エンド ユーザーに対して表示されることのないシステム文字列を除き、すべてのテキスト文字列で Unicode 文字列を使用する必要があります。  MBCS は、レガシ テクノロジであり、新規開発にはお勧めしません。  
  
 最も一般的な MBCS の実装は、2 バイト文字セット \(DBCS: Double\-Byte Character Set\) です。  Visual C\+\+ と MFC では、DBCS に完全に対応しています。  
  
> [!WARNING]
>  Visual Studio 2013 以降では、マルチバイト文字エンコード \(MBCS\) 用の MFC ライブラリは Visual Studio に対するアドオンとして提供され、Visual Studio の顧客 \(Professional エディションと Enterprise エディションのみ\) は MSDN のダウンロード サイトから無料で入手できます。  
>   
>  ライブラリを使用するには、ドライブで約 440 MB が必要です。インストールには、ライブラリのすべてのローカライズ バージョンが含まれます。  Community、Professional、Enterprise のいずれかの Visual Studio のエディションがインストールされ、組み込みの MFC 機能が有効になっている任意のコンピューターにインストールできます。  
>   
>  Visual Studio をアンインストールまたは修復する場合は、MBCS ライブラリもアンインストールまたは修復されます。  ただし、MFC 機能のみを削除する場合は、MBCS ライブラリは、システムに残ります。  MBCS ライブラリを修復する場合は、Visual Studio はまったく変更されません。  
>   
>  Visual Studio 2013 以降を対象とする再頒布可能パッケージには、引き続き MBCS MFC DLL が含まれています。  DLL を顧客に再頒布するために、追加の手順は必要ありません。  
  
 サンプルについては、MFC ソース コード ファイルを参照してください。  
  
 大きな文字セットを採用している市場に対応したプラットフォームでは、Unicode の代わりとしては MBCS がまず考えられます。  MFC では、国際化に対応できるデータ型と C ランタイム関数を使用することにより MBCS をサポートしています。  プログラム コードでもこれらを使用するようにしてください。  
  
 MBCS では、1 バイトまたは 2 バイトのいずれかで文字がエンコードされます。  2 バイト文字では、最初にくる先頭バイトとその後ろに続くバイトの両方で 1 つの文字と解釈されるようになっています。  この最初のバイトは、先行バイト用に予約されている範囲の値をとります。  バイトのどの範囲が先行バイトとなるかは、使用するコード ページによって異なります。  たとえば、日本語のコード ページ 932 では 0x81 から 0x9F までの範囲を先行バイトとして使いますが、韓国語のコード ページ 949 では別の範囲を使っています。  
  
 MBCS のプログラミングでは、次の点について考慮する必要があります。  
  
 環境で使われる MBCS 文字  
 MBCS 文字は、ファイル名やフォルダー名などの文字列に使用できます。  
  
 編集操作  
 MBCS アプリケーションでの編集操作は、バイトではなく文字に対して行う必要があります。  カレットで文字を分割しないでください。右方向キーでは、右へ 1 文字移動します。  "**削除**" は 1 文字を削除し、"**元に戻す**" \(Undo\) は 1 文字を挿入し直すように機能する必要があります。  
  
 文字列操作  
 MBCS を使うアプリケーションでは、文字列操作で特殊な問題が出てきます。  1 つの文字列の中に 1 バイト幅の文字と 2 バイト幅の文字が混在しているため、先頭バイトがあるかどうかを必ず確認する必要があります。  
  
 ランタイム ライブラリのサポート  
 C のランタイム ライブラリおよび MFC は、1 バイト文字、MBCS、および Unicode でのプログラミングをそれぞれサポートしています。  1 バイトの文字列は、`str` ファミリのランタイム関数で処理します。MBCS 文字列は、対応する `_mbs` 関数で処理し、また Unicode 文字列は、対応する *wcs* 関数で処理します。  MFC クラスのメンバー関数では、状況に応じて、通常の `str` ファミリの関数、MBCS の関数、または Unicode の関数に割り当てる移植性の高いランタイム関数を使用しています。  
  
 MBCS と Unicode の移植性  
 Tchar.h ヘッダー ファイルを使用することにより、同じソースから 1 バイト、MBCS、および Unicode の各アプリケーションをビルドできます。  Tchar.h では、*\_tcs* プレフィックスが付いたマクロが定義されており、状況に応じて、`str`、`_mbs`、または *wcs* のいずれかの関数に割り当てます。  MBCS をビルドするには、シンボル **\_MBCS** を定義します。  Unicode をビルドするには、シンボル **\_UNICODE** を定義します。  MFC アプリケーションでは、既定として、**\_MBCS** が定義されています。  詳細については、「[Tchar.h における汎用テキストのマッピング](../Topic/Generic-Text%20Mappings%20in%20Tchar.h.md)」を参照してください。  
  
> [!NOTE]
>  **\_UNICODE** と **\_MBCS** の両方を定義すると、動作は正しく定義されなくなります。  
  
 Mbctype.h ヘッダー ファイルおよび Mbstring.h ヘッダー ファイルでは、MBCS 固有の関数とマクロが定義されています。この関数とマクロは状況に応じて必要になります。  たとえば `_ismbblead` は、文字列の特定のバイトが先行バイトかどうかを示します。  
  
 多言語間での移植性を持たせるには、プログラムを [Unicode](../text/support-for-unicode.md) またはマルチバイト文字セット \(MBCS\) でコーディングします。  
  
## 実行する操作  
  
-   [国際化対応について](../text/international-enabling.md)  
  
-   [国際化のアプローチ](../text/internationalization-strategies.md)  
  
-   [MBCS のプログラミングについて](../Topic/MBCS%20Programming%20Tips.md)  
  
-   [MBCS のプログラミングについて](../Topic/MBCS%20Programming%20Tips.md)  
  
-   [Tchar.h における汎用テキストのマッピング](../Topic/Generic-Text%20Mappings%20in%20Tchar.h.md)  
  
## 参照  
 [テキストと文字列](../text/text-and-strings-in-visual-cpp.md)   
 [Visual C\+\+ における MBCS のサポート](../text/mbcs-support-in-visual-cpp.md)