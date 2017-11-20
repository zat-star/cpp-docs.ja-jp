---
title: "Qpar (自動並行化) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.VCCLCompilerTool.EnableParallelCodeGeneration
dev_langs: C++
ms.assetid: 33ecf49d-c0d5-4f34-bce3-84ff03f38918
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 82f33d178799f56465f0d1a9794dacad7c01c77a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/24/2017
---
# <a name="qpar-auto-parallelizer"></a>/Qpar (自動並行化)
により、[自動並行化](../../parallel/auto-parallelization-and-auto-vectorization.md)を自動的に、コード内のループを並列化するコンパイラの機能です。  
  
## <a name="syntax"></a>構文  
  
```  
/Qpar  
```  
  
## <a name="remarks"></a>コメント  
 コンパイラでは、自動的にコード内のループを並列化、ときに、複数のプロセッサ コアを計算が分散させます。 これを行うことはおよびパフォーマンスが向上する並列化に、コンパイラが判断された場合のみループが並列化します。  
  
 `#pragma loop()`ディレクティブは、オプティマイザーが特定のループを並列化のために使用できます。 詳細については、次を参照してください。[ループ](../../preprocessor/loop.md)です。  
  
 自動並行化の出力メッセージを有効にする方法については、次を参照してください。 [/Qpar-report (自動並行化レポート作成レベル)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)です。  
  
### <a name="to-set-the-qpar-compiler-option-in-visual-studio"></a>Visual Studio で/Qpar コンパイラ オプションを設定するには  
  
1.  **ソリューション エクスプローラー**で、プロジェクトのショートカット メニューを開き、 **[プロパティ]**をクリックします。  
  
2.  **プロパティ ページ**ダイアログ ボックスで、 **C/C++****コマンド ライン**です。  
  
3.  **追加オプション**ボックスに、入力`/Qpar`です。  
  
### <a name="to-set-the-qpar-compiler-option-programmatically"></a>/Qpar コンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> のコード例を使用してください。  
  
## <a name="see-also"></a>関連項目  
 [/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)   
 [/Qpar-report (自動並行化レポート作成レベル)](../../build/reference/qpar-report-auto-parallelizer-reporting-level.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)   
 [#pragma loop()](../../preprocessor/loop.md)   
 [ネイティブ コードでの並列プログラミング](http://go.microsoft.com/fwlink/?LinkId=263662)