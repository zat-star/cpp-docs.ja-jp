---
title: "MFC クラスの追加 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.classes.adding.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "クラス [C++], 追加 (MFC を)"
  - "MFC, 追加 (クラスを)"
ms.assetid: 9a96b67f-40bf-43d4-8872-2f8dfc5404f1
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# MFC クラスの追加
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

MFC \(Microsoft Foundation Class\) ライブラリのクラスの派生クラスをプロジェクトに追加するには、[クラス ビュー](http://msdn.microsoft.com/ja-jp/8d7430a9-3e33-454c-a9e1-a85e3d2db925)の \[クラスの追加\] コマンドを使用します。  新しいクラスの名前を指定し、基本クラスを選択し、関連付けるダイアログ ボックスがある場合はその ID を選択します。  コード ウィザードではヘッダー ファイルと実装ファイルを作成し、プロジェクトに追加します。  
  
> [!NOTE]
>  最初に [MFC を使用するアプリケーションを作成](../../atl/reference/mfc-support-in-atl-projects.md)した場合は、MFC クラスを ATL COM アプリケーションに追加できます。  MFC クラスは、MFC サポートを持つ Win32 プロジェクトにも追加できます。  
  
### MFC クラスをプロジェクトに追加するには  
  
1.  クラス ビューでプロジェクト名を右クリックします。  \[追加\] をクリックし、次に \[クラスの追加\] をクリックして [&#91;クラスの追加&#93;](../../ide/add-class-dialog-box.md) ダイアログ ボックスを開きます。  
  
2.  \[テンプレート\] ペインで **\[MFC クラス\]** を選択し、**\[追加\]** をクリックします。  
  
3.  [MFC クラス ウィザード](../../mfc/reference/mfc-add-class-wizard.md)のダイアログ ボックスで、新しいクラスの設定を定義します。  
  
4.  \[完了\] をクリックしてウィザードを閉じ、新しいクラスをクラス ビューに表示します。  ウィザードで作成したファイルは、**ソリューション エクスプローラー**にも表示できます。  
  
## 参照  
 [コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [クラスの追加](../Topic/Adding%20a%20Class%20\(Visual%20C++\).md)   
 [クラスの概要](../../mfc/class-library-overview.md)