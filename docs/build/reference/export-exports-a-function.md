---
title: "/EXPORT (関数のエクスポート) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.ExportFunctions"
  - "/export"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/EXPORT リンカー オプション"
  - "EXPORT リンカー オプション"
  - "-EXPORT リンカー オプション"
ms.assetid: 0920fb44-a472-4091-a8e6-73051f494ca0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /EXPORT (関数のエクスポート)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/EXPORT:entryname[,@ordinal[,NONAME]][,DATA]  
```  
  
## 解説  
 このオプションは、プログラムから関数をエクスポートして、ほかのプログラムがその関数を呼び出すことができるようにします。  また、データもエクスポートできます。  通常、エクスポートは DLL ファイルで定義されています。  
  
 *entryname* は、呼び出し側のプログラムが使用する関数またはデータ項目の名前です。  引数 `ordinal` には、エクスポート テーブルのインデックスとして 1 ～ 65,535 の値を指定します。`ordinal` でインデックスを指定しないと、LIB によって自動的に割り当てられます。  **NONAME** キーワードを指定すると、*entryname* を使用せずに、指定されたインデックスだけで関数がエクスポートされます。  
  
 **DATA** キーワードは、エクスポートされた項目がデータ項目であることを示します。  クライアント プログラムにおいて、このデータ項目は **extern \_\_declspec\(dllimport\)** を使って宣言する必要があります。  
  
 定義をエクスポートするには、次の 3 とおりの方法 \(推奨順\) があります。  
  
1.  ソース コードでキーワード [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) を使う。  
  
2.  .def ファイルで [EXPORTS](../Topic/EXPORTS.md) ステートメントを使う。  
  
3.  LINK コマンドで、\/EXPORT 指定を使う。  
  
 同じプログラムでこの 3 つの方法すべてを使用できます。  エクスポートを含むプログラムを LINK でビルドすると、インポート ライブラリも同時に作成されます。ただし、ビルドで .exp ファイルが使用されている場合は除きます。  
  
 LINK は、装飾された形式の識別子を使用します。  .obj ファイルの作成時に、コンパイラが識別子を装飾します。  *entryname* が装飾されない形式 \(ソース コードでの形式と同じ\) でリンカーに渡されると、LINK は該当する名前を探します。  一致する名前が 2 つ以上見つかると、エラー メッセージが表示されます。  リンカーに対して装飾形式で識別子を指定する必要がある場合は、[DUMPBIN](../../build/reference/dumpbin-reference.md) ツールを使って[装飾名](../Topic/Decorated%20Names.md)を得ます。  
  
> [!NOTE]
>  `__cdecl` または `__stdcall` として宣言されている C 言語の識別子は、装飾形式で指定しないでください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  **\[コマンド ライン\]** プロパティ ページをクリックします。  
  
4.  **\[追加のオプション\]** ボックスにオプションを入力します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)