---
title: "/DRIVER (Windows NT カーネル モード ドライバー) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.driver"
  - "/driver"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/DRIVER リンカー オプション"
  - "DRIVER リンカー オプション"
  - "-DRIVER リンカー オプション"
  - "カーネル モード ドライバー"
ms.assetid: aeee8e28-5d97-40f5-ba16-9f370fe8a1b8
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /DRIVER (Windows NT カーネル モード ドライバー)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/DRIVER[:UPONLY | :WDM]  
```  
  
## 解説  
 \/Driver リンカー オプションは、Windows NT カーネル モード ドライバーをビルドするときに使用します。  
  
 **\/DRIVER:UPONLY** により、出力ヘッダーにユニプロセッサ \(UP\) ドライバーを指定する **IMAGE\_FILE\_UP\_SYSTEM\_ONLY** ビットが追加されます。  マルチプロセッサ \(MP\) システムでは、オペレーティング システムによって、UP ドライバーの読み込みが拒否されます。  
  
 **\/DRIVER:WDM** により、オプションのヘッダーの DllCharacteristics フィールドに **IMAGE\_DLLCHARACTERISTICS\_WDM\_DRIVER** ビットが設定されます。  
  
 **\/DRIVER** が指定されていない場合、リンカーはこれらのビットを設定しません。  
  
 **\/DRIVER** が指定されている場合  
  
-   \/FIXED:NO が有効です \([\/FIXED \(固定ベース アドレス\)](../../build/reference/fixed-fixed-base-address.md)\)。  
  
-   出力ファイルの拡張子は .sys です。  **\/OUT** を使用して、既定のファイル名および拡張子 \([\/OUT \(出力ファイル名\)](../../build/reference/out-output-file-name.md)\) を変更します。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  **\[リンカー\]** フォルダーをクリックします。  
  
3.  **\[システム\]** プロパティ ページをクリックします。  
  
4.  **\[ドライバー\]** プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
1.  「`P:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.driver`」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)