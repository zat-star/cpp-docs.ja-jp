---
title: "/DELAY (遅延読み込みのインポート設定) | Microsoft Docs"
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
  - "/delay"
  - "VC.Project.VCLinkerTool.DelayNoBind"
  - "VC.Project.VCLinkerTool.SupportUnloadOfDelayLoadedDLL"
  - "VC.Project.VCLinkerTool.DelayUnload"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DELAY リンカー オプション"
  - "DELAY リンカー オプション"
  - "-DELAY リンカー オプション"
  - "遅延読み込み (DLL を), /DELAY オプション"
ms.assetid: 9334b332-cc58-4dae-b10f-a4c75972d50c
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DELAY (遅延読み込みのインポート設定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DELAY:UNLOAD  
/DELAY:NOBIND  
```  
  
## 解説  
 \/DELAY オプションは、DLL の[遅延読み込み](../../build/reference/linker-support-for-delay-loaded-dlls.md)を制御します。  
  
-   UNLOAD 修飾子は、DLL の明示的なアンロードをサポートするように遅延読み込みヘルパー関数に指定します。  インポート アドレス テーブル \(IAT\) は元の形式にリセットされ、IAT のポインターは無効になって上書きされます。  
  
     UNLOAD を選択しない場合、[FUnloadDelayLoadedDLL](../../build/reference/explicitly-unloading-a-delay-loaded-dll.md) の呼び出しは失敗します。  
  
-   NOBIND 修飾子は、バインドできる IAT を最終イメージに含めないようにリンカーに指定します。  既定では、遅延読み込みされる DLL に対してバインドできる IAT が作成されます。  生成されるイメージは静的にバインドできません。  \(バインドできる IAT を含むイメージは、実行前に静的にバインドできます\)。「[\/BIND](../../build/reference/bind.md)」を参照してください。  
  
     DLL がバインドされた場合、ヘルパー関数は、参照される各インポートに対して [GetProcAddress](http://msdn.microsoft.com/library/windows/desktop/ms683212.aspx) を呼び出す代わりに、バインドされた情報を使用しようとします。  タイムスタンプまたは優先アドレスが、読み込まれた DLL のものと一致しない場合、ヘルパー関数はバインドされた IAT は古いと見なし、バインドされた IAT が存在しないかのように続行します。  
  
     NOBIND を使用すると、プログラム イメージは大きくなりますが、DLL の読み込み時間は速くなります。  DLL をバインドしない場合は、NOBIND を使用すると、バインドされた IAT は生成されません。  
  
 DLL の遅延読み込みを指定するには、[\/DELAYLOAD](../../build/reference/delayload-delay-load-import.md) オプションを使用します。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[構成プロパティ\]**、**\[リンカー\]** を展開し、**\[詳細\]** を選択します。  
  
3.  **\[DLL の遅延読み込み\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.DelayLoadDLLs%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)