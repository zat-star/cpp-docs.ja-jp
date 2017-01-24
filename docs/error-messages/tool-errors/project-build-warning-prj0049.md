---
title: "プロジェクト ビルドの警告 PRJ0049 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PRJ0049"
ms.assetid: 8b38afa1-e080-4efd-ae89-776cfd044413
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# プロジェクト ビルドの警告 PRJ0049
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

参照されたターゲット '\<参照は\>' 必要とし、.NET Framework \<MinFrameworkVersion を\> このプロジェクトのターゲット フレームワークで動作しません  
  
 [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] を使用して作成されたアプリケーションは、対象とする [!INCLUDE[dnprdnshort](../Token/dnprdnshort_md.md)] のバージョンを指定できます。  対象とするバージョンより後の [!INCLUDE[dnprdnshort](../Token/dnprdnshort_md.md)] のバージョンに依存するアセンブリまたはプロジェクトへの参照を追加する場合、コンパイル時にこの警告が出力されます。  
  
### この警告を解決するには  
  
1.  次のいずれかを選択します。  
  
    -   プロジェクトの **\[プロパティ ページ\]** ダイアログ ボックスで、対象とするフレームワークを変更して、参照されるすべてのアセンブリおよびプロジェクトについて最小フレームワーク バージョン以降になるようにします。  詳細については、「[参照の追加](../../ide/adding-references-in-visual-cpp-projects.md)」を参照してください。  
  
    -   対象とするフレームワークより後の最小フレームワーク バージョンであるアセンブリまたはプロジェクトへの参照を削除します。  これらの項目には、プロジェクトの **\[プロパティ ページ\]** で、警告アイコンが付けられます。  
  
## 参照  
 [プロジェクト ビルド エラーと警告 \(PRJxxxx\)](../../error-messages/tool-errors/project-build-errors-and-warnings-prjxxxx.md)