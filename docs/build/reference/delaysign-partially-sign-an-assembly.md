---
title: "/DELAYSIGN (アセンブリの部分署名) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delaysign"
  - "VC.Project.VCLinkerTool.DelaySign"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAYSIGN リンカー オプション"
  - "DELAYSIGN リンカー オプション"
  - "-DELAYSIGN リンカー オプション"
ms.assetid: 15244d30-3ecb-492f-a408-ffe81f38de20
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# /DELAYSIGN (アセンブリの部分署名)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAYSIGN[:NO]  
```  
  
## 解説  
 指定項目  
  
 NO  
 アセンブリに部分署名できないことを指定します。  
  
## 解説  
 **\/DELAYSIGN** は、アセンブリに公開キーを挿入する場合にだけ使用します。  既定値は、**\/DELAYSIGN:NO** です。  
  
 **\/DELAYSIGN** オプションは、[\/KEYFILE](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) または [\/KEYCONTAINER](../../build/reference/keycontainer-specify-a-key-container-to-sign-an-assembly.md) と組み合わせて使用しない限り効果がありません。  
  
 完全署名されたアセンブリを要求すると、コンパイラはマニフェスト \(アセンブリ メタデータ\) を含むファイルをハッシュし、そのハッシュに秘密キーで署名します。  結果として得られるデジタル署名は、マニフェストを含むファイルに格納されます。  アセンブリが遅延署名された場合、リンカーは署名の計算や格納を行いませんが、署名を後で追加できるようにファイルの領域を予約します。  
  
 たとえば、**\/DELAYSIGN** を使用すると、テスト時にはグローバル キャッシュにアセンブリを挿入できます。  テスト後に、アセンブリに秘密キーを追加することにより、そのアセンブリに完全署名できます。  
  
 アセンブリに対する署名の詳細については、「[厳密名アセンブリ \(アセンブリ署名\)](../../dotnet/strong-name-assemblies-assembly-signing-cpp-cli.md)」および「[アセンブリへの遅延署名](../Topic/Delay%20Signing%20an%20Assembly.md)」を参照してください。  
  
 このほかにも、次のようなリンカー オプションがアセンブリの生成に影響します。  
  
-   [\/ASSEMBLYDEBUG \(DebuggableAttribute の追加\)](../Topic/-ASSEMBLYDEBUG%20\(Add%20DebuggableAttribute\).md)  
  
-   [\/ASSEMBLYLINKRESOURCE](../../build/reference/assemblylinkresource-link-to-dotnet-framework-resource.md)  
  
-   [\/ASSEMBLYMODULE](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md)  
  
-   [\/ASSEMBLYRESOURCE](../../build/reference/assemblyresource-embed-a-managed-resource.md)  
  
-   [\/NOASSEMBLY](../../build/reference/noassembly-create-a-msil-module.md)  
  
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