---
title: "テンプレート ファイル | Microsoft Docs"
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
  - "カスタム ウィザード, テンプレート ファイル"
  - "ファイル [C++], 作成 (カスタム ウィザードで)"
  - "テンプレート [C++], ウィザードの"
ms.assetid: 48fae3d8-3a53-4f62-8010-144c5ffe334e
caps.latest.revision: 8
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# テンプレート ファイル
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ウィザードを構成するテンプレートは、テキスト ファイルの集まりです。これらのファイルには、いくつかの[単純なディレクティブ](../ide/template-directives.md)が含まれており、ユーザーの入力に従って解析およびレンダリングされ、スタート プロジェクトに追加されます。  ウィザード コントロールのシンボル テーブルに直接アクセスすることによって、テンプレートの解析に関する適切な情報が取得されます。  
  
 ユーザーに A か B の選択を求めるウィザード用の単純なテンプレートを次に示します。  
  
## 使用例  
  
```  
This file has been created by My Custom wizard.  
You selected:  
[!if TYPE_A]  
Type A  
[!else]  
Type B  
[!endif]  
The name of this project is [!output PROJECT_NAME].root.cpp:  
```  
  
 ユーザーが Type B を選択すると、このテンプレートは次のようにレンダリングされます。  
  
  **This file has been created by My Custom wizard.  You selected:**  
**Type B**  
**The name of this project is MyApp8.**    
## 出力  
  
```  
This file has been created by My Custom wizard.  
You selected:  
Type B  
The name of this project is MyApp8.  
```  
  
 **メモ** この構文は Visual C\+\+ .NET で新しく追加されたものです。  以前のバージョンの Visual C\+\+ の構文は、Visual C\+\+ .NET ではサポートされません。  
  
## 参照  
 [ウィザード用に作成されるファイル](../ide/files-created-for-your-wizard.md)   
 [カスタム ウィザード](../ide/custom-wizard.md)   
 [カスタム ウィザードの作成](../ide/creating-a-custom-wizard.md)   
 [ウィザードのデザイン](../ide/designing-a-wizard.md)   
 [Templates.inf ファイル](../Topic/Templates.inf%20File.md)