---
title: "スタック (スタック割り当て) |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCLinkerTool.StackReserveSize
- VC.Project.VCLinkerTool.StackCommitSize
- /stack
dev_langs: C++
helpviewer_keywords:
- STACK linker option
- -STACK linker option
- memory allocation, stack
- /STACK linker option
- stack, setting size
ms.assetid: 73283660-e4bd-47cc-b5ca-04c5d739034c
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6b487ff830abd3dfa97a748c81d541cbd9fdd0b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="stack-stack-allocations"></a>/STACK (スタック割り当て)
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>コメント  
 /STACK オプションは、スタックのサイズをバイト単位で指定します。 このオプションは、.exe ファイルのビルドだけに使用します。  
  
 `reserve` 値は、仮想メモリ内のスタック割り当ての合計サイズを指定します。 ARM、x86、および [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] コンピューターの場合、既定のスタック のサイズは 1 MB です。  
  
 `commit` は、オペレーティング システムによって解釈が異なります。 Windows WindowsRT では、一度に確保する物理メモリ量です。 仮想メモリがコミットされると、ページング ファイル内にメモリ空間が予約されます。 `commit` の値を大きく設定すると、アプリケーションに必要なスタック領域が増えたときに処理時間を節約できます。ただし、必要なメモリ量と起動時間が増えます。 ARM、x86、および [!INCLUDE[vcprx64](../../assembler/inline/includes/vcprx64_md.md)] コンピューターの場合、既定のコミット値は 4 KB です。  
  
 引数 `reserve` と引数 `commit` の値は、10 進表記か C 言語表記で指定します。  
  
 スタックのサイズを設定する別の方法は、 [STACKSIZE](../../build/reference/stacksize.md)モジュール定義 (.def) ファイル内のステートメント。 **STACKSIZE**オーバーライド スタック割り当て (/stack) オプションの両方を指定した場合は。 スタック サイズを変更するには、.exe ファイルを使用してビルドした後、 [EDITBIN](../../build/reference/editbin-reference.md)ツールです。  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「 [Visual C プロジェクト プロパティの設定](../../ide/working-with-project-properties.md)です。  
  
2.  選択、**リンカー**フォルダーです。  
  
3.  選択、**システム**プロパティ ページ。  
  
4.  次のいずれかのプロパティを変更します。  
  
    -   **スタックのコミット サイズ**  
  
    -   **スタックのサイズ**  
  
### <a name="to-set-this-linker-option-programmatically"></a>このリンカーをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackCommitSize%2A> プロパティおよび <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.StackReserveSize%2A> プロパティを参照してください。  
  
## <a name="see-also"></a>参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)