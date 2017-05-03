---
title: "コンパイラとリンカーのオプション (C++-CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ecfadce8-3a3f-40cc-bb01-b4731f8d2fcb
caps.latest.revision: 10
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 10
---
# コンパイラとリンカーのオプション (C++-CX)
[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 向けアプリの作成をサポートする環境変数、[!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] コンパイラ オプション、リンカー オプションがあります。  
  
## ライブラリのパス  
 %LIBPATH% 環境変数は、.winmd ファイルを検索するための既定パスを指定します。  
  
## コンパイラ オプション  
  
|オプション|説明|  
|-----------|--------|  
|[\/ZW](../build/reference/zw-windows-runtime-compilation.md)<br /><br /> \/ZW:nostdlib|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] 言語拡張機能を有効にします。<br /><br /> `nostdlib` パラメーターは、コンパイラが、アセンブリと .winmd ファイルの検索に標準の定義済み検索パスを使用しないようにします。<br /><br /> [\/ZW](../build/reference/zw-windows-runtime-compilation.md) コンパイラ オプションは、暗黙的に次のコンパイラ オプションを指定します。<br /><br /> -   [\/FI](../build/reference/fi-name-forced-include-file.md) vccorlib.h \- コンパイラで必要な多くの型を定義する vccorlib.h ヘッダー ファイルのインクルードを強制します。<br />-   [\/FU](../Topic/-FU%20\(Name%20Forced%20%23using%20File\).md) Windows.winmd \- オペレーティング システムが提供し、[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] の多くの型を定義する Windows.winmd メタデータ ファイルのインクルードを強制ます。<br />-   [\/FU](../Topic/-FU%20\(Name%20Forced%20%23using%20File\).md) Platform.winmd \- コンパイラが提供し、名前空間のプラットフォーム ファミリのほとんどの型を定義する Platform.winmd メタデータ ファイルのインクルードを強制します。|  
|[\/AI](../build/reference/ai-specify-metadata-directories.md) *dir*|*dir* パラメーターに指定されたディレクトリを、コンパイラがアセンブリと .winmd ファイルを検索するために使用する検索パスに追加します。|  
|[\/FU](../Topic/-FU%20\(Name%20Forced%20%23using%20File\).md) *ファイル*|指定されたモジュールまたは .winmd ファイルのインクルードを強制します。 つまり、ソース コード内に `#using`*file* を指定する必要はありません。 コンパイラは、独自の Windows メタデータ ファイル Platform.winmd のインクルードを自動的に強制します。|  
|\/D"WINAPI\_FAMILY \= 2"|[!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] と互換性のある Win32 SDK のサブセットの使用を有効にする定義を作成します。|  
  
## リンカー オプション  
  
|オプション|説明|  
|-----------|--------|  
|\/APPCONTAINER\[:NO\]|実行可能ファイルを、AppContainer \(のみ\) で実行可能としてマークを付けます。|  
|\/WINMD\[:{NO&#124;ONLY}\]|.winmd ファイルと関連するバイナリ ファイルを生成します。 このオプションは、生成する .winmd のリンカーに渡す必要があります。<br /><br /> **NO**—.winmd ファイルは生成しませんが、バイナリ ファイルを生成します。<br /><br /> **ONLY**—..winmd ファイルを生成しますが、バイナリ ファイルは生成しません。|  
|\/WINMDFILE:*filename*|生成する .winmd ファイルの名前。既定の .winmd ファイル名の代わりに使用されます。 コマンド ラインで複数のファイル名を指定すると、最後の名前が使用されます。|  
|\/WINMDDELAYSIGN\[:NO\]|部分的に .winmd ファイルに署名し、公開キーをバイナリに配置します。<br /><br /> **NO**—\(既定\) .winmd ファイルに署名しません。<br /><br /> \/WINMDKEYFILE または \/WINMDKEYCONTAINER も指定しないかぎり、\/WINMDDELAYSIGN の影響はありません。|  
|\/WINMDKEYCONTAINER:*name*|アセンブリに署名するためのキー コンテナーを指定します。*name* パラメーターは、メタデータ ファイルの署名に使用するキー コンテナーに対応します。|  
|\/WINMDKEYFILE:*filename*|アセンブリに署名するためのキーまたはキー ペアを指定します。*filename* パラメーターは、メタデータ ファイルの署名に使用するキーに対応します。|  
  
## 解説  
 **\/ZW** が使用されると、コンパイラは DLL バージョンの C ランタイム \(CRT\) に自動的にリンクします。 スタティック ライブラリ バージョンにはリンクできません。また、[!INCLUDE[win8_appname_long](../cppcx/includes/win8-appname-long-md.md)] アプリで許可されていない CRT 関数を使用すると、コンパイル時のエラーが発生します。  
  
## 参照  
 [アプリケーションとライブラリのビルド](../cppcx/building-apps-and-libraries-c-cx.md)