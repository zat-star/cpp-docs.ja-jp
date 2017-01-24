---
title: "MFC における Unicode | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "文字列 [C++], Unicode"
  - "Unicode [C++], 有効化"
  - "Unicode [C++], MFC"
  - "ワイド文字, エンコーディング"
  - "ワイド文字, Unicode"
ms.assetid: 1002004b-4113-4380-bf63-e1570934b793
caps.latest.revision: 13
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC における Unicode
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC は、Windows NT、Windows 2000、Windows XP の各プラットフォームのワイド文字をエンコードするための Unicode 規格をサポートします。  Unicode アプリケーションは Windows 98 プラットフォームで実行できません。  
  
 Unicode バージョンの MFC ライブラリについて説明します。:  
  
### スタティック リンク ライブラリ  
  
|リリース|デバッグ|説明|  
|----------|----------|--------|  
|UAFXCW.lib、.pdb|UAFXCWD.lib、.pdb|Unicode MFC のスタティック リンク ライブラリ|  
  
### ダイナミック リンク ライブラリ \(DLL\)  
  
|リリース|デバッグ|説明|  
|----------|----------|--------|  
|MFC100U.lib、.dbg の def、.dll、.map、.pdb、.prf|MFC100UD.lib、.def、.dll、.map、.pdb|Unicode MFC インポート ライブラリ ファイル \(拡張子の詳細については、次の説明を参照してください\)。|  
|MFCS100U.lib、.pdb|MFCS100UD.lib、.pdb|アプリケーションや DLL に静的にリンクする必要のある Unicode MFC インポートを含むライブラリ コード|  
  
 **ファイルの種類**  
  
-   インポート ライブラリ \(.lib\) ファイルに拡張できます。  
  
-   ダイナミック リンク ライブラリ \(.dll\) ファイルに拡張できます。  
  
-   モジュール定義 \(.def\) ファイルは、.exe または .dll を定義するためのステートメントを含むテキスト ファイルです。  
  
-   マップ \(.map\) ファイルはリンカーが使用する情報を含むテキスト ファイルがプログラムをリンクするとき。  
  
-   ライブラリ ファイル \(.lib\) は DLL バージョンの MFC とともに使用されます。  これらのファイルは、アプリケーションまたは DLL に静的にリンクするコードが含まれています。  
  
-   プログラム データベース \(.pdb\) ファイルがデバッグおよびプロジェクトの状態情報を格納します。  
  
-   \(デバッグ\) .dbg ファイルは、Visual C\+\+ のデバッガーを使用する CodeView\) を COFF \(FPO\) が含まれます。  
  
 名前付け規則の詳細については、「[ライブラリの名前付け規則](../Topic/Library%20Naming%20Conventions.md)」を参照してください。  
  
 MFC の Unicode の使用の詳細については、「[文字列: Unicode とマルチバイト文字セット \(MBCS\) のサポート](../atl-mfc-shared/unicode-and-multibyte-character-set-mbcs-support.md)」を参照してください。  
  
## 参照  
 [概念](../mfc/mfc-concepts.md)   
 [MFC の一般的なトピック](../mfc/general-mfc-topics.md)