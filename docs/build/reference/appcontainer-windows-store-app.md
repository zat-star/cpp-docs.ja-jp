---
title: "/APPCONTAINER (Windows ストア アプリ) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9a432db5-7640-460b-ab18-6f61fa7daf6f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /APPCONTAINER (Windows ストア アプリ)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

リンカーがアプリ コンテナーで実行される必要がある実行可能イメージを生成するかどうかを指定します。  
  
## 構文  
  
```  
/APPCONTAINER[:NO]  
```  
  
## 解説  
 既定では、\/APPCONTAINER は無効になっています。  
  
 このオプションは、実行可能ファイルを変更し、appcontainer プロセス分離環境でアプリが実行される必要があるかどうかを示します。  appcontainer 環境で実行される必要があるアプリに対し、\/APPCONTAINER を指定します \([!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] アプリなど\) \(テンプレートから [!INCLUDE[win8_appstore_long](../../build/reference/includes/win8_appstore_long_md.md)] アプリを作成するときに、オプションは Visual Studio で自動的に設定されます\)。デスクトップ アプリケーションでは、\/APPCONTAINER:NO を指定するか、オプションを省略します。  
  
 \/APPCONTAINER オプションは [!INCLUDE[win8](../../build/includes/win8_md.md)] で導入されました。  
  
### このリンカー オプションを Visual Studio で設定するには  
  
1.  プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスを開きます。  詳細については、「[方法 : プロジェクト プロパティ ページを開く](../../misc/how-to-open-project-property-pages.md)」を参照してください。  
  
2.  **\[構成プロパティ\]** ノードを展開します。  
  
3.  **\[リンカー\]** ノードを展開します。  
  
4.  **\[コマンド ライン\]** プロパティ ページを選択します。  
  
5.  **\[追加オプション\]** に、`/APPCONTAINER` または `/APPCONTAINER:NO` を入力します。  
  
## 参照  
 [リンカー オプションの設定](../../build/reference/setting-linker-options.md)   
 [リンカー オプション](../../build/reference/linker-options.md)