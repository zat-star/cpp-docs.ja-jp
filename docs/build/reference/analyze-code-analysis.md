---
title: "/analyze (コード分析) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLCompilerTool.EnablePREfast"
  - "/analyze"
  - "VC.Project.VCCLCompilerTool.PREfastAdditionalOptions"
  - "VC.Project.VCCLCompilerTool.PREfastAdditionalPlugins"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/analyze コンパイラ オプション [C++]"
  - "analyze コンパイラ オプション [C++]"
  - "-analyze コンパイラ オプション [C++]"
ms.assetid: 81da536a-e030-4bd4-be18-383927597d08
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# /analyze (コード分析)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コード分析とコントロール オプションを有効にします。  
  
## 構文  
  
```  
/analyze[-][:WX-][:log filename][:quiet][:stacksize number][:max_paths number][:only]  
```  
  
## 引数  
 \/analyze  
 既定のモードで分析をオンにします。  分析の出力は、他のエラー メッセージのように **\[出力\]** ウィンドウに移動します。  分析を明示的にオフにするには、**\/analyze\-** を使用します。  
  
 \/analyze:WX\-  
 **\/analyze:WX\-** を指定すると、**\/WX** を使用してコンパイルするときに、コード分析の警告がエラーとして処理されません。  詳細については、「[\/w、\/Wn、\/WX、\/Wall、\/wln、\/wdn、\/wen、\/won \(警告レベル\)](../../build/reference/compiler-option-warning-level.md)」を参照してください。  
  
 \/analyze:log `filename`  
 詳細なアナライザーの結果が、`filename` で指定されたファイルに XML として書き込まれます。  
  
 \/analyze:quiet  
 **\[出力\]** ウィンドウへのアナライザーの出力をオフにします。  
  
 \/analyze:stacksize `number`  
 このオプションと共に使用される `number` パラメーターでは、[C6262](../Topic/C6262.md) 警告が生成されたスタック フレームのサイズをバイト単位で指定します。  このパラメーターが指定されていない場合は、既定の 16 KB がスタック フレーム サイズとして使用されます。  
  
 \/analyze:max\_paths `number`  
 このオプションと共に使用される `number` パラメーターでは、分析するコード パスの最大数を指定します。  このパラメーターが指定されていない場合は、既定の 256 が最大数として使用されます。  値を大きくすると、より細かなチェックが実行されますが、分析に時間がかかることがあります。  
  
 \/analyze:only  
 通常、コンパイラは、アナライザーを実行した後にコードを生成し、構文チェックをさらに実行します。  **\/analyze:only** オプションを使用すると、このコード生成パスがオフになるため、分析をさらに高速に実行できますが、コンパイラのコード生成パスによって検出された可能性があるコンパイラのエラーと警告が出力されません。  プログラムにコード生成のエラーがある場合は、分析結果が信頼できないものになる可能性があるため、このオプションを使用するのは、コードが既にコード生成構文チェックをエラーなしで渡している場合だけにすることをお勧めします。  
  
## 解説  
 詳細については、「[C\/C\+\+ のコード分析の概要](../Topic/Code%20Analysis%20for%20C-C++%20Overview.md)」および「[C\/C\+\+ コードの警告に対応するコードの分析](../Topic/Code%20Analysis%20for%20C-C++%20Warnings.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[コード分析\]** ノードを展開します。  
  
4.  **\[全般\]** プロパティ ページをクリックします。  
  
5.  **\[コード分析\]** のプロパティを 1 つ以上変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
1.  <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.EnablePREfast%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)