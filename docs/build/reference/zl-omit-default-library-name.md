---
title: "/Zl (既定のライブラリ名の省略) | Microsoft Docs"
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
  - "/zi"
  - "VC.Project.VCCLCompilerTool.OmitDefaultLibName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zl コンパイラ オプション [C++]"
  - "既定のライブラリ, 省略 (名前を)"
  - "省略 (既定のライブラリ名を) コンパイラ オプション"
  - "ZI コンパイラ オプション"
  - "-Zl コンパイラ オプション [C++]"
ms.assetid: b27d39d0-44d6-498c-84ae-27c1326fee59
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zl (既定のライブラリ名の省略)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

.obj ファイルから、既定の C ランタイム ライブラリ名を削除します。  既定では、リンカーに正しいライブラリを指示するために、コンパイラによって .obj ファイルにライブラリ名が埋め込まれます。  
  
## 構文  
  
```  
/Zl  
```  
  
## 解説  
 既定のライブラリの詳細については、「[\/MD、\/ML、\/MT、\/LD \(ランタイム ライブラリの使用\)](../../build/reference/md-mt-ld-use-run-time-library.md)」を参照してください。  
  
 **\/Zl** オプションは、ライブラリに格納する予定の .obj ファイルをコンパイルするときに使います。  単一の .obj ファイルでライブラリ名を省略しても節約できるスペースはわずかですが、多数のオブジェクト モジュールから成るライブラリ全体ではかなりのスペースを節約できます。  
  
 これは、高度なオプションです。  このオプションを設定すると、特定の C ランタイム ライブラリのサポートが削除されますが、アプリケーションではそのサポートが要求されている可能性があります。アプリケーションがこのサポートに依存している場合は、リンク時エラーが発生します。  このオプションを使用する場合は、要求されるコンポーネントを何か別の方法で提供する必要があります。  
  
 [\/NODEFAULTLIB \(ライブラリを無視する\)](../../build/reference/nodefaultlib-ignore-libraries.md)を使用します。リンカーは、すべての .obj ファイルでライブラリ参照を無視するように指示します。  
  
 詳細については、「[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)」を参照してください。  
  
 **\/Zl** を指定してコンパイルする場合、`_VC_NODEFAULTLIB` が定義されます。たとえば、次のようになります。  
  
```  
// vc_nodefaultlib.cpp  
// compile with: /Zl  
void Test() {  
   #ifdef _VC_NODEFAULTLIB  
      int i;  
   #endif  
  
   int i;   // C2086  
}  
```  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[詳細\]** プロパティ ページをクリックします。  
  
4.  **\[既定ライブラリ名の省略\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.OmitDefaultLibName%2A>」を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)