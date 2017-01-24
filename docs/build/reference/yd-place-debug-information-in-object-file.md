---
title: "/Yd (デバッグ情報のオブジェクト ファイルへの取り込み) | Microsoft Docs"
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
  - "/yd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Yd コンパイラ オプション [C++]"
  - "デバッグ [C++], デバッグ情報ファイル"
  - "Yd コンパイラ オプション [C++]"
  - "-Yd コンパイラ オプション [C++]"
ms.assetid: c5a699fe-65ce-461e-964c-7f5eb2a8320a
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Yd (デバッグ情報のオブジェクト ファイルへの取り込み)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/Yc](../../build/reference/yc-create-precompiled-header-file.md) オプションおよび [\/Z7](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) オプションと共に使用すると、プリコンパイル済みヘッダー \(.pch\) ファイルから生成されたすべてのオブジェクト ファイルに詳細なデバッグ情報が取り込まれます。  使用は推奨されていません。  
  
## 構文  
  
```  
/Yd  
```  
  
## 解説  
 **\/Yd** は使用されていません。[!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] では、1 つの .pdb ファイルに対する複数オブジェクトの書き込みをサポートするようになりました。代わりに **\/Zi** を使用してください。  詳細については、「[Deprecated Compiler Options in Visual C\+\+ 2005](http://msdn.microsoft.com/ja-jp/aa59fce3-50b8-4f66-9aeb-ce09a7a84cce)」を参照してください。  
  
 デバッグ情報を含むライブラリを配布する必要がある場合以外は、**\/Z7** オプションと **\/Yd** オプションではなく [\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) オプションを使用してください。  
  
 すべての .obj ファイルに詳細なデバッグ情報を格納する必要があるのは、デバッグ情報を含むライブラリを配布する場合だけです。  デバッグ情報をすべての .obj ファイルに取り込むと、コンパイル速度が低下するうえ、ディスク領域をかなり消費します。  **\/Yd** オプションを指定せずに **\/Yc** オプションと **\/Z7** オプションを指定すると、.pch ファイルから生成された最初の .obj ファイルだけに共通のデバッグ情報が取り込まれます。  .pch ファイルから生成された以降の .obj ファイルには、デバッグ情報の代わりにデバッグ情報に対するクロス リファレンスが挿入されます。  同一の .pch ファイルから生成された .obj ファイルの数に関係なく、共通デバッグ情報は単一の .obj ファイルにしか保存されません。  
  
 このように \/Yd オプションを省略すると、ビルド時間を短縮でき、ディスク容量を節約できます。ただし、ごく小さな変更があっても、共通デバッグ情報を取り込んでいる .obj ファイルにはリビルドが必要です。  この場合、その .obj ファイルへのクロス リファレンスを含むすべての .obj ファイルをリビルドする必要があります。  また、1 つの共通 .pch ファイルが複数のプロジェクト間で共有されている場合は、同じ .obj ファイルへのクロス リファレンスが難しくなります。  
  
 プリコンパイル済みヘッダーの詳細については、以下のトピックを参照してください。  
  
-   [\/Y \(プリコンパイル済みヘッダー\)](../../build/reference/y-precompiled-headers.md)  
  
-   [プリコンパイル済みヘッダー ファイルの作成](../../build/reference/creating-precompiled-header-files.md)  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにコンパイラ オプションを入力します。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 例  
 次の **\#include** ステートメントを含む 2 つのベース ファイル F.cpp と G.cpp を想定します。  
  
```  
#include "windows.h"  
#include "etc.h"  
```  
  
 次のコマンドは、プリコンパイル済みヘッダー ファイル ETC.pch とオブジェクト ファイル F.obj を作成します。  
  
```  
CL /YcETC.H /Z7 F.CPP  
```  
  
 オブジェクト ファイル F.obj には、WINDOWS.h と ETC.h \(およびこれらのファイルにインクルードされるほかのヘッダー ファイル\) の型情報とシンボル情報が挿入されます。  これで、プリコンパイル済みヘッダー ETC.pch を使用して、ソース ファイル G.cpp をコンパイルできます。  
  
```  
CL /YuETC.H /Z7 G.CPP  
```  
  
 オブジェクト ファイル G.obj にはプリコンパイル済みヘッダーのデバッグ情報が挿入されず、単に F.obj ファイルでその情報を参照します。  したがって、F.obj とリンクすることが必要です。  
  
 プリコンパイル済みヘッダーが **\/Z7** でコンパイルされていなくても、後で行う **\/Z7** を指定したコンパイルで、引き続きそのヘッダーを使用できます。  ただし、デバッグ情報は現在のオブジェクト ファイルに取り込まれます。また、デバッガーがプリコンパイル済みヘッダーに定義された関数と型のローカル シンボルを使用できなくなります。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)