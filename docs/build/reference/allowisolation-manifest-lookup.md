---
title: "/ALLOWISOLATION (マニフェスト検索) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/ALLOWISOLATION"
  - "VC.Project.VCLinkerTool.AllowIsolation"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ALLOWISOLATION リンカー オプション"
  - "-ALLOWISOLATION リンカー オプション"
ms.assetid: 6d41851e-b3c1-4bdf-beaa-031773089d6f
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /ALLOWISOLATION (マニフェスト検索)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

マニフェスト検索の動作を指定します。  
  
## 構文  
  
```  
/ALLOWISOLATION[:NO]  
```  
  
## 解説  
 **\/ALLOWISOLATION:NO** は、マニフェストがないものとして DLL が読み込まれたことを示し、リンカーはこれにより、ヘッダーの省略可能なフィールドである `DllCharacteristics` に `IMAGE_DLLCHARACTERISTICS_NO_ISOLATION` ビットを設定します。  
  
 **\/ALLOWISOLATION** により、オペレーティング システムはマニフェストの検索と読み込みを行います。  
  
 **\/ALLOWISOLATION** が既定値です。  
  
 実行可能ファイルを分離できない場合、Windows ローダーは、新しく作成されるプロセスのアプリケーション マニフェストを検索しません。  マニフェストが実行可能ファイル内に配置 *executable\-name*または名前**.exe.manifest**と実行可能ファイルと同じディレクトリにある場合、新しいプロセスは既定のアクティベーション コンテキストはありません。  
  
 詳細については、「[Manifest Files Reference](http://msdn.microsoft.com/library/aa375632)」を参照してください。  
  
### Visual Studio 開発環境でこのリンカー オプションを設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[マニフェスト ファイル\]** プロパティ ページをクリックします。  
  
5.  **\[分離の許可\]** プロパティを変更します。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)