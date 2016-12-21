---
title: "/FIXED (固定ベース アドレス) | Microsoft Docs"
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
  - "/fixed"
  - "VC.Project.VCLinkerTool.FixedBaseAddress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/FIXED リンカー オプション"
  - "FIXED リンカー オプション"
  - "-FIXED リンカー オプション"
  - "指定ベース アドレス (プログラム読み込み用の)"
ms.assetid: 929bba5e-b7d8-40ed-943e-056aa3710fc5
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /FIXED (固定ベース アドレス)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/FIXED[:NO]  
```  
  
## 解説  
 オペレーティング システムに、指定されたベース アドレスにだけプログラムを読み込むように指示します。  指定したベース アドレスが使用できない場合、オペレーティング システムはファイルを読み込みません。  詳細については、「[\/BASE \(ベース アドレス\)](../../build/reference/base-base-address.md)」を参照してください。  
  
 DLL には \/FIXED:NO が既定で使用されます。他のすべての種類のプロジェクトには \/FIXED が既定で使用されます。  
  
 \/FIXED オプションを指定すると、プログラム内に再配置セクションが作成されなくなります。  実行時にオペレーティング システムが指定されたアドレスにプログラムを読み込むことができない場合は、エラー メッセージが表示され、プログラムが読み込まれなくなります。  
  
 \/FIXED:NO を指定すると、プログラム内に再配置セクションが生成されます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーを選択します。  
  
3.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
4.  **\[追加オプション\]** ボックスにオプション名と設定を入力します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)