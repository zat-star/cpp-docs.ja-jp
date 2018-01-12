---
title: "一般的な問題、リリース ビルドを作成するときに |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- unexpected code generation
- debugging [MFC], release builds
- release builds, troubleshooting
- stray pointers
- debug builds, difference from release builds
- MFC [C++], release builds
- heap layout problems
- pointers, stray
- release builds, building applications
- debug memory allocator
- optimization [C++], compiler
- projects [C++], debug configuration
- troubleshooting Visual C++
- troubleshooting release builds
- memory [C++], overwrites
ms.assetid: 73cbc1f9-3e33-472d-9880-39a8e9977b95
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 44b5528a2d6bedaaaa7ddce582f58042e084b3d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="common-problems-when-creating-a-release-build"></a>リリース ビルド作成時によくある問題
開発中は、通常ビルドし、プロジェクトのデバッグ ビルドをテストします。 リリース ビルド用にアプリケーションをビルドする場合アクセス違反が発生する可能性があります。  
  
 以下の一覧は、デバッグとリリース (非デバッグ) ビルドの間の主な違いを示しています。 その他の違いがありますが、原因となるアプリケーションが失敗するリリース ビルドでは、デバッグ ビルドで使用する場合の主な違いを次に示します。  
  
-   [ヒープ レイアウト](#_core_heap_layout)  
  
-   [コンパイル](#_core_compilation)  
  
-   [ポインターのサポート](#_core_pointer_support)  
  
-   [最適化](#_core_optimizations)  
  
 参照してください、 [/GZ (キャッチ リリース ビルド エラーのデバッグ ビルドで)](../../build/reference/gz-enable-stack-frame-run-time-error-checking.md)コンパイラ オプション リリースをキャッチする方法については、デバッグ ビルドでエラーをビルドします。  
  
##  <a name="_core_heap_layout"></a>ヒープ レイアウト  
 ヒープ レイアウトには、デバッグがないリリースで動作するアプリケーション、約 90% を見かけ上の問題の原因になります。  
  
 デバッグするためにプロジェクトをビルドすると、デバッグ メモリ アロケーターを使用しています。 これは、すべてのメモリ割り当ては、それらの周りに配置ガード バイトであることを意味します。 これらガード バイトがメモリの上書きを検出します。 ヒープ レイアウトはリリースとデバッグの間で異なるためバージョンでは、メモリの上書きは、デバッグ ビルドに問題を作成せず可能性がありますが、リリース ビルドで壊滅的な効果があります。  
  
 詳細については、次を参照してください。[メモリ上書きのチェック](../../build/reference/checking-for-memory-overwrites.md)と[メモリ上書きのデバッグ ビルドにチェックを使用して](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)です。  
  
##  <a name="_core_compilation"></a>コンパイル  
 MFC マクロとリリース用にビルドするときに、MFC 実装の変更の多くの多くは。 具体的には、アサートのコードのいずれも実行されるので、ASSERT マクロは、リリース ビルドでは nothing に評価されます。 詳細については、次を参照してください。 [ASSERT ステートメントの確認](../../build/reference/using-verify-instead-of-assert.md)です。  
  
 一部の関数は、リリース ビルドで速度を上げるためインライン展開されます。 一般に、最適化は、リリース ビルドでになっています。 別のメモリ アロケーターも使用されています。  
  
##  <a name="_core_pointer_support"></a>ポインターのサポート  
 デバッグ情報の欠如は、アプリケーションからの余白を削除します。 リリース ビルドでは、無効なポインターは、デバッグ情報へのポイントではなく、初期化されていないメモリを指す可能性が高くをあります。  
  
##  <a name="_core_optimizations"></a>最適化  
 コードの特定のセグメントの性質、によって最適化コンパイラは、予期しないコードを生成可能性があります。 これはリリース ビルドの問題の最も可能性がありますが、これが発生した場合になる場合。 ソリューションで、次を参照してください。[コードの最適化](../../build/reference/optimizing-your-code.md)です。  
  
## <a name="see-also"></a>参照  
 [リリース ビルド](../../build/reference/release-builds.md)   
 [リリース ビルドの問題の解決](../../build/reference/fixing-release-build-problems.md)