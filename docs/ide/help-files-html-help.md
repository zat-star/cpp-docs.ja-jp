---
title: "ヘルプ ファイル (HTML ヘルプ) | Microsoft Docs"
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
  - "ファイルの種類 [C++], HTML ヘルプ ファイル"
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ヘルプ ファイル (HTML ヘルプ)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC アプリケーション ウィザードの [&#91;高度な機能&#93;](../mfc/reference/advanced-features-mfc-application-wizard.md) ページで \[コンテキスト ヘルプ\] チェック ボックスをオンにしてから \[HTML ヘルプ フォーマット\] を選択して、アプリケーションに HTML ヘルプ形式のヘルプ サポートを追加すると、以下のファイルが作成されます。  
  
|ファイル名|ディレクトリの場所|ソリューション エクスプローラーでの場所|Description|  
|-----------|---------------|--------------------------|-----------------|  
|*Projname*.hhp|*Projname*\\hlp|HTML ヘルプ ファイル|ヘルプ プロジェクト ファイル。  このファイルには、ヘルプ ファイルを .hxs ファイルまたは .chm ファイルにコンパイルするために必要なデータが含まれます。|  
|*Projname*.hhk|*Projname*\\hlp|HTML ヘルプ ファイル|ヘルプ トピックのキーワードが含まれるファイル。|  
|*Projname*.hhc|*Projname*\\hlp|HTML ヘルプ ファイル|ヘルプ プロジェクトの目次が含まれるファイル。|  
|Makehtmlhelp.bat|*Projname*|ソース ファイル|プロジェクトのコンパイル時に、ヘルプ プロジェクトのビルドに使用されるファイル。|  
|Afxcore.htm|*Projname*\\hlp|HTML ヘルプ トピック|MFC の標準コマンドと画面オブジェクト用の標準ヘルプ トピックが含まれるファイル。  このファイルには、独自のヘルプ トピックを追加できます。|  
|Afxprint.htm|*Projname*\\hlp|HTML ヘルプ トピック|印刷コマンド用のヘルプ トピックが含まれるファイル。|  
|\*.jpg、\*.gif|*Projname*\\hlp\\Images|リソース ファイル|生成されたさまざまなヘルプ ファイル トピック用のイメージが含まれるファイル。|  
  
## 参照  
 [Visual C\+\+ プロジェクトに対して作成されるファイルの種類](../ide/file-types-created-for-visual-cpp-projects.md)