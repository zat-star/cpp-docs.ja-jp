---
title: "デザイン時にコントロールのプロパティを設定する | Microsoft Docs"
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
  - "ActiveX コントロール [C++], プロパティ"
ms.assetid: 963bf498-d371-4cfd-8bed-865427dcfad9
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# デザイン時にコントロールのプロパティを設定する
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

コントロールのプロパティをデザイン時に設定するには、ダイアログ エディターを使用します。  プロパティを設定すると、リソース エディターによってコントロールが指定値に初期化されます。  このプロパティは、プログラムで変更できます。  
  
 すべての[データ バインド コントロール](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)にある **DataSource** プロパティでは、バインドする[データ ソース](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md) コントロールを指定できます。  
  
 単一データ連結コントロールである ADO データ連結コントロールを ADO データ コントロール \(ADODC: ADO Data Control\) に連結するには、**DataField** プロパティを行セット内の有効なフィールドに設定することにより、コントロールを列に関連付ける必要があります。  この操作を行わないと、コンパイルされたアプリケーションがデバッグ ビルドの実行中にアサートします。アサーションは単にコントロールが null 列にバインドされたことを示します。  
  
> [!NOTE]
>  プロパティの \[全般\] タブでは、コントロール ID および .rc ファイルに必要なプロパティを指定できます。この .rc ファイルをコンパイルすると、Windows プログラムのリソース コードが生成されます。  
  
### \[全ページ\] タブでプロパティを設定するには  
  
1.  ダイアログ ボックスに [ActiveX コントロールを挿入します](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)。  
  
2.  ダイアログ エディターでコントロールを右クリックし、**\[プロパティ\]** をクリックします。  
  
3.  **\[すべて\]** タブをクリックしてコントロールのプロパティを表示し、  目的のプロパティに対する初期値を入力します。  
  
 実行時にコントロールのプロパティを設定するには、「[コントロールの実行時の動作を変更する](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)」を参照してください。  
  
## 参照  
 [ActiveX コントロールを使用する](../Topic/Using%20ActiveX%20Controls.md)