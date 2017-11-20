---
title: "コンパイラ オプション |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler
- IPF Visual C++ compiler
- Itanium Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 490814f85199450d4261bf4071184b75b5ea10c2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-options"></a>コンパイラ オプション
cl.exe は、Microsoft C および C++ コンパイラとリンカーを制御するツールです。 cl.exe は、Microsoft Visual Studio をサポートするオペレーティング システムでのみ実行できます。  
  
> [!NOTE]
>  このツールは、[!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)] コマンド プロンプトからのみ開始できます。 システム コマンド プロンプトやエクスプローラーからは開始できません。  
  
 コンパイラは、COFF (Common Object File Format) 形式のオブジェクト (.obj) ファイルを生成します。 リンカーは、実行可能 (.exe) ファイルまたはダイナミック リンク ライブラリ (DLL: Dynamic-Link Library) を生成します。  
  
 すべてのコンパイラ オプションで、大文字小文字を区別します。  
  
 使用せずにコンパイルするリンク、 [/c](../../build/reference/c-compile-without-linking.md)です。  
  
## <a name="finding-an-option"></a>オプションの検索  
 特定のコンパイラ オプションを見つけるには、次のいずれかの一覧を参照してください。  
  
-   [アルファベット順のコンパイラ オプション](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [カテゴリ別のコンパイラ オプション](../../build/reference/compiler-options-listed-by-category.md)  
  
## <a name="specifying-options"></a>オプションの指定  
 開発環境での設定方法は、コンパイラの各オプションのトピックで説明します。 開発環境以外からオプションを指定する方法の詳細については、下記を参照してください。  
  
-   [コンパイラ コマンド ラインの構文](../../build/reference/compiler-command-line-syntax.md)  
  
-   [CL コマンド ファイル](../../build/reference/cl-command-files.md)  
  
-   [CL 環境変数](../../build/reference/cl-environment-variables.md)  
  
## <a name="related-build-tools"></a>関連ビルド ツール  
 使用して[NMAKE](../../build/nmake-reference.md)出力ファイルをビルドします。  
  
 使用して[BSCMAKE](../../build/reference/bscmake-reference.md)クラス参照をサポートするためにします。  
  
 [リンカー オプション](../../build/reference/linker-options.md)プログラムのビルド方法にも影響します。  
  
## <a name="see-also"></a>関連項目  
 [C/C++ ビルドのリファレンス](../../build/reference/c-cpp-building-reference.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [高速コンパイル](../../build/reference/fast-compilation.md)   
 [リンカーを呼び出す CL](../../build/reference/cl-invokes-the-linker.md)