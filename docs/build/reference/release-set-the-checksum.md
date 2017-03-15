---
title: "/RELEASE (チェックサムの設定) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/release"
  - "VC.Project.VCLinkerTool.SetChecksum"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/RELEASE リンカー オプション"
  - "チェックサムの設定"
  - "RELEASE リンカー オプション"
  - "-RELEASE リンカー オプション"
ms.assetid: 93bcadf4-29ac-4824-914b-6997e3751d22
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# /RELEASE (チェックサムの設定)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/RELEASE  
```  
  
## 解説  
 \/RELEASE オプションは、.exe ファイルのヘッダーにチェックサムを設定します。  
  
 オペレーティング システムでは、デバイス ドライバーに対してチェックサムを必要とします。  リリースするデバイス ドライバーには、将来のオペレーティング システムとの互換性を保つためにチェックサムを設定してください。  
  
 [\/SUBSYSTEM:NATIVE](../../build/reference/subsystem-specify-subsystem.md) オプションを指定すると、既定では、\/RELEASE オプションが設定されます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[Visual C\+\+ プロジェクトのプロパティの設定](../../ide/working-with-project-properties.md)」を参照してください。  
  
2.  \[リンカー\] フォルダーをクリックします。  
  
3.  \[詳細\] プロパティ ページをクリックします。  
  
4.  \[チェックサムの設定\] プロパティを変更します。  
  
### このリンカーをコードから設定するには  
  
-   「<xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SetChecksum%2A>」を参照してください。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)