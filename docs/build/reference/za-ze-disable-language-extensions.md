---
title: "/Za、/Ze (言語拡張機能の無効化) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions"
  - "/za"
  - "/ze"
  - "VC.Project.VCCLCompilerTool.DisableLanguageExtensions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Za コンパイラ オプション [C++]"
  - "/Ze コンパイラ オプション [C++]"
  - "Disable Language Extensions コンパイラ オプション"
  - "有効化 (言語拡張機能を)"
  - "言語拡張"
  - "言語拡張, 無効化 (コンパイラで)"
  - "Za コンパイラ オプション [C++]"
  - "-Za コンパイラ オプション [C++]"
  - "Ze コンパイラ オプション [C++]"
  - "-Ze コンパイラ オプション [C++]"
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Za、/Ze (言語拡張機能の無効化)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**\/Za** コンパイラ オプションは、ANSI C または ANSI C\+\+ と互換性のない言語構成要素にエラーを出力します。  既定である**\/Ze** コンパイラ オプションは Microsoft 拡張機能を有効にします。  
  
## 構文  
  
```  
/Za  
/Ze  
```  
  
## 解説  
  
> [!NOTE]
>  **\/Ze** オプションの使用は推奨されていません。  詳細については、「[Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ja-jp/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)」を参照してください。  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] コンパイラでは、ANSI C または ANSI C\+\+ 規格以外の機能を多数用意しています。  これらの機能はまとめて、C および C\+\+ の Microsoft 拡張機能として知られています。  これらの拡張機能は、**\/Ze** オプションを指定すると使用可能になり、**\/Za** オプションを指定すると使用不能になります。  詳細については、「[Microsoft C\/C\+\+ の拡張機能](../../build/reference/microsoft-extensions-to-c-and-cpp.md)」を参照してください。  
  
 プログラムをほかの環境に移植する予定がある場合は、拡張機能を無効にします。  このオプションを選択してコンパイルを行うと、拡張キーワードが単に識別子として処理されるため、Microsoft のその他の拡張機能が無効になり、C プログラム用の組み込みマクロとして `__STDC__` マクロが自動的に定義されます。  
  
 その他のコンパイラ オプションを **\/Za** と共に使用すると、コンパイラが ANSI への準拠を確保する方法に影響が及ぶことがあります。  たとえば、**\/Za** と [\/fp \(浮動小数点の動作の指定\)](../../build/reference/fp-specify-floating-point-behavior.md) を併用すると、予期しない動作が発生する可能性があります。  
  
 **\/Za** の標準動作を指定する方法については、[\/Zc](../../build/reference/zc-conformance.md) コンパイラ オプションに関するトピックを参照してください。  
  
 [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] の準拠の問題の詳細については、「[Visual C\+\+ での互換性と準拠の問題](../../misc/compatibility-and-compliance-issues-in-visual-cpp.md)」を参照してください。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[言語\]** プロパティ ページをクリックします。  
  
4.  **\[言語拡張を無効にする\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)