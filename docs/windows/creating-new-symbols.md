---
title: "Creating New Symbols | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.creating"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "New Symbol dialog box"
  - "symbols, creating"
ms.assetid: 35168d31-3af6-4ecd-9362-3707d47b53f3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating New Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

新しいプロジェクトを開始するときは、必要なシンボル名を、シンボル名を割り当てるリソースを作成する前に決めておくと便利です。  
  
### \[リソース シンボル\] ダイアログ ボックスを使用して新しいシンボルを作成するには  
  
1.  [&#91;リソース シンボル&#93; ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)で、**\[新規\]** を選択します。  
  
2.  **\[名前\]** ボックスに、シンボル名を入力します。  
  
3.  割り当てられたシンボル値を受け入れます。  
  
     または  
  
     **\[値\]** ボックスに、新しい値を入力します。  
  
4.  **\[OK\]** をクリックして新しいシンボルをシンボルの一覧に追加します。  
  
 既に存在するシンボルの名前を入力すると、その名前のシンボルが既に定義されていることを示すメッセージ ボックスが表示されます。  複数の同じ名前のシンボルを定義することはできませんが、同じ数値を持つ異なるシンボルを定義することができます。  詳細については、「[シンボル名の制限](../windows/symbol-name-restrictions.md)」および「[シンボル値の制限](../Topic/Symbol%20Value%20Restrictions.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 必要条件  
  
 Win32  
  
## 参照  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)