---
title: "/FS (同期 PDB 書き込みの強制) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/FS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "-FS コンパイラ オプション [C++]"
  - "/FS コンパイラ オプション [C++]"
ms.assetid: b2caaffe-f6e1-4963-b068-648f06b105e0
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# /FS (同期 PDB 書き込みの強制)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

[\/Zi](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) または [\/ZI](../Topic/-Z7,%20-Zi,%20-ZI%20\(Debug%20Information%20Format\).md) を指定して作成したプログラム データベース \(PDB\) ファイルへの書き込みを MSPDBSRV.EXE によりシリアル化します。  
  
## 構文  
  
```  
/FS  
```  
  
## 解説  
 既定では、**\/Zi** または **\/ZI** を指定すると、コンパイル時、型情報とシンボリック デバッグ情報を書き込むために PDB ファイルがロックされます。  これにより、型の数が多い場合、コンパイル時に型情報の生成にかかる時間が大幅に短くなることがあります。  ウイルス対策プログラムなどの別のプロセスによって PDB ファイルが一時的にロックされている場合、コンパイラによる書き込みは失敗し、重大なエラーが発生することがあります。  この問題は、cl.exe の複数のコピーが同じ PDB ファイルにアクセスするときにも発生することがあります。たとえば、ソリューションで個別のプロジェクトが同じ中間ディレクトリまたは出力ディレクトリを使用する場合や、並列ビルドが有効になっている場合です。  **\/FS** コンパイラ オプションを指定すると、コンパイラ時に PDB ファイルはロックされず、このファイルへの書き込みは MSPDBSRV.EXE によりシリアル化されます。  これにより、ビルド時間が大幅に長くなることがあります。cl.exe の複数のインスタンスが PDB ファイルに同時にアクセスするときに発生する可能性があるすべてのエラーを防止できないこともあります。  個別のプロジェクトによりそれぞれ別々の中間ディレクトリと出力ディレクトリに書き込まれるように、または、他のプロジェクトに依存するいずれかのプロジェクトでプロジェクトのビルドがシリアル化されるように、ソリューションを変更することをお勧めします。  
  
 [\/MP](../../build/reference/mp-build-with-multiple-processes.md) オプションは指定すると、既定で **\/FS** が有効になります。  
  
### Visual Studio 開発環境でこのコンパイラ オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[C\/C\+\+\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  `/FS` が含まれるように "**追加オプション**" プロパティを変更し、**\[OK\]** をクリックします。  
  
### このコンパイラ オプションをコードから設定するには  
  
-   <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A> を参照してください。  
  
## 参照  
 [コンパイラ オプション](../../build/reference/compiler-options.md)   
 [コンパイラ オプションの設定](../Topic/Setting%20Compiler%20Options.md)