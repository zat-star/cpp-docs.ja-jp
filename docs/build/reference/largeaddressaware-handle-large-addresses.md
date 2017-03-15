---
title: "/LARGEADDRESSAWARE (大きいアドレスの処理) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.LargeAddressAware"
  - "/largeaddressaware"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LARGEADDRESSAWARE リンカー オプション"
  - "LARGEADDRESSAWARE リンカー オプション"
  - "-LARGEADDRESSAWARE リンカー オプション"
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# /LARGEADDRESSAWARE (大きいアドレスの処理)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/LARGEADDRESSAWARE[:NO]  
```  
  
## 解説  
 \/LARGEADDRESSAWARE オプションは、アプリケーションが 2 GB を超えるアドレスを処理できることをリンカーに知らせます。  64 ビット コンパイラでは、このオプションは既定で有効になっています。  32 ビット コンパイラでは、リンカーのコマンド ラインに \/LARGEADDRESSAWARE が指定されていない場合に、 \/LARGEADDRESSAWARE:NO が有効になります。  
  
 \/LARGEADDRESSAWARE オプションを指定してアプリケーションをリンクした場合は、DUMPBIN [\/HEADERS](../../build/reference/headers.md) でその情報が表示されます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[システム\] プロパティ ページをクリックします。  
  
4.  \[大きいサイズのアドレス\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)