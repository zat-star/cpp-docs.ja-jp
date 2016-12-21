---
title: "/NOLOGO (著作権情報の非表示) (リンカー) | Microsoft Docs"
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
  - "VC.Project.VCLinkerTool.SuppressStartupBanner"
  - "/nologo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/NOLOGO リンカー オプション"
  - "著作権情報, 非表示 (著作権情報を)"
  - "著作権メッセージ"
  - "NOLOGO リンカー オプション"
  - "-NOLOGO リンカー オプション"
  - "著作権情報の非表示 リンカー オプション"
  - "バージョン番号, 防止 (リンカー表示を)"
ms.assetid: 3b20dddd-eca6-4545-a331-9f70bf720197
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /NOLOGO (著作権情報の非表示) (リンカー)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/NOLOGO  
```  
  
## 解説  
 \/NOLOGO オプションを指定すると、著作権のメッセージとバージョン番号が表示されなくなります。  
  
 このオプションでは、コマンド ファイルのエコーも行われません。  詳細については、「[LINK コマンド ファイル](../../build/reference/link-command-files.md)」を参照してください。  
  
 既定では、著作権メッセージなどの情報はアウトプット ウィンドウに送られます。  コマンド ラインで指定した場合は標準出力に送られるため、ファイルにリダイレクトできます。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  このオプションは、コマンド ラインだけで使用できます。  
  
### このリンカーをコードから設定するには  
  
1.  このリンカー オプションをプログラムによって変更することはできません。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)