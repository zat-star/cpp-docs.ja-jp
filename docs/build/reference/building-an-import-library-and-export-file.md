---
title: "インポート ライブラリとエクスポート ファイルのビルド | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLibrarianTool.ModuleDefinitionFile"
  - "VC.Project.VCLibrarianTool.ExportNamedFunctions"
  - "VC.Project.VCLibrarianTool.GenerateDebug"
  - "VC.Project.VCLibrarianTool.ForceSymbolReferences"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".lib ファイル"
  - "/DEF ライブラリ マネージャー オプション"
  - "/EXPORT ライブラリ マネージャー オプション"
  - "/INCLUDE ライブラリ マネージャー オプション"
  - "/OUT ライブラリ マネージャー オプション"
  - "DEF ライブラリ マネージャー オプション"
  - "-DEF ライブラリ マネージャー オプション"
  - "EXP ファイル"
  - "EXPORT ライブラリ マネージャー オプション"
  - "-EXPORT ライブラリ マネージャー オプション"
  - "エクスポート (データを)"
  - "エクスポート (データを), エクスポート (.exp) ファイル"
  - "インポート ライブラリ, ビルド"
  - "INCLUDE ライブラリ マネージャー オプション"
  - "-INCLUDE ライブラリ マネージャー オプション"
  - "OUT ライブラリ マネージャー オプション"
  - "-OUT ライブラリ マネージャー オプション"
ms.assetid: 2fe4f30a-1dd6-4b05-84b5-0752e1dee354
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# インポート ライブラリとエクスポート ファイルのビルド
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

インポート ライブラリとエクスポート ファイルをビルドするには、次の構文を使用します。  
  
```  
LIB /DEF[:deffile] [options] [objfiles] [libraries]  
```  
  
 \/DEF を指定すると、LIB コマンドで渡したエクスポートの指定に基づいて、出力ファイルが作成されます。  エクスポートを指定するには、次の 3 とおりの方法 \(推奨順\) があります。  
  
1.  *objfiles* または *libraries* で、**\_\_declspec\(dllexport\)** を定義する。  
  
2.  LIB のコマンド ラインで、\/EXPORT:*name* を指定する。  
  
3.  `deffile` で、**EXPORTS** 文形式で定義する。  
  
 これらの方法は、エクスポートするプログラムをリンクするときのエクスポートの指定方法と同じです。  1 つのプログラムで複数の方法を使用できます。  LIB コマンドでも LINK コマンドと同じように、コマンドの一部 \(複数の *objfiles* や \/EXPORT 指定など\) をコマンド ファイルで指定できます。  
  
 以下は、インポート ライブラリとエクスポート ファイルをビルドするオプションです。  
  
 \/OUT:*import*  
 作成するインポート ライブラリの既定の出力ファイル名を変更します。  \/OUT を指定しないと、既定の出力ファイル名は、LIB コマンドで最初に指定したオブジェクト ファイルまたはライブラリの基本名に拡張子 .lib が付いたものになります。  エクスポート ファイル名は、インポート ライブラリの基本名に拡張子 .exp が付いたものになります。  
  
 \/EXPORT:*entryname*\[\=*internalname*\]\[,@`ordinal`\[,**NONAME**\]\]\[,**DATA**\]  
 プログラムから特定の関数をエクスポートし、ほかのプログラムからそれを呼び出せるようにします。  **DATA** キーワードを使うと、データもエクスポートできます。  通常、エクスポートは DLL ファイルで定義されています。  
  
 *entryname* は、呼び出し側のプログラムが使用する関数またはデータ項目の名前です。  引数 *internalname* に、エクスポート側のプログラム内で認識される関数名を指定することもできます。既定では、*internalname* は *entryname* と同じ名前になります。  引数 `ordinal` には、エクスポート テーブルのインデックスとして 1 ～ 65,535 の値を指定します。`ordinal` でインデックスを指定しないと、LIB によって自動的に割り当てられます。  **NONAME** キーワードを指定すると、*entryname* を使用せずに、指定されたインデックスだけで関数がエクスポートされます。  **DATA** キーワードを使用すると、データだけのオブジェクトをエクスポートできます。  
  
 \/INCLUDE:`symbol`  
 指定されたシンボルをシンボル テーブルに追加します。  このオプションは、通常は取り込まれないライブラリ オブジェクトを追加する場合に使用します。  
  
 .dll をビルドする前の予備ステップでインポート ライブラリを作成する場合は、.dll をビルドするときに、インポート ライブラリのビルド時に渡したものと同じオブジェクト ファイル セットを渡す必要があることに注意してください。  
  
## 参照  
 [インポート ライブラリとエクスポート ファイル](../../build/reference/working-with-import-libraries-and-export-files.md)