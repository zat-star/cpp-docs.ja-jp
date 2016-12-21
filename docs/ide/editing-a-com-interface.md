---
title: "COM インターフェイスの編集 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.com.editing.interfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM インターフェイス, 編集"
  - "メソッド [C++], 追加 (COM インターフェイスに)"
  - "プロパティ [C++], 追加 (COM インターフェイスに)"
ms.assetid: 6c2909e0-af2d-4a37-bb39-ed372e6129cf
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM インターフェイスの編集
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

クラス ビューのショートカット メニューのコマンドを使用して、Visual C\+\+ プロジェクトの COM インターフェイスに新しいメソッドとプロパティを定義できます。  また、ツールボックスで ActiveX コントロールのイベントを定義できます。  
  
 ATL ベースと MFC ベースの COM オブジェクト クラスの場合は、インターフェイスの編集時にクラス実装の編集も行うことができます。  
  
> [!NOTE]
>  \[クラスの追加\] ダイアログ ボックスを使用せずに定義したインターフェイスについては、インターフェイスが手動で追加された場合でも、Visual C\+\+ によりメソッドまたはプロパティが .idl ファイルに追加され、メソッドを実装するクラスにスタブが追加されます。  
  
 以下の 3 つのウィザードは、既存のインターフェイスのカスタマイズに役立ちます。  どのウィザードもクラス ビューから起動できます。  
  
|ウィザード|プロジェクトの種類|  
|-----------|---------------|  
|[プロパティの追加ウィザード](../ide/names-add-property-wizard.md)|ATL プロジェクト、または ATL をサポートする MFC プロジェクト。  プロパティを追加するインターフェイスを右クリックします。<br /><br /> Visual C\+\+ でプロジェクトの種類が検出され、種類に応じて以下のようにプロパティの追加ウィザードのオプションが変更されます。<br /><br /> -   [MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)を使用して作成されたプロジェクトのディスパッチ インターフェイスの場合は、プロパティの追加ウィザードを起動すると MFC 固有のオプションが表示されます。<br />-   MFC ActiveX コントロール インターフェイスの場合は、そのまま使用することも、コントロールに合わせてカスタマイズすることもできるストック メソッドとプロパティの一覧が、プロパティの追加ウィザードに表示されます。<br />-   その他のインターフェイスの場合は、ほとんどの状況で使用できるオプションがプロパティの追加ウィザードに表示されます。|  
|[メソッド追加ウィザード](../ide/add-method-wizard.md)|ATL プロジェクト、または ATL をサポートする MFC プロジェクト。  メソッドを追加するインターフェイスを右クリックします。<br /><br /> Visual C\+\+ でプロジェクトの種類が検出され、種類に応じて以下のようにメソッド追加ウィザードのオプションが変更されます。<br /><br /> -   [MFC アプリケーション ウィザード](../Topic/MFC%20Application%20Wizard.md)を使用して作成されたプロジェクトのディスパッチ インターフェイスの場合は、メソッド追加ウィザードを起動すると MFC 固有のオプションが表示されます。<br />-   MFC ActiveX コントロール インターフェイスの場合は、そのまま使用することも、コントロールに合わせてカスタマイズすることもできるストック メソッドとプロパティの一覧が、メソッド追加ウィザードに表示されます。<br />-   その他のインターフェイスの場合は、ほとんどの状況で使用できるオプションがメソッド追加ウィザードに表示されます。|  
  
 また、クラス ビューでオブジェクトのコントロール クラスを右クリックし、[&#91;インターフェイスの実装&#93;](../Topic/Implement%20Interface%20Wizard.md) をクリックすると、COM コントロールに新しいインターフェイスを実装できます。  
  
## 参照  
 [Working with Resource Files](../mfc/working-with-resource-files.md)   
 [コード ウィザードを使用した機能の追加](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Visual C\+\+ プロジェクトの種類](../ide/visual-cpp-project-types.md)