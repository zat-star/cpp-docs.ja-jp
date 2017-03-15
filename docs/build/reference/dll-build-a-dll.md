---
title: "/DLL (DLL のビルド) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/dll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DLL リンカー オプション [C++]"
  - "-DLL リンカー オプション"
  - "DLL リンカー オプション [C++]"
  - "DLL [C++], ビルド"
  - "エクスポート (DLL を) [C++], 指定 (エクスポートを)"
ms.assetid: c7685aec-31d0-490f-9503-fb5171a23609
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /DLL (DLL のビルド)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DLL  
```  
  
## 解説  
 \/DLL オプションは、DLL ファイルを主な出力ファイルとしてビルドします。  通常、DLL ファイルには、ほかのプログラムから使用できるエクスポートが取り込まれています。  エクスポートを指定するには、次の 3 とおりの方法 \(推奨順\) があります。  
  
1.  ソース コードでキーワード [\_\_declspec\(dllexport\)](../../cpp/dllexport-dllimport.md) を使う。  
  
2.  .def ファイルで [EXPORTS](../Topic/EXPORTS.md) ステートメントを使う。  
  
3.  LINK コマンドで、[\/EXPORT](../../build/reference/export-exports-a-function.md) 指定を使う。  
  
 1 つのプログラムで複数の方法を使用できます。  
  
 別の方法としては、モジュール定義ステートメント **LIBRARY** を使って DLL をビルドできます。  \/BASE オプションと \/DLL オプションを併用すると、**LIBRARY** ステートメントと同じ結果になります。  
  
 開発環境では、このオプションを指定しないでください。このオプションはコマンド ライン専用です。  このオプションは、アプリケーション ウィザードを使って DLL プロジェクトを作成するときに設定します。  
  
 .dll をビルドする前の予備ステップでインポート ライブラリを作成する場合は、.dll をビルドするときに、インポート ライブラリのビルド時に渡したものと同じオブジェクト ファイル セットを渡す必要があることに注意してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[構成プロパティ\] フォルダーをクリックします。  
  
3.  \[全般\] プロパティ ページをクリックします。  
  
4.  \[構成の種類\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCPropertySheet.ConfigurationType%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)