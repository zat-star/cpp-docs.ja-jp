---
title: "Including Shared (Read-Only) or Calculated Symbols | Microsoft Docs"
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
  - "vc.editors.symbol.shared.calculated"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "symbols, read-only"
  - "symbols, shared"
  - "symbols, calculated"
  - "read-only symbols"
  - "symbol directives"
  - "calculated symbols"
  - "shared symbols"
ms.assetid: 32b77faf-a066-4371-a072-9a5b84c0766d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Including Shared (Read-Only) or Calculated Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

別のアプリケーションによって作成されたリソース ファイルを開発環境に初めて読み取るとき、インクルードされるすべてのヘッダー ファイルが読み取り専用とマークされます。  その後、[&#91;リソース インクルード&#93; ダイアログ ボックス](../windows/resource-includes-dialog-box.md)を使用して、他の読み取り専用のシンボル ヘッダー ファイルを追加できます。  
  
 読み取り専用のシンボル定義を使用する状況の 1 つに、複数のプロジェクト間でシンボル ファイルを共有する場合があります。  
  
 インクルードされるシンボル ファイルは、単純な整数の代わりに式を使用してシンボル値を定義するシンボル定義を含む既存のリソースがあるときに使用することもできます。  例:  
  
```  
#define   IDC_CONTROL1 2100  
#define   IDC_CONTROL2 (IDC_CONTROL1+1)  
```  
  
 計算型シンボルは、次の条件が満たされる場合に環境によって適切に解釈されます。  
  
-   計算型シンボルが読み取り専用シンボル ファイルに配置されている。  
  
-   これらの計算型シンボルが既に割り当てられているリソースがリソース ファイルに含まれている。  
  
-   数値式が求められる。  
  
> [!NOTE]
>  文字列または数値式が求められる場合、式は評価されません。  
  
### 共有 \(読み取り専用\) シンボルをリソース ファイルに含めるには  
  
1.  [リソース ビュー](../windows/resource-view-window.md)で、.rc ファイルを右クリックし、ショートカット メニューの [&#91;リソース ファイルのインクルード&#93;](../windows/resource-includes-dialog-box.md) を選択します。  
  
    > [!NOTE]
    >  プロジェクトに .rc ファイルがまだ含まれていない場合は、「[リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。  
  
2.  **\[読み取り専用ヘッダー ファイル\]** ボックスで、**\#include** コンパイラ ディレクティブを使用して、読み取り専用シンボルを格納するファイルを指定します。  
  
     Resource.h を呼び出さないでください。これは、通常、メイン シンボル ヘッダー ファイルで使用されるファイル名です。  
  
    > [!NOTE]
    >  **重要** \[読み取り専用ヘッダー ファイル\] ボックスに入力した内容がそのままリソース ファイルに反映されます。  入力ミスや構文エラーがないことを確認してください。  
  
     **\[読み取り専用ヘッダー ファイル\]** ボックスは、シンボル定義を含むファイルをインクルードするためにのみ使用してください。  リソース定義をインクルードする目的には使用しないでください。そうでないと、ファイルを保存したときに重複するリソース定義が作成されます。  
  
3.  指定したファイルにシンボルを配置します。  
  
     この方法でインクルードされるファイル内のシンボルは、リソース ファイルを開くたびに評価されますが、ファイルを保存するときにディスク上で置き換えられません。  
  
4.  **\[OK\]** をクリックします。  
  
 マネージ プロジェクトにリソースを追加する方法については、『.NET Framework 開発者ガイド』の「[アプリケーションのリソース](../Topic/Resources%20in%20Desktop%20Apps.md)」を参照してください。 マネージ プロジェクトにリソース ファイルを手動で追加する方法、リソースへのアクセス方法、静的リソースの表示方法、およびリソース文字列をプロパティに割り当てる方法については、「[Walkthrough: Using Resources for Localization with ASP.NET](../Topic/Walkthrough:%20Using%20Resources%20for%20Localization%20with%20ASP.NET.md)」を参照してください。  
  
 必要条件  
  
 Win32  
  
## 参照  
 [Symbol Name Restrictions](../windows/symbol-name-restrictions.md)   
 [Symbol Value Restrictions](../Topic/Symbol%20Value%20Restrictions.md)   
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)