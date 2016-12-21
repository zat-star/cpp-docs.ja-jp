---
title: "/MACHINE (ターゲット プラットフォームの指定) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.TargetMachine"
  - "/machine"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MACHINE リンカー オプション"
  - "MACHINE リンカー オプション"
  - "-MACHINE リンカー オプション"
  - "マップ ファイル, 作成 (リンカーを)"
  - "ターゲット プラットフォーム"
ms.assetid: 8d41bf4b-7e53-4ab9-9085-d852b08d31c2
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /MACHINE (ターゲット プラットフォームの指定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/MACHINE:{ARM|EBC|X64|X86}  
```  
  
## 解説  
 \/MACHINE オプションは、プログラムのターゲット プラットフォームを指定します。  
  
 通常、\/MACHINE オプションは指定する必要がありません。  LINK では、.obj ファイルからコンピューターの種類を推測するためです。  ただし、環境によっては、LINK がコンピューターの種類を判定できず、[リンカー ツール エラー LNK1113](../../error-messages/tool-errors/linker-tools-error-lnk1113.md) が発生する場合があります。  このようなエラー メッセージが出力された場合は、\/MACHINE オプションを指定してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーをクリックします。  
  
3.  **\[詳細\]** プロパティ ページをクリックします。  
  
4.  **\[対象コンピューター\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TargetMachine%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)