---
title: "Changing a Symbol or Symbol Name (ID) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.changing"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbol names"
  - "symbols, names"
ms.assetid: 26541832-8dba-4177-b642-e08f94502ea7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Changing a Symbol or Symbol Name (ID)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

リソースまたはリソース オブジェクトを新規作成すると、IDD\_DIALOG1 などの既定のシンボル名が開発環境によって割り当てられます。  [&#91;プロパティ&#93;](../Topic/Properties%20Window.md) ウィンドウを使用して、既定のシンボル名を変更したり、既にリソースに関連付けられているシンボルの名前を変更したりできます。  
  
### リソースのシンボル名を変更するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)で、リソースを選択します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  **\[プロパティ\]** ウィンドウで、新しいシンボル名を入力するか、または **\[ID\]** ボックスの既存のシンボルの一覧からシンボルを選択します。  
  
     新しいシンボル名を入力すると、値が自動的に割り当てられます。  
  
 [&#91;リソース シンボル&#93; ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)を使用すると、現在リソースに割り当てられていないシンボルの名前を変更できます。  詳細については、「[未使用のシンボルの変更](../Topic/Changing%20Unassigned%20Symbols.md)」を参照してください。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 必要条件  
  
 Win32  
  
## 参照  
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)