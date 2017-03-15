---
title: "/Os、/Ot (実行可能ファイルのサイズの優先、実行速度の優先) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCCLWCECompilerTool.FavorSizeOrSpeed"
  - "/os"
  - "VC.Project.VCCLCompilerTool.FavorSizeOrSpeed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Os コンパイラ オプション [C++]"
  - "/Ot コンパイラ オプション [C++]"
  - "高速コード"
  - "優先 (実行速度を) コンパイラ オプション [C++]"
  - "優先 (実行可能ファイルのサイズを) コンパイラ オプション [C++]"
  - "Os コンパイラ オプション [C++]"
  - "-Os コンパイラ オプション [C++]"
  - "Ot コンパイラ オプション [C++]"
  - "-Ot コンパイラ オプション [C++]"
  - "小さいマシン語コード"
ms.assetid: 9a340806-fa15-4308-892c-355d83cac0f2
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /Os、/Ot (実行可能ファイルのサイズの優先、実行速度の優先)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

EXE および DLL のサイズを最小または最大にします。  
  
## 構文  
  
```  
/Os  
/Ot  
```  
  
## 解説  
 **\/Os** \(実行可能ファイルのサイズの優先\) は、実行速度よりもサイズを優先させて、EXE および DLL のサイズを最小化します。  C や C\+\+ のソースの内容を機能的に同等でサイズの小さいマシン語コードに置き換えます。  ただし、実行速度を高速化した結果、ファイル サイズが大きくなる場合もあります。  **\/Os** と **\/Ot** では、そのいずれかを優先させることができます。  
  
 **\/Ot** \(実行速度の優先\) は、サイズよりも実行速度を優先して、EXE や DLL の実行速度を最高速にします。これは、既定の設定です。C や C\+\+ のソースの内容を機能的に同等でサイズの小さいマシン語コードに置き換えます。  ただし、実行速度を高速化した結果、ファイル サイズが大きくなる場合もあります。  \/Ot オプションは、[\/02](../../build/reference/o1-o2-minimize-size-maximize-speed.md) \(実行速度\) オプションによって暗黙的に指定されます。  **\/O2** オプションでは、複数のオプションを組み合わせて高速なコードを生成します。  
  
 **\/Os** または **\/Ot** を使用する場合、コードを最適化するために [\/Og](../../build/reference/og-global-optimizations.md) も指定する必要があります。  
  
> [!NOTE]
>  プロファイリングのテスト実行から収集される情報により、**\/Ob**、**\/Os**、または **\/Ot** を指定する場合に有効な最適化がオーバーライドされます。  詳細については、「[ガイド付き最適化のプロファイル](../../build/reference/profile-guided-optimizations.md)」を参照してください。  
  
 **x86 固有の仕様→**  
  
 次のコードは、**\/Os** \(実行可能ファイルのサイズの優先\) と **\/Ot** \(実行速度の優先\) の各オプションの違いを示します。  
  
> [!NOTE]
>  次に、**\/Os** または **\/Ot** を使用した場合に予想される動作を説明します。  ただし、コンパイラの動作はリリースごとに異なるため、次のコードの最適化の結果は異なる場合があります。  
  
```  
/* differ.c  
  This program implements a multiplication operator  
  Compile with /Os to implement multiply explicitly as multiply.  
  Compile with /Ot to implement as a series of shift and LEA instructions.  
*/  
int differ(int x)  
{  
    return x * 71;  
}  
```  
  
 次のマシン語コードのように、**\/Os** \(実行可能ファイルのサイズの優先\) で DIFFER.c をコンパイルすると、return ステートメントの乗算式が明示的に乗算として実装され、サイズは小さいが低速のコードが生成されます。  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
imul   eax, 71                  ; 00000047H  
```  
  
 これに対し、**\/Ot** \(実行速度の優先\) で DIFFER.c をコンパイルすると、return ステートメントの乗算式が一連のシフト命令および `LEA` 命令として実装され、高速だがサイズの大きいコードが生成されます。  
  
```  
mov    eax, DWORD PTR _x$[ebp]  
mov    ecx, eax  
shl    eax, 3  
lea    eax, DWORD PTR [eax+eax*8]  
sub    eax, ecx  
```  
  
 **← x86 固有の仕様**  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[最適化\]** プロパティ ページをクリックします。  
  
4.  **\[速度またはサイズを優先\]** プロパティを変更します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.FavorSizeOrSpeed%2A>」を参照してください。  
  
## 参照  
 [\/O オプション \(コードの最適化\)](../../build/reference/o-options-optimize-code.md)   
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)