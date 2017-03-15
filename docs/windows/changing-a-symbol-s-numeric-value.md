---
title: "Changing a Symbol&#39;s Numeric Value | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.editors.symbol.changing.value"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "numeric values"
  - "symbols, numeric values"
  - "numeric values, changing symbols"
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Changing a Symbol&#39;s Numeric Value
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

1 つのリソースに関連付けられているシンボルの場合は、[プロパティ ウィンドウ](../Topic/Properties%20Window.md)を使用してシンボル値を変更できます。  [&#91;リソース シンボル&#93; ダイアログ ボックス](../windows/resource-symbols-dialog-box.md)を使用すると、現在リソースに割り当てられていないシンボルの値を変更できます。  詳細については、「[未使用のシンボルの変更](../Topic/Changing%20Unassigned%20Symbols.md)」を参照してください。  
  
### 1 つのリソースまたはオブジェクトに割り当てられているシンボル値を変更するには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)で、リソースを選択します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  **\[プロパティ\]** ウィンドウの **\[ID\]** ボックスで、シンボル名、等号、整数の順に入力します。たとえば、次のように入力します。  
  
    ```  
    IDC_EDITNAME=5100  
    ```  
  
 新しい値は、次回のプロジェクトの保存時に、シンボル ヘッダー ファイルに格納されます。  検証後は、\[ID\] ボックスに等号と値は表示されず、シンボル名だけが表示されます。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的なリソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 必要条件  
  
 Win32  
  
## 参照  
 [Symbol Value Restrictions](../Topic/Symbol%20Value%20Restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)