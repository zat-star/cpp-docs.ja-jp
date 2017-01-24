---
title: "[リソース シンボル] ダイアログ ボックス | Microsoft Docs"
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
  - "vc.editors.resourcesymbols"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "[新規シンボル] ダイアログ ボックス"
  - "[リソース シンボル] ダイアログ ボックス"
  - "[シンボルの変更] ダイアログ ボックス"
ms.assetid: 9706cde3-1f48-4fcd-bedb-2b03b455e3c1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# [リソース シンボル] ダイアログ ボックス
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**\[リソース シンボル\]** ダイアログ ボックスでは、新しいリソース シンボルの追加、表示されるシンボルの変更、またはソース コード内のシンボルが使用されている場所へのスキップを実行できます。  
  
 **名前**  
 シンボルの名前を表示します。  詳細については、「[シンボル名の制限](../windows/symbol-name-restrictions.md)」を参照してください。  
  
 **値**  
 シンボルの数値を表示します。  詳細については、「[シンボル値の制限](../Topic/Symbol%20Value%20Restrictions.md)」を参照してください。  
  
 **使用中**  
 シンボルが 1 つ以上のリソースで使用されることを指定する場合にオンにします。  リソースの一覧が \[次のリソースで使用\] ボックスに表示されます。  
  
 **読み取り専用のシンボルを表示**  
 読み取り専用のリソースを表示する場合にオンにします。  既定では、\[リソース シンボル\] ダイアログ ボックスには、リソース スクリプト ファイル内の変更可能なリソースのみが表示されます。このオプションをオンにすると、変更可能なリソースは太字で表示され、読み取り専用リソースはプレーン テキストで表示されます。  
  
 **次のリソースで使用**  
 シンボル一覧で選択したシンボルを使用するリソースが表示されます。  特定のリソースのエディターに移動するには、**\[次のリソースで使用\]** ボックスでリソースを選択し、**\[表示\]** をクリックします。  詳細については、「[特定のシンボル用のリソース エディターを開く](../Topic/Opening%20the%20Resource%20Editor%20for%20a%20Given%20Symbol.md)」を参照してください。  
  
 **新規作成**  
 \[新規シンボル\] ダイアログ ボックスが開きます。このダイアログ ボックスで、新しいシンボル リソース識別子の名前を定義します。必要に応じて、値も定義できます。  詳細については、「[シンボルの新規作成](../windows/creating-new-symbols.md)」を参照してください。  
  
 **\[変更\]**  
 \[シンボルの変更\] ダイアログ ボックスが開きます。このダイアログ ボックスで、シンボルの名前または値を変更できます。  使用中のコントロールまたはリソースのシンボルを変更するには、対応するリソース エディターを使用する必要があります。  詳細については、「[未使用のシンボルの変更](../Topic/Changing%20Unassigned%20Symbols.md)」を参照してください。  
  
 **表示**  
 対応するリソース エディターで、シンボルが含まれたリソースを開きます。  詳細については、「[特定のシンボル用のリソース エディターを開く](../Topic/Opening%20the%20Resource%20Editor%20for%20a%20Given%20Symbol.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
## 必要条件  
 Win32  
  
## 参照  
 [Viewing Resource Symbols](../windows/viewing-resource-symbols.md)