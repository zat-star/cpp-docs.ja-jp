---
title: "ストック プロパティ | Microsoft Docs"
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
  - "ストック プロパティ"
  - "ストック プロパティ, ストック プロパティの概要"
ms.assetid: a89fc454-0b8e-447a-9033-4c8af46a24d9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ストック プロパティ
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[プロパティの追加ウィザード](../ide/idl-attributes-add-property-wizard.md)を使用して MFC ディスパッチ インターフェイスにプロパティを追加する場合は、ウィザードの [&#91;名前&#93;](../ide/names-add-property-wizard.md) ページの **\[プロパティ名\]** ボックスからストック プロパティを選択できます。  選択できるプロパティは次のとおりです。  
  
|プロパティ名|Description|  
|------------|-----------------|  
|**\[表示\]**|コントロールの外観を指定する値を取得または設定します。  コントロールの **Appearance** プロパティでは、3 次元の表示効果の使用の有無を指定できます。  これは読み取り\/書き込みアンビエント プロパティです。|  
|`BackColor`|パレット カラー \(RGB\) または定義済みのシステム カラーに対して、コントロールの `BackColor` アンビエント プロパティを取得または設定します。  既定では、このプロパティの値はコントロールのコンテナーの前景色に対応します。  これは読み取り\/書き込みアンビエント プロパティです。|  
|`BorderStyle`|コントロールの境界線スタイルを取得または設定します。  これは読み取り\/書き込みプロパティです。|  
|**\[キャプション\]**|コントロールの **Caption** プロパティを取得または設定します。  キャプションとはウィンドウのタイトルです。  **Caption** を選択すると、\[メンバー変数\] という実装型は表示されなくなります。|  
|**Enabled**|コントロールの **Enabled** プロパティを取得または設定します。  **Enabled** プロパティが True のコントロールは、ユーザー生成イベントに応答できます。|  
|**フォント**|コントロールのアンビエント フォントを取得または設定します。  コントロールにフォントがない場合には Null です。|  
|`ForeColor`|コントロールの `ForeColor` アンビエント プロパティを取得または設定します。|  
|**hWnd**|コントロールの **hWnd** プロパティを取得または設定します。  **hWnd** を選択すると、\[メンバー変数\] という実装型は表示されなくなります。|  
|**ReadyState**|コントロールの **ReadyState** プロパティを取得または設定します。  コントロールは、初期化前、初期化済み、読み込み中、対話形式、または完了のいずれかの状態になります。  詳細については、「WebBrowser Control」の「[READYSTATE](https://msdn.microsoft.com/en-us/library/aa768362.aspx)」を参照してください。|  
|**テキスト**|コントロールに含まれるテキストを取得または設定します。  **Text** を選択すると、\[メンバー変数\] という実装型は表示されなくなります。|  
  
## 参照  
 [プロパティの追加](../Topic/Adding%20a%20Property%20\(Visual%20C++\).md)   
 [\[IDL 属性\] \(プロパティの追加ウィザード\)](../Topic/IDL%20Attributes,%20Add%20Property%20Wizard.md)