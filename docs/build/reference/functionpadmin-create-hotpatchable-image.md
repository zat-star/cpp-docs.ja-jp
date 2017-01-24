---
title: "/FUNCTIONPADMIN (ホットパッチ可能なイメージの作成) | Microsoft Docs"
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
  - "/functionpadmin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FUNCTIONPADMIN リンカー オプション"
  - "-FUNCTIONPADMIN リンカー オプション"
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FUNCTIONPADMIN (ホットパッチ可能なイメージの作成)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

イメージをホットパッチできるようにします。  
  
## 構文  
  
```  
/FUNCTIONPADMIN[:space]  
```  
  
## 解説  
 指定項目  
  
 `space` \(省略可能\)  
 各関数の先頭で、5 つ追加する、埋め込みの量 Itanium Processor Family 用にビルドされた 6、または 16 の埋め込みの。x86 イメージでは 5 バイト、x64 イメージでは 6 バイト、およびイメージは各関数の先頭に埋め込みに 16 バイトが必要です。  
  
 既定では、イメージが置かれているコンピューターの種類に従って、適切な大きさの領域がイメージに追加されます。  
  
 リンカーがホットパッチ可能なイメージを生成するためには、.obj ファイルが [\/hotpatch \(ホットパッチ可能なイメージの作成\)](../../build/reference/hotpatch-create-hotpatchable-image.md) でコンパイルされていることが必要です。  
  
 イメージをコンパイルして単一の cl.exe 呼び出しにリンクすると、**\/hotpatch** は暗黙に **\/functionpadmin** を指定します。  
  
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