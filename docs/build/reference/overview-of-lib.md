---
title: "LIB の概要 | Microsoft Docs"
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
  - "Lib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LIB [C++], モード"
ms.assetid: e997d423-f574-434f-8b56-25585d137ee0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# LIB の概要
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

LIB は、プログラムをビルドするときに [LINK](../../build/reference/linker-options.md) で使用できる標準ライブラリ、インポート ライブラリ、およびエクスポート ファイルを作成します。  LIB はコマンド ラインから実行します。  
  
 LIB は、次のモードで使用できます。  
  
-   [ライブラリの管理](../../build/reference/managing-a-library.md)  
  
-   [ライブラリ メンバーの抽出](../../build/reference/extracting-a-library-member.md)  
  
-   [インポート ライブラリとエクスポート ファイル](../../build/reference/working-with-import-libraries-and-export-files.md)  
  
 これらのモードは相互に排他的です。LIB は、一度に 1 つのモードでしか使用できません。  
  
## LIB オプション  
 次の表に、lib.exe のオプションとその参照先へのリンクを示します。  
  
 **\/DEF**  
 インポート ライブラリとエクスポート ファイルを作成します。  
  
 詳細については、「[インポート ライブラリとエクスポート ファイルのビルド](../../build/reference/building-an-import-library-and-export-file.md)」を参照してください。  
  
 **\/ERRORREPORT**  
 lib.exe の内部エラー情報を Microsoft に送信します。  
  
 詳細については、「[LIB の実行](../../build/reference/running-lib.md)」を参照してください。  
  
 **\/EXPORT**  
 プログラムから関数をエクスポートします。  
  
 詳細については、「[インポート ライブラリとエクスポート ファイルのビルド](../../build/reference/building-an-import-library-and-export-file.md)」を参照してください。  
  
 **\/EXTRACT**  
 既存のライブラリのメンバーからオブジェクト \(.obj\) ファイルを作成します。  
  
 詳細については、「[ライブラリ メンバーの抽出](../../build/reference/extracting-a-library-member.md)」を参照してください。  
  
 **\/INCLUDE**  
 シンボル テーブルにシンボルを追加します。  
  
 詳細については、「[インポート ライブラリとエクスポート ファイルのビルド](../../build/reference/building-an-import-library-and-export-file.md)」を参照してください。  
  
 **\/LIBPATH**  
 環境で指定されるライブラリのパスを一時的に変更します。  
  
 詳細については、「[ライブラリの管理](../../build/reference/managing-a-library.md)」を参照してください。  
  
 **\/LIST**  
 出力ライブラリに関する情報を標準出力に表示します。  
  
 詳細については、「[ライブラリの管理](../../build/reference/managing-a-library.md)」を参照してください。  
  
 **\/LTCG**  
 リンク時コード生成を使用してライブラリがビルドされます。  
  
 詳細については、「[LIB の実行](../../build/reference/running-lib.md)」を参照してください。  
  
 **\/MACHINE**  
 プログラムのターゲット プラットフォームを指定します。  
  
 詳細については、「[LIB の実行](../../build/reference/running-lib.md)」を参照してください。  
  
 **\/NAME**  
 インポート ライブラリをビルドするときに、そのインポート ライブラリの対象となる DLL の名前を指定します。  
  
 詳細については、「[ライブラリの管理](../../build/reference/managing-a-library.md)」を参照してください。  
  
 **\/NODEFAULTLIB**  
 外部参照を解決するときに、検索するライブラリ リストから既定のライブラリを除外します。  
  
 詳細については、「[ライブラリの管理](../../build/reference/managing-a-library.md)」を参照してください。  
  
 **\/NOLOGO**  
 LIB の著作権情報とバージョン情報が表示されなくなり、コマンド ファイルもエコーされません。  
  
 詳細については、「[LIB の実行](../../build/reference/running-lib.md)」を参照してください。  
  
 **\/OUT**  
 既定の出力ファイル名を変更します。  
  
 詳細については、「[ライブラリの管理](../../build/reference/managing-a-library.md)」を参照してください。  
  
 **\/REMOVE**  
 オブジェクトを出力ライブラリから削除します。  
  
 詳細については、「[ライブラリの管理](../../build/reference/managing-a-library.md)」を参照してください。  
  
 **\/SUBSYSTEM**  
 オペレーティング システムに対して、出力ライブラリにリンクして作成されたプログラムの実行方法を指示します。  
  
 詳細については、「[ライブラリの管理](../../build/reference/managing-a-library.md)」を参照してください。  
  
 **\/VERBOSE**  
 追加されている .obj ファイルの名前など、セッションの進行状況を詳しく表示します。  
  
 詳細については、「[LIB の実行](../../build/reference/running-lib.md)」を参照してください。  
  
 **\/WX**  
 警告をエラーとして扱います。  
  
 詳細については、「[LIB の実行](../../build/reference/running-lib.md)」を参照してください。  
  
## 参照  
 [LIB リファレンス](../../build/reference/lib-reference.md)   
 [LIB の入力ファイル](../../build/reference/lib-input-files.md)   
 [LIB の出力ファイル](../../build/reference/lib-output-files.md)   
 [LIB のその他の出力](../../build/reference/other-lib-output.md)   
 [ライブラリの構造](../../build/reference/structure-of-a-library.md)